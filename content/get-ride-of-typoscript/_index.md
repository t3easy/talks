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
 
## Thanks for attention
