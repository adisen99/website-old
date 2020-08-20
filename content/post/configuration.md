---
date: 2019-04-13T11:15:58-04:00
description: "Website shortcodes and syntax highlighting"
featured_image: ""
tags: ["Code"]
title: "Configuration"
---

Here are some helpful tips for setting up this theme.

## Syntax Highlighting

Ananke theme allows the use of Hugo's rich built-in syntax highlighting capabilities. See [Syntax Highlighting](https://gohugo.io/content-management/syntax-highlighting/) in the Hugo docs.

Below is an example configuration for Highlight. See [Highlight in the Hugo docs](https://gohugo.io/getting-started/configuration-markup#highlight) for more.

```toml
[markup]
  [markup.highlight]
    codeFences = true
    guessSyntax = false
    hl_Lines = ""
    lineNoStart = 1
    lineNos = false
    lineNumbersInTable = true
    noClasses = true
    # For styles, see https://xyproto.github.io/splash/docs/longer/all.html
    style = "friendly"
    tabWidth = 4
```

## Shortcodes

[Custom shortcodes](https://gohugo.io/templates/shortcode-templates/) can be added to a `layouts/shortcodes/` directory in your site root. Below, I use two custom shortcodes to display a data file: the current configuration file for this site! See the [source for this page](https://github.com/theNewDynamic/gohugo-theme-ananke) to understand how to use shortcodes.

## Show HTML in Posts

To ensure Hugo renders any HTML that your shortcode or other additions like Font Awesome uses in posts, make sure these lines for [the Goldmark renderer](https://gohugo.io/getting-started/configuration-markup) are in your `config.toml`:

```toml
[markup]
defaultMarkdownHandler = "goldmark"

[markup.goldmark]

[markup.goldmark.renderer]
unsafe = true
```

## Configuration

Introduction can be easily configured using [Hugo's configuration file](https://gohugo.io/getting-started/configuration/). You can copy the `config.toml` in the `exampleSite/` to your site root get started.

Here are all the options included in the configuration file for this example site!

```toml
title = "Food 4 Thought"
baseURL = "https://example.com"
languageCode = "en-us"
theme = "ananke"

DefaultContentLanguage = "en"
SectionPagesMenu = "main"
Paginate = 10 # this is set low for demonstrating with dummy content. Set to a higher number
googleAnalytics = ""
enableRobotsTXT = true
enableInlineShortcodes = true

[sitemap]
  changefreq = "monthly"
  priority = 0.5
  filename = "sitemap.xml"

[params]
  favicon = "/images/favicon.ico"
  site_logo = "/logo/favicon-32x32.png"
  description = "Blog | Aditya Sengupta"
  facebook = ""
  twitter = "https://twitter.com/adi_sen99"
  instagram = "https://instagram.com/adi_sen99"
  youtube = ""
  github = "https://github.com/adisen99"
  gitlab = "https://gitlab.com/adisen99"
  linkedin = "https://www.linkedin.com/in/aditya-sengupta-10/"
  mastodon = "https://mastodon.online/@adisen99"
  slack = ""
  researchgate = "https://www.researchgate.net/profile/Aditya_Sengupta5"
  stackoverflow = ""
  rss = ""
  # choose a background color from any on this page: http://tachyons.io/docs/themes/skins/ and preface it with "bg-"
  background_color_class = "bg-black"
  featured_image = "/images/f4f.jpg"
  recent_posts_number = 3
  body_classes = "helvetica neue bg-near-white"
  custom_css = ["/dist/css/custom1.css","/dist/css/custom2.css"]
```
