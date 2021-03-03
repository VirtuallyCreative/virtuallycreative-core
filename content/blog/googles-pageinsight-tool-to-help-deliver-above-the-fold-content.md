---
title: Google's PageInsight Tool to help deliver Above-the-Fold Content
subtitle: A interesting tale about function of design
excerpt: >-
  measure web performance for mobile and desktop is to use Google’s PageSpeed Insights tool.
date: '2018-01-30'
thumb_image: images/above-the-fold-content.png
thumb_image_alt: White concrete building wall
image: images/above-the-fold-content.png
image_alt: White concrete building wall
seo:
  title: Google's PageInsight Tool to help deliver Above-the-Fold Content
  description: >-
    measure web performance for mobile and desktop is to use Google’s PageSpeed Insights tool.
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Google's PageInsight Tool to help deliver Above-the-Fold Content
      keyName: property
    - name: 'og:description'
      value: >-
        measure web performance for mobile and desktop is to use Google’s PageSpeed Insights tool.
      keyName: property
    - name: 'og:image'
      value: images/above-the-fold-content.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Google's PageInsight Tool to help deliver Above-the-Fold Content
    - name: 'twitter:description'
      value: >-
        measure web performance for mobile and desktop is to use Google’s PageSpeed Insights tool.
    - name: 'twitter:image'
      value: images/above-the-fold-content.png
      relativeUrl: true
layout: post
---

A great way to measure web performance for mobile and desktop is to use Google’s PageSpeed Insights tool. It fetches a URL and returns a score that falls into one of three categories:

- Good
- Needs Work
- Poor

The score is based on 10 optimization techniques web developers should consider when creating a solid front-end workflow. One of the trickiest optimization techniques to pass is the dreaded eliminate render-blocking JavaScript and CSS in above-the-fold content.  Let’s explain what this means and how to pass the CSS portion with flying colors.

**What it Means**

Above-the-fold content is the portion of the webpage that is visible in a browser window when the page first loads. This phrase originates from the newspaper-era when the newspaper is folded in stacks and all you can see is what's on top. Hence, "above-the-fold".

Google wants to see inline CSS extracted from your main CSS file and injected into the head tag, allowing everything you see first to be loaded first, as fast as possible. This is difficult to achieve when you have a fat, bundled CSS file that may create some page flicker on load due to its substantial file-size.

**The Easy Fix**

Setting up your project in a way you can manipulate output is the first step. I’m not going to go into too much detail on project structure, but a solid workflow for web developers is to have a development folder with expanded content for editing and a production folder you can output, compress, and manipulate for performance.

To achieve this, I'm using Node.js and Gulp in our example.

Once Node.js and Gulp are set up into your project, you can use the NPM (node package manager) library and search for a package titled “[Critical](https://www.npmjs.com/package/critical)” that can be added to your project Gulp file. We will use Critical to do all the heavy lifting, because it ensures exactly what Google requests. It extracts the CSS from the main file and injects it into the head of the HTML (above the fold).

Install Critical into your project and take a look at the output configuration options that come with Critical. Here is an example of how it could look in your project’s gulpfile.js file:

\[javascript\]var gulp = require("gulp"); var critical = require("critical"); gulp.task("critical", function(cb) { critical.generate({ inline: true, base: "build/", src: "index.html", dest: "index-critical.html", minify: true, dimensions: \[ { height: 667, width: 375 }, { height: 900, width: 1200 } \] }); }); \[/javascript\]

**Options Explained:**

- inline: Set this to "true" and generate the CSS styles to be inline
- base: Directory path in which the source and destination are to be written
- src: Location of the HTML source to be operated against
- dest: Location of where to save the output of an operation
- minify: Enable minification of generated critical-path CSS
- dimensions: Determine the target screen sizes for desktop and mobile

After adding the Critical task, you can now run the command “gulp critical” to generate all the CSS above-the-fold content into your production HTML file.

If you're looking for more, [check out this example project](https://github.com/addyosmani/critical-path-css-demo) showcasing how to use Critical and the performance gains you achieve when doing so.

**Summary**

Following the basic SEO web standards Google provides can help give businesses a better SEO score and the competitive advantage that comes with it. There are many simple solutions like this that will boost your SEO rank, so don’t skip out on doing the research and taking the time to produce a high-quality digital product.
