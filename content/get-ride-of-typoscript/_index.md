+++
title = "Get rid of TypoScript (almost)"
outputs = ["Reveal"]
+++

# Get rid of TypoScript (almost)

---

## Assets

```typoscript
page.includeCSS {
  main = EXT:sitepackage/Resources/Public/Assets/main.css
  webfonts = EXT:sitepackage/Resources/Public/Assets/webfonts.css
}

page.includeJSFooter {
  main = EXT:sitepackage/Resources/Public/Assets/main.js
}
```

```html
<f:asset.css identifier="main" href="EXT:sitepackage/Resources/Public/Assets/main.css"/>
<f:asset.css identifier="webfonts" href="EXT:sitepackage/Resources/Public/Assets/webfonts.css"/>
<f:asset.script identifier="main" src="EXT:sitepackage/Resources/Public/Assets/main.js"/>
```

---

## Metatags

```typoscript
page.meta {
  viewport = width=device-width, initial-scale=1.0
}
```

```html
<f:section name="HeaderAssets">
    <meta name="viewport" content="width=device-width, initial-scale=1">
</f:section>

```

---

{{% section %}}

## Favicons

If you don't need the html markup, you can publish your favicons directly by their default paths.

```typoscript
page.shortcutIcon = EXT:sitepackage/Resources/Public/Icons/favicon.ico
page.headerData.1731399311 = COA
page.headerData.1731399311 {
  10 = IMAGE
  10 {
    file = EXT:sitepackage/Resources/Public/Icons/apple-touch-icon.png
    file.width = 60
    file.height = 60
    layoutKey = apple-touch-icon
    layout {
      apple-touch-icon {
        element = <link rel="apple-touch-icon" href="###SRC###"###SELFCLOSINGTAGSLASH###>
      }
      # a lot of more layouts...
    }
  }
  20 < .10
  20.layoutKey = msapplication-TileImage
  # ...
}
```

---

## Favicons since v13.3

```yaml
- route: favicon.ico
  type: asset
  asset: EXT:sitepackage/Resources/Public/Icons/favicon.ico
- route: apple-touch-icon.png
  type: asset
  source: EXT:sitepackage/Resources/Public/Icons/apple-touch-icon.png
- route: mstile-150x150.png
  type: asset
  source: EXT:sitepackage/Resources/Public/Icons/mstile-150x150.png
```

---

## Favicons in v12

With routing > jpmschuler/staticpathrouteresolver

```yaml
- route: favicon.ico
  asset: EXT:sitepackage/Resources/Public/Icons/favicon.ico
- route: apple-touch-icon.png
  source: EXT:sitepackage/Resources/Public/Icons/apple-touch-icon.png
- route: mstile-150x150.png
  source: EXT:sitepackage/Resources/Public/Icons/mstile-150x150.png
```

---

## Worked from v9 to v11

```yaml
- route: favicon.ico
  type: uri
  source: FILE:EXT:sitepackage/Resources/Public/Icons/favicon.ico
- route: apple-touch-icon.png
  type: uri
  source: FILE:EXT:sitepackage/Resources/Public/Icons/apple-touch-icon.png
- route: mstile-150x150.png
  type: uri
  source: FILE:EXT:sitepackage/Resources/Public/Icons/mstile-150x150.png
```

{{% /section %}}

---

## Thanks for attention
