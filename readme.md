

[![Build Status](http://img.shields.io/travis/badges/badgerbadgerbadger.svg?style=flat-square)](https://travis-ci.org/badges/badgerbadgerbadger) [![Coverage Status](http://img.shields.io/coveralls/badges/badgerbadgerbadger.svg?style=flat-square)](https://coveralls.io/r/badges/badgerbadgerbadger)
[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)

# debut-shopify-tailwinnd-starter

---

---
### Debut theme starter project using tailwindcss.
#### This project is the most easy way to combine shopify theme (css/sass) using tailwindCSS without css override.
![Alt text](https://i.imgur.com/pZe9RNT.png)


<!-- TABLE OF CONTENTS -->
## Table of Contents

* [Setup](#Setup)
* [Compatibility issues shopify and Tailwindcss](#Compatibility issues shopify  Tailwindcss)
* [Usage](#usage)
* [Contributing](#contributing)
* [useful link](#useful-link)


---
# Setup
#### 1 - Setup theme kit. 
```bash
$ theme watch
```
*Synchronize as a priority the local theme with the sass theme. More information here*
[shopifyThemekit](https://shopify.github.io/themekit/) 
[shopifyThemekitCommands](https://help.github.com/en/articles/fork-a-repo) 

#### 2 - Modify theme.liquid with this line.
```twig
  {{ 'file.css' | asset_url | stylesheet_tag }}
```
*This file.css is the new tailwindcss class generated using nodejs script*

```bash
# install dependencies
$ npm install
```

```bash
$ npm run dev
$ npm run prod
```
*`npm run dev generate`* generate a file.css with ALL tailwind class for production.

*`npm run prod script` scan all the theme and search specify tailwind.class*

---
## Compatibility issues shopify + Tailwindcss
*Initially tailwindcss posed a lot of style problems on a shopify project. I have desactivated two important core plugin see `tailwin.config.js`.*
[See Tailwind CSS Core plugins](https://tailwindcss.com/docs/configuration/#core-plugins) 

Preflight modify global style, like size/spacing of svg icon. H1/H2 etc...
Display override grid class. It breaks the navigation bar, product page and some sections. A solution exist. You can manually replace grid class by flexbox class like on this example, but the result are not perfect.

```css
grid grid--no-gutters grid--table
```
by
```css
flex flex-row items-center

```
#### Here the actual tailwind config file
```js
// tailwind.config.js
module.exports = {
  corePlugins: {
    preflight: false,
    display: false
  }
}
```

*The other way around. Here's a list of all the plugins that work.*
```js
// tailwind.config.js
module.exports = {
  corePlugins: [
    'container',
    'accessibility',
    'alignContent',
    'alignItems',
    'alignSelf',
    'appearance',
    'backgroundAttachment',
    'backgroundColor',
    'backgroundPosition',
    'backgroundRepeat',
    'backgroundSize',
    'borderCollapse',
    'borderColor',
    'borderRadius',
    'borderStyle',
    'borderWidth',
    'boxSizing',
    'boxShadow',
    'clear',
    'cursor',

    'fill',
    'flex',
    'flexDirection',
    'flexGrow',
    'flexShrink',
    'flexWrap',
    'float',
    'gap',
    'gridAutoFlow',
    'gridColumn',
    'gridColumnStart',
    'gridColumnEnd',
    'gridRow',
    'gridRowStart',
    'gridRowEnd',
    'gridTemplateColumns',
    'gridTemplateRows',
    'fontFamily',
    'fontSize',
    'fontSmoothing',
    'fontStyle',
    'fontWeight',
    'height',
    'inset',
    'justifyContent',
    'letterSpacing',
    'lineHeight',
    'listStylePosition',
    'listStyleType',
    'margin',
    'maxHeight',
    'maxWidth',
    'minHeight',
    'minWidth',
    'objectFit',
    'objectPosition',
    'opacity',
    'order',
    'outline',
    'overflow',
    'padding',
    'pointerEvents',
    'position',
    'resize',
    'rotate',
    'scale',
    'skew',
    'stroke',
    'strokeWidth',
    'tableLayout',
    'textAlign',
    'textColor',
    'textDecoration',
    'textTransform',
    'transform',
    'transitionDuration',
    'transitionProperty',
    'transitionTimingFunction',
    'translate',
    'userSelect',
    'verticalAlign',
    'visibility',
    'width',
    'wordBreak',
    'zIndex',
  ]
}
```


## Contributing

1. [Create a fork](https://help.github.com/en/articles/fork-a-repo) of this project
2. Clone the project:
```bash
git clone https://github.com/<YOUR_GITHUB_USERNAME>/debut-shopify-tailwind-starter
```
2. Create your Feature Branch (`git checkout -b AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

--
## Useful link and ressources
* [Shopify for dev](https://www.shopify.com/partners)
* [dev shopify tutorials](https://shopify.dev/tutorials#themes)












