# food-for-thought
My personal blog/website

**Note** - This GitHub repository has been created to host my personal blog using the GitHub pages. Hence I do not particularly recommend anybody to fork or clone this repository as the changes made to the anake theme are personal changes and won't particularly help anyone. 
But still I made this repo public as I wanted to share the code of the changes I made using the README.md file. All the changes have been shown and you can see them by accessing my website. **Hope it Helps. Happy Coding!!**
_____________________________________________________________________________________________________________________________

### Theme used - 

[Mediumish Theme](https://github.com/lgaida/mediumish-gohugo-theme) - Courtesy [Lenard Gaida](https://github.com/lgaida)
_____________________________________________________________________________________________________________________________

### Modifications made- 

Added the linkedin social share code `share.html` in the folder `layouts/partials/single-partials/` -

```html
<div class="share sticky-top sticky-top-offset">
    <p>Share</p>
    <ul>
        <li class="ml-1 mr-1">
            <a target="_blank" href="https://twitter.com/intent/tweet?text={{ .Title }}&url={{ .Permalink }}"
                onclick="window.open(this.href, 'twitter-share', 'width=550,height=435');return false;">
                <i class="fab fa-twitter"></i>
            </a>
        </li>

        <li class="ml-1 mr-1">
            <a target="_blank" href="https://facebook.com/sharer.php?u={{ .Permalink }}"
                onclick="window.open(this.href, 'facebook-share', 'width=550,height=435');return false;">
                <i class="fab fa-facebook-f"></i>
            </a>
        </li>

        <li class="ml-1 mr-1">
            <a target="_blank" href="https://www.xing.com/spi/shares/new?url={{ .Permalink }}"
                onclick="window.open(this.href, 'xing-share', 'width=550,height=435');return false;">
                <i class="fab fa-xing"></i>
            </a>
        </li>

        <li class="ml-1 mr-1">
            <a target="_blank"
                href="https://www.linkedin.com/shareArticle?mini=true&url={{ .Permalink }}&title={{ .Title }}"
                onclick="window.open(this.href, 'linkedin-share', 'width=550,height=435');return false;">
                <i class="fab fa-linkedin"></i>
            </a>
        </li>
    </ul>

    {{ if .Params.comments }}
    <div class="sep">
    </div>
    <ul>
        <li>
            <a class="small smoothscroll" href="#disqus_thread"></a>
        </li>
    </ul>
    {{ end }}
</div>
```

### ~Make your own website using Hugo as well !! ~
_____________________________________________________________________________________________________________________________

