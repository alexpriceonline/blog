---
title: 3 Key Points to Writing Killer CSS
summary: Whether you're a seasoned front-end developer, or a CSS rookie, writing readable and maintainable styles can be really tough. But struggle no longer. I've written a comprehensive guide to writing super CSS.
date: 2016-05-28T11:03:10+00:00
author: Alex Price
layout: post
permalink: /3-tips-for-great-css/
categories:
  - tips
tags:
  - CSS
  - SCSS
  - Style guide
---
# Writing Good CSS is Hard

Whether you're a seasoned front-end developer, or a CSS rookie, writing readable and maintainable styles can be really tough. But struggle no longer. I've written a comprehensive guide to writing super CSS. _N.B. I did steal the format from <a title="Open the Trello website (new tab)" href="http://trello.com/" rel="noopener no referrer">Trello</a>, but I've made some important updates._

This won't be a long post as the best advice I can give you is to go ahead and read the style guide. But below I will list my top three things to remember.

If you like my approach or want to save the style guide for later, please _star_ing it on Github.

<a title="Read the style guide (new tab)" href="https://github.com/alexpriceonline/scss-style-guide" rel="noopener noreferrer" target="_blank">Read the style guide</a>

## 3 Things to Remember

### 1. <a title="Open the style guide (new tab)" href="https://github.com/alexpriceonline/scss-style-guide#keeping-it-encapsulated" rel="noopener noreferrer" target="_blank">Keep it Encapsulated</a>

Every web page is made up of many elements. We can divide these _elements_ up into **components**. A component is a single, reusable chunk of HTML.

The point of _Encapsulation_ is to keep all of the styles associated with a component in it's own file and in it's own _namespace_. This will stop your components interfering with other components and prevents issues like having to override inherited styles. It also makes our files small, readable and maintainable.

### 2. Avoid Nesting, Classes for Everything

This may seem like overkill to some people, but it's super important. Giving each piece of HTML a class allows us to really know what styles are being applied to it, and what _component_ it belongs to.

The best way that I've found to manage this the `.component-child-grandchild` approach and indent each block of CSS equal to the level of ancestry.

<p data-height="265" data-theme-id="0" data-slug-hash="jqgmwp" data-default-tab="html" data-user="alexpriceonline" data-embed-version="2" data-preview="true" class="codepen">See the Pen <a href="http://codepen.io/alexpriceonline/pen/jqgmwp/">SCSS .component-child-grandchild example</a> by Alex Price (<a href="http://codepen.io/alexpriceonline">@alexpriceonline</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

### 3. Avoid `@extend` whenever possible

`@extend` may seem like a wonderful, time saving feature of SCSS, but the second you use it your component is coupled with it's `super`. This is breaks our _'Keep it Encapsulated'_ rule from earlier.

Every time we change styles on the `super` component, we have to make sure it doesn't break any of the components which inherit from it. Plus, the reason you're thinking of `@extend`ing is because you want to add/remove/override some styles, so just **copy the ones you want!** This will prevent coupling and unnecessary overriding.

Another reason—this maybe less important to some people—is you're `super` component file will have to be `@import`ed _before_ the inheriting file. This means your file imports might be in non-alphabetical order. Blasphemy right?.

---

There is a lot to remember when writing awesome CSS. I use this guide as a cheatsheet and refer back to it on an almost daily basis.

<a title="Read the style guide (new tab)" href="https://github.com/alexpriceonline/scss-style-guide" rel="noopener noreferrer" target="_blank">Read the full style guide</a>
