# SCSS Playing Cards

## Introduction

Here is a CSS of 52 playing cards built on top of [younestouati/playing-cards-standard-deck](https://github.com/younestouati/playing-cards-standard-deck), 
which is a fork itself of [digitaldesignlabs/responsive-playing-cards](https://github.com/digitaldesignlabs/responsive-playing-cards).

This library provides CSS classes for displaying cards instead of relying on SVG only.

With the help of SCSS, it aims at being a little customizable and easy to integrate in your application.

## Example usages

With semantic classes:

```html
<div class="pl-card ace-of-clubs"></div>
```

With data-attributes:
```html
<div class="pl-card" data-rank="1" data-suit="♣"></div>
<!-- or -->
<div class="pl-card" data-rank="1"  data-suit="&clubs;"></div>
<!-- or also -->
<div class="pl-card" data-rank="14" data-suit="♣"></div>
<!-- or even -->
<div class="pl-card" data-rank="A" data-suit="♣"></div>
```

### Sizing

You can add `pl-card-[sm|md|lg|xl]` classes to any card to change its size:

```html
<div class="pl-card pl-card-xl ten-of-diamonds"></div>
<div class="pl-card pl-card-sm" data-rank="6" data-suit="&hearts;"></div>
```

Or resize multiple cards at once:
```html
<ul class="pl-cards pl-cards-xl">
    <li class="pl-card jack-of-spades"></li>
    <li class="pl-card queen-of-clubs"></li>
</ul>
```

## Customization

You can use the built-in CSS file in `/dist`: it's plug-and play and ready to use, but at the cost of performance: 
images are base64-encoded to allow uploading the stylesheet anywhere in your public web structure.

The `dist/css-cards.css` is about 1.1MB uncompressed, 470K gzipped.

So, if you're familiar with Webpack, Gulp or whatever, you'd definitely better compile it yourself according to your directory structure:

```scss
@import "./my-variables"; // Optional file of your own to override some variables
@import "~card-game-scss/src/variables";
@import "~card-game-scss/src/main";
@import "~card-game-scss/src/semantics"; // Semantic classes support
@import "~card-game-scss/src/numerics"; // data-attributes support
```

It will then render SVG images with the appropriate URLs.
