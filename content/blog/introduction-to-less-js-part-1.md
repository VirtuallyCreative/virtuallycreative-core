---
title: Introduction to LESS.js -Part 1
subtitle: A interesting tale about function of design
excerpt: >-
  this tutorial is covering today is how to add variables, mixins, nested rules and much more to CSS 3 to make it function like you have never seen before!
date: '2011-05-17'
thumb_image: images/lessLgImg.png
thumb_image_alt: White concrete building wall
image: images/lessLgImg.png
image_alt: White concrete building wall
seo:
  title: Introduction to LESS.js -Part 1
  description: >-
    this tutorial is covering today is how to add variables, mixins, nested rules and much more to CSS 3 to make it function like you have never seen before!
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Introduction to LESS.js -Part 1
      keyName: property
    - name: 'og:description'
      value: >-
        this tutorial is covering today is how to add variables, mixins, nested rules and much more to CSS 3 to make it function like you have never seen before!
      keyName: property
    - name: 'og:image'
      value: images/lessLgImg.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Introduction to LESS.js -Part 1
    - name: 'twitter:description'
      value: >-
        this tutorial is covering today is how to add variables, mixins, nested rules and much more to CSS 3 to make it function like you have never seen before!
    - name: 'twitter:image'
      value: images/lessLgImg.png
      relativeUrl: true
layout: post
---

## The Dynamic Stylesheet Language

Welcome to my second tutorial! Hope you guys find this useful, as I know this has changed the way I use CSS forever!

What this tutorial is covering today is how to add variables, mixins, nested rules and much more to CSS 3 to make it function like you have never seen before! The amount of benefits you can gain from being able to optimize your CSS could be explained here but I just won't do it justice until you see it in action. It should take you about 1-2 hours to learn the concepts presented here.

This tutorial already assumes you know how to code (X)HTML and CSS 3 and should be comfortable with creating basic layouts of pages (including header, content, sidesbars, footers and can style individual elements within containers and it's children). Knowlege of:

- Grouping/Nesting
- Dimensions
- Display
- Positioning
- Floating
- Align
- Pseudo-class
- Pseudo-element
- Image Opacities
- Image Sprites
- Media Types
- CSS Attribute Selectors

would be a big help, but not required. However, I won't be covering (X)HTML/CSS itself in this tutorial, just possibly using elements within those topics, so if you're unfamilar with them I suggest you do a little reading up! If you're unable to write CSS mark-up "on-the-fly" that's not a big deal but, you might want have a stronger base before you start manipulating it! I know I confused myself with my own projects sometimes so making a strong foundation correctly to build upon will always serve you well in the future.

I know what you're thinking now.. "Wait a minute! You can't add variables and all this "mix-in stuff" to CSS! So what's going on here!?".

Well you're correct! Natively Cascading Style Sheets doesn't support this style of scripting but when we add a very clever Javascript libary called LESS.js we can expand CSS beyond just its normal capabilities. Check this out:

```CSS
@color: #FFFFFF; 
#header { background-color: #000000; } 
h2 { color: @color; } 
\* Compiled CSS in browser \*
#header { background-color: #000000; } h2 { color: #FFFFFF; }
```

That is LESS in action with CSS. Don't worry if this looks confusing, all will be explained by reading this shortly. If you already grasp the concept outlined above then you're well on your way to seeing how powerful LESS is and will help in day-to-day CSS coding.

If you already use LESS in your CSS projects then please let us know how you use it to your advantage and some of the things you've created!

#### LESS Info:

LESS was developed by [Alexis Sellier](https://cloudhead.io/ "Alexis Sellier"), more commonly known as [cloudhead](https://cloudhead.io/ "cloudhead"). I am in no way or part taking credit for LESS obviously, just showing you some really cool ways to use it in your CSS coding. You can read more information, see some of the tutorial examples and learn more about LESS.js on the [official page](https://lesscss.org/ "External link").

**NOTE:**In order to use LESS you will need to make sure your browser has Javascript turned on as your website now requires Javascript to display all styling. If you plan to use LESS for mobile development you might run into some issues with Javascript running in some browsers. We will cover a "hack" to solve this issue. But Remember that it requires Javascript to run (LESS, not the "hack")! **END NOTE\*\*\***

### Let's begin: LESS Setup

To acheive what we did with that _#header_ and _h2_ property above, a couple of steps are needed. First we need to setup our environment to use LESS within CSS. This is very easy and can be done in a few steps.

**Step 1:** Download the Less.js file and add it to your project! **You can get it here.** The most current version as of writing (1.0.41.min) is attached **[![Attached File](images/zip.gif.pagespeed.ce.oGdlqcpZFW.gif)](http://www.dreamincode.net/forums/index.php?app=core&module=attach&section=attach&attach_id=23177 "Download attachment") [less-1.0.41.min.zip](http://www.dreamincode.net/forums/index.php?app=core&module=attach&section=attach&attach_id=23177 "Download attachment") **(10.49K)**** along with the example files used. ****OR**** You can just link to it since it's hosted on googlecode like so:

\[javascript\]<script src="http://lesscss.googlecode.com/files/less-1.0.41.min.js"></script>\[/javascript\]

**Step 2:** Start a blank HTML document and either make your own markup or paste the markup below to follow along. We will not be building anything of signifigance HTML layout wise, more just basic elements to help display CSS concepts required for learning, but I do have an important note to make within the _<head>_ tags. This would be a document for your website if it was a real project. Since we are going to be using an external stylesheet for this tutorial you need to link to your css file within the _<head>_ of your HTML and load the LESS.js like any normal CSS stylesheet and Javascript file but their is a difference, can you spot it?:

\[html\]

<meta charset="UTF-8"> <title>LESS.js Tutorial</title> <!-- LESS Stylesheet --> <link rel="stylesheet/less" type="text/css" href="css/style.less">

<!-- LESS Javascript --> <script src="http://lesscss.googlecode.com/files/less-1.0.41.min.js"></script> <div id="header"> <h2>A Headline</h2> This is some text with an <a href="#">anchor</a> present.

</div> <!-- /header --> <div id="footer"> <a href="#">Link Name</a></div> <!-- /footer -->

\[/html\]

If you noticed, the _rel="stylesheet/less"_ and the _href="styles.less"_ are different than the normal _"stylesheet/css"_ and _styles.css_ respectively. In our case LESS uses a special stylesheet ending (.less) which it parses and then outputs a live stylesheet for the browser. Nifty huh! So that means our default stylesheet has a .less ending hence the _"stylesheet/less"_ relationship. After that, we need to import the logic for LESS locally **(Option 1)**, or by calling it with the URL version posted in Step 1 **(Option 2)**. **DO NOT USE BOTH OPTIONS!**

And that's it, now we can start using style.less to style our webpage like normal!

### Using LESS #1: Variables

Our first topic is Variables. If you've ever used Javascript, PHP or any other larger scripting language sooner rather than later, you'll run into variables.

For our purpose, variables allow you to specify widely used values in a single place, and then re-use them throughout the stylesheet. This makes global changes as easy as changing one line of code! Lets use Example 1 and break it down.

Inside our style.less we can define a variable by using the @ symbol before the desired variable name and then give it any value we want. Then we call the variable inside the CSS property #header:

\[css\] @color: #FFFFFF;

#header { color: @color; } \[/css\]

Here we made a new variable @color: and it's value set to #FFFFFF. To use this new variable we made, we are going to assign it to color: by replacing the spot the color hex number (#FFFFFF) normally would of gone. If you save and refresh the page in a browser and view your CSS (I love Firebug for Firefox, or Inspect Element in Safari/Chrome) you should see:

\[css\] #header { color: #FFFFFF; } \[/css\]

This means it works! You just sucessfully made your first CSS variable using LESS.js! Cool stuff huh! So back to Example 1, it's the same concept just with more than one use. That's the beauty of variables! You can use them over and over and it can save you lots of time when you have different specific colours for specific links, nav elements, box shadows etc... but note that variables are actually ‘constants’ in that they can only be defined once. I'll let you play around with the idea and when you're comfortable with creating multiple variables and calling them in various properties we can move on.

Check out [Introduction To LESS.js: -Part 2](http:virtuallycreative.ca/introduction-to-less-js-part-2/) here.
