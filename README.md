# food-for-thought
My personal blog/website

**Note** - This GitHub repository has been created to host my personal blog using the GitHub pages. Hence I do not particularly recommend anybody to fork or clone this repository as the changes made to the anake theme are personal changes and won't particularly help anyone. 
But still I made this repo public as I wanted to share the code of the changes I made using the README.md file. All the changes have been shown and you can see them by accessing my website. **Hope it Helps. Happy Coding!!**
_____________________________________________________________________________________________________________________________

### Theme used - 

[Ananke Gohugo Theme](https://github.com/budparr/gohugo-theme-ananke.git) - Courtesy [Bud Parr](https://github.com/budparr)
_____________________________________________________________________________________________________________________________

### Modifications made- 

* Added the ResearchGate Link on the Home Page in the Social icons section on top right.
  
  * Added the following in the `[params]` section in `config.toml` .
  
  ```
  researchgate = "https://www.researchgate.net/profile/your_profile_name"
  ```
  * Added the *researchgate.svg* image in the `layout/partials/svg/` folder
  
  * Added the following piece of code in `social-follow.html` file in the `layout/partials/` folder.
  
  ```
  {{ with .Param "researchgate" }}
  <a href="{{ . }}" target="_blank" class="link-transition researchgate link dib z-999 pt3 pt0-l mr1" title="ResearchGate link" rel="noopener" aria-label="follow on ResearchGate——Opens in a new window">
  {{ partial "svg/researchgate.svg" (dict "size" $icon_size) }}
  {{- partial "new-window-icon.html" . -}}
  </a>
  {{ end }}
  ```
  * Modified the `_social-icons.css` file in the `src/css/` folder
  
  ``.facebook, .twitter, .instagram, .youtube, .github, .gitlab, .keybase, .linkedin, .researchgate, .medium, .mastodon,        .slack, .stackoverflow {``
    `fill: #BABABA;`
    `}`
    
    And
    
    ``
    `.researchgate:hover {
    `fill: #0cb;
   ` }
    ``
  * Added the name and label in the `stackbit.yaml` file
  
  ```
  models:
  config:
    type: data
    label: Config
    file: config.toml
    fields:
        type: object
        name: params
        label: Params
        description: Site parameters
        required: true
        fields:
           -type: string
            name: researchgate
            label: ResearchGate
  ```
  
* Added the support for comments on my site using DISQUS and commentto according to the instructions given on the [Ananke Hugo theme page](https://themes.gohugo.io/gohugo-theme-ananke/).

* Generated a custom css and custom js file in the `static/dist/css` & `static/dist/js` directories.

### ~Hope this encourages someone to make their own website using Hugo !! ~
_____________________________________________________________________________________________________________________________

