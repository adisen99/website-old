---
title: "Regridding `.nc` files using Python"
date: 2021-11-07T15:31:17+05:30
publishdate: 2021-11-07T15:31:17+05:30
tags: ["Python", "Meteorology"]
comments: true
draft: false
---

Here is a basic script to re-grid multiple `.nc` data files in python using `xesmf`, `xarray` and `dask` libraries and output to a new directory -

```python
# Regridding using ESMF library in python (xesmf)
# the new regrid script using the ESMF regridding framework

import numpy as np
import xarray as xr
import dask.array as da
import xesmf as xe
import time
import os
from dask.distributed import Client
from dask.diagnostics import ProgressBar

# Main function
def main():
    with os.scandir('../data/GPM_data/') as it: # enter the directory containing input .nc files
        for entry in it:
            if entry.name.endswith('.nc') and entry.is_file() and not os.path.exists('../data/GPM_lowres_data/' + entry.name):
                print("Starting the Regridding of - " + entry.name + " ...")

                # loading the data
                ds = xr.open_dataset(entry.path, chunks=dict(time=2000))
                ds.unify_chunks()
                ds = ds.drop_dims('bnds')
                ds = ds.transpose('time', 'lat', 'lon')

                print("Data is imported successfully ...")

                # prepare the regridding
                ds_out = xr.Dataset({'lat': (['lat'], np.arange(0, 40.25, 0.25)),
                    'lon': (['lon'], np.arange(60, 100.25, 0.25)),
                    }
                )
                regridder = xe.Regridder(ds, ds_out, 'bilinear')

                print("Data has been successfully prepared for regridding ...")

                # Do the regridding
                dr_out = regridder(ds.precipitationCal)

                print("The data has been regridded, now exporting ...")

                # Ooutput the data
                dr_out = dr_out.to_dataset(name = 'precipCal')
                delayedObj = dr_out.to_netcdf('../data/GPM_lowres_data/' + entry.name, compute=False) # enter the directory to output the regridded .nc files

                with ProgressBar():
                    results = delayedObj.compute()

                print(results)
                print("Finished Regridding and data exported " + entry.name)
                time.sleep(7)

if __name__ == "__main__":
    main()
    print("Finished the Regridding process")
```

Just run the script with the correct names of input and output directories for your data and you're good to go. Thank me later. ;)
