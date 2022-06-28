One of the guiding principles of NexT is to hide complex details and give you a simple but flexible config, so you can use it easily.

The values given in the document are often typical allowable values rather than default values. They may be different from those in NexT config file.

### [](https://theme-next.js.org/docs/theme-settings/#NexT-Quick-Start "NexT Quick Start")NexT Quick Start

#### [](https://theme-next.js.org/docs/theme-settings/#Cache-Support "Cache Support")Cache Support

NexT v6+ allows to cache content generation. Set the value `enable` to `true` in `cache` section in NexT config file as following:

NexT config file

```
cache:  enable: true
```

#### [](https://theme-next.js.org/docs/theme-settings/#Minify-Support "Minify Support")Minify Support

NexT allows to minify Hexo generation. Set the value `minify` to `true` in NexT config file as following:

NexT config file

```
minify: true
```

#### [](https://theme-next.js.org/docs/theme-settings/#Choosing-Scheme "Choosing Scheme")Choosing Scheme

Scheme is a feature supported by NexT, by using Scheme NexT gives you different views. And nearly all config can be used by those Schemes. Till now NexT supports 4 schemes, and they are:

-   **`Muse`** → Default Scheme, this is the initial version of NexT. Uses black-white tone and mainly looks cleanly.
-   `Mist` → A tighter version of Muse with a tidy single-column view.
-   `Pisces` → Double-column Scheme, fresh like your neighbor's daughter.
-   `Gemini` → Looks like Pisces, but have distinct column blocks with shadow to appear more sensitive to view.

You can change Scheme by editing NexT config file, searching `scheme` keyword. You'll see 4 lines of scheme settings and can enable one of them by removing it's `#` and added `#` to previous.

NexT config file

```
scheme: Gemini
```

#### [](https://theme-next.js.org/docs/theme-settings/#Dark-Mode "Dark Mode")Dark Mode

![NexT Schemes](https://theme-next.js.org/images/next-schemes.png) ![NexT Schemes](https://theme-next.js.org/images/next-schemes-dark.png)

You can enable Dark Mode by setting `darkmode` to `true` in NexT config file.

NexT config file

```
darkmode: true
```

The `prefers-color-scheme` CSS media feature is used to bring Dark Mode to all 4 schemes above, make sure your browser supports it.

Theme NexT automatically shows Dark Mode if the OS prefered theme is dark. It's supported by macOS Mojave, iOS 13 and Android 10 or later. Relevant docs:  
[How to use Dark Mode on your Mac](https://support.apple.com/en-us/HT208976)  
[Use Dark Mode on your iPhone, iPad, or iPod touch](https://support.apple.com/en-us/HT210332)  
[Dark theme | Android Developers](https://developer.android.com/guide/topics/ui/look-and-feel/darktheme)

#### [](https://theme-next.js.org/docs/theme-settings/#Configuring-Favicon "Configuring Favicon")Configuring Favicon

By default the Hexo site use NexT favicons in `hexo-site/themes/next/source/images/` directory with different size for different device. You can replace them with your own favicons.

For example, you can put your favicons in `hexo-site/source/images/` directory. Then you need to rename them and change the settings in `favicon` section in NexT config file, otherwise icons from Next will rewrite your custom icons in Hexo.

You can also put custom favicons into `hexo-site/source/` directory. In this way, you **must remove** `/images` prefix from paths.

To generate custom favicons, you can visit [Favicon Generator](https://realfavicongenerator.net/).

Hexo config file

```
favicon:  small: /images/favicon-16x16-next.png  medium: /images/favicon-32x32-next.png  apple_touch_icon: /images/apple-touch-icon-next.png  safari_pinned_tab: /images/logo.svg  android_manifest: /images/manifest.json
```

#### [](https://theme-next.js.org/docs/theme-settings/#Custom-Logo-Support "Custom Logo Support")Custom Logo Support

NexT supports the site logo personalization.

You can enable it by adding images's url to `custom_logo` in NexT config file.

NexT config file

```
custom_logo: /uploads/custom-logo.jpg
```

Scheme Mist does not support custom logo setting.

#### [](https://theme-next.js.org/docs/theme-settings/#Creative-Commons "Creative Commons")Creative Commons

NexT supports the display of [Creative Commons 4.0 International License](https://creativecommons.org/) in sidebar and post including `by`, `by-nc`, `by-nc-nd`, `by-nc-sa`, `by-nd`, `by-sa` and `cc-zero`. These licenses allow creators to communicate which rights they reserve, and which rights they waive for the benefit of recipients or other creators.

You can configure it by editing values in `creative_commons` section in NexT config file, for example:

NexT config file

```
creative_commons:    license: by-nc-sa    size: small  sidebar: true  post: true  language: deed.zh
```

You can set a language value if you prefer a translated version of CC license, e.g. deed.zh  
CC licenses are available in 39 languages, you can find the specific and correct abbreviation you need on [https://creativecommons.org](https://creativecommons.org/)

#### [](https://theme-next.js.org/docs/theme-settings/#Open-Graph "Open Graph")Open Graph

NexT config file

```
open_graph:  enable: true    options:    type: blog
```

Menu settings items have format `Key: /link/ || icon` which contains 3 values:

By default, all menu items are commented out to ensure that you can override them in the [Alternate Theme Config](https://theme-next.js.org/docs/getting-started/configuration.html).  
To customize menu items, edit the following content in NexT config file:

NexT config file

```
menu:  home: / || fa fa-home        archives: /archives/ || fa fa-archive      
```

Dynamic sub-menu within hierarchy structure is also supported. Add your sub-menu items in `menu` section in NexT config file as following:

NexT config file

```
menu:  home: / || fa fa-home  archives: /archives/ || fa fa-archive  Docs:    default: /docs/ || fa fa-book    Getting Started:      default: /getting-started/ || fa fa-flag      Installation: /installation.html || fa fa-download      Configuration: /configuration.html || fa fa-wrench    Third Party Services:      default: /third-party-services/ || fa fa-puzzle-piece      Math Equations: /math-equations.html || fa fa-square-root-alt      Comment Systems: /comments.html || fa fa-comment-alt
```

A `default` page is required for each sub-menu item.

By default NexT shows the icons of menu items without badges.