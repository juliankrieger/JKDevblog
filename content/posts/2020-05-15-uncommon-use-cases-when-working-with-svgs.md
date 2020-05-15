---
template: post
title: 'Uncommon Use-Cases when working with SVGs '
slug: svg-uncommon-use-cases
draft: true
date: 2020-05-15T15:22:24.522Z
description: >-
  In this post, I showcase uncommon SVG use cases I needed at work and how I
  solved them.
category: webdev
tags:
  - svg
  - webdev
  - javascript
  - html
  - css
---
## Letting an SVG image stretch without respecting its aspect-ratio



For this to work, you'll need to change your SVG's header data, notably the `preserveAspectRatio` attribute. The spec at [mozilla](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/preserveAspectRatio) helpfully showcases the different options. This attribute needs a `viewBox` to be speficied, or it won't work. We want our image to stretch in all directions, so we choose `none`. **However**, MDN fails to specify that our SVG image also **needs** a `width` and `height` attribute for this to work. 

```svg
<svg version="1.1" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px"
     viewBox="0 0 1920 1080" preserveAspectRatio="none" height="100%" width="100%"
     xml:space="preserve"
>
</svg>

```
