---
title: Introduction to LESS.js -Part 2
subtitle: A interesting tale about function of design
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2011-05-17'
thumb_image: images/lessLgImg.png
thumb_image_alt: White concrete building wall
image: images/lessLgImg.png
image_alt: White concrete building wall
seo:
  title: Introduction to LESS.js -Part 2
  description: >-
    Learning more about LESS with nested rules, mixins and more.
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Introduction to LESS.js -Part 2
      keyName: property
    - name: 'og:description'
      value: >-
       Learning more about LESS with nested rules, mixins and more.
      keyName: property
    - name: 'og:image'
      value: images/lessLgImg.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Introduction to LESS.js -Part 2
    - name: 'twitter:description'
      value: >-
        Learning more about LESS with nested rules, mixins and more.
    - name: 'twitter:image'
      value: images/lessLgImg.png
      relativeUrl: true
layout: post
---

## Using LESS #2: Nested Rules

This is something I love using when marking up CSS with LESS. Rather than constructing long selector names to specify inheritance, in LESS you can simply nest selectors inside other selectors. This makes inheritance from parents much easier to visualize on a page, at least in my opinion. Check this out, this is how you should normally go about styling the paragraph in our header HTML markup:

```css
#header h2 { font-size: 26px; font-weight: bold; } #header p { font-size: 12px; color: #FFFFFF; } #header p a { text-decoration: none; } #header p a:hover { border-width: 1px; }
```

Ok nothing new here. If you wanted to target children, you have to declare the parent first, then each child element till you arrive at the one you want to style. Boring!! With Nested Rules you can write Example 2 like this:

```css
#header { h2 { font-size: 26px; font-weight: bold; } //Close h2 p { font-size: 12px; color: @color; a { text-decoration: none; &amp;:hover { border-width: 1px } //Close :hover } //Close a } //Close p } //Close  header
```

Now, when you "nest" a child element inside its parent, it takes all the styling of the parent and applies it to the children for you! Notice the & combinator. It is used when you want a nested selector to be concatenated (joined) to its parent selector, instead of acting as a descendent. This is especially important for pseudo-classes like :hover and :focus. I'll wait a second while you calm yourself from the realization of how much time you could of saved yourself on past projects using this method. Are you ok to continue now? Your sure? Okay, awesome!

## Using LESS #3: Mixins (Parametric Included)

So if you're like me and other developers/designers and want your fancy CSS 3 shadows, rounded borders etc... working on all browers you know the pain of typing out all the versions for each runtime (moz, webkit, standard) so this is where Mix-In's come into play. **Mixins allow you to embed all the properties of a class into another class by simply including the class name as one of its properties!** Yes, I realize that sounds like a mouthful, but think of it like a variable, but for whole CSS classes. **Mixins can also behave like functions too and take arguments as well**, as seen below in Example 3:

```css // LESS

@footcolor: #000000;

/* Create Mixin .rounded-corners and assign a @radius: variable to pass through */

.rounded-corners (@radius: 5px) {
     border-radius: @radius; -webkit-border-radius: @radius; -moz-border-radius: @radius; }

#header { .rounded-corners; } #footer { background-color: @footcolor; .rounded-corners(10px); }

/* Compiled CSS in browser */

#header { 
    border-radius: 5px; /* This is 5px because that's the default @radius value we set */ -webkit-border-radius: 5px; /* This is 5px because that's the default @radius value we set */ -moz-border-radius: 5px; /* This is 5px because that's the default @radius value we set */ 
    } 
#footer { 
    background-color: #000000; border-radius: 10px; /* This is 10px because we passed a value of 10px */ -webkit-border-radius: 10px; /* This is 10px because we passed a value of 10px */ 
    -moz-border-radius: 10px; /* This is 10px because we passed a value of 10px */ 
    }
```

Wow lots going on here so let's break Example 3 down! The proper usage to make a Mixin is like a CSS class and Javascript function in one. Proper usage is _.mixinName() {}_. Looking like a CSS class but, has the power of a Javascript function.

So we want to set a border radius but only want to type out the code once. We can set a mixin to call all 3 at the same time by making one like a variable but rather than give it one value, we can assign multiple to a mixin:

```css //LESS

.rounded-corners() { border-radius: 5px; -webkit-border-radius: 5px; -moz-border-radius: 5px; }

#header { .rounded corners; }
```

So here we made our mixin and gave it something to output. And this would work for our Example 3 /\* Compiled CSS in Browser \*/ result for #header but we want more control over the border-radius and we don't want to make a different mixin for each different radius size so we can give the mixin an arguement to pass through to our styling:

```css //LESS

.rounded-corners(@radius: 5px;) { // 1) We create our new variable inside the Mixin border-radius: @radius; // 2) We then Add the Variable where it needs to appear to affect the styling -webkit-border-radius: @radius; -moz-border-raidus: @radius; }

#footer { background-color: @footcolor; .rounded-corners(10px); }
```

Now we have a Parametric Mixin! This would output the #footer result from Example 3 /\* Compiled CSS in Browser \*/ above. By passing the 10px as the mixin's arguement you can effectivly alter the created variable to your liking! You will use Mixins often if you choose to use LESS so this concept is particularly important. Try it out and play around with them to learn how they work.

Continue on to [Introduction to LESS.js -Part 3](/introduction-to-less-js-part-3/) here.
