---
layout: docs
title: Introduction
description: Get started with FloSCSS, Based on the world's most popular framework for building responsive, mobile-first sites, with BootstrapCDN and a template starter page.
group: getting-started
aliases:
  - "/docs/4.3/getting-started/"
  - "/docs/getting-started/"
  - "/getting-started/"
toc: true
---

## Quick start

Looking to quickly add FloSCSS to your project? Use BootstrapCDN, provided for free by the folks at StackPath. Using a package manager or need to download the source files? [Head to the downloads page]({{< docsref "/getting-started/download" >}}).

### CSS

Copy-paste the stylesheet `<link>` into your `<head>` before all other stylesheets to load our CSS.

{{< highlight html >}}

<link rel="stylesheet" href="{{< param "cdn.css" >}}" integrity="{{< param "cdn.css_hash" >}}" crossorigin="anonymous">
{{< /highlight >}}

## Starter template

Be sure to have your pages set up with the latest design and development standards. That means using an HTML5 doctype and including a viewport meta tag for proper responsive behaviors. Put it all together and your pages should look like this:

{{< highlight html >}}

<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="{{< param "cdn.css" >}}" integrity="{{< param "cdn.css_hash" >}}" crossorigin="anonymous">

    <title>Hello, world!</title>

  </head>
  <body>
    <span class="h1 text-primary">FloSports</span>
  </body>
</html>
{{< /highlight >}}

That's all you need for overall page requirements. Visit the [Layout docs]({{< docsref "/layout/overview" >}}) or [our official examples]({{< docsref "/examples" >}}) to start laying out your site's content and components.

## Important globals

FloSCSS employs a handful of important global styles and settings that you'll need to be aware of when using it, all of which are almost exclusively geared towards the _normalization_ of cross browser styles. Let's dive in.

### HTML5 doctype

FloSCSS requires the use of the HTML5 doctype. Without it, you'll see some funky incomplete styling, but including it shouldn't cause any considerable hiccups.

{{< highlight html >}}

<!doctype html>
<html lang="en">
  ...
</html>
{{< /highlight >}}

### Responsive meta tag

FloSCSS is developed _mobile first_, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, **add the responsive viewport meta tag** to your `<head>`.

{{< highlight html >}}

<meta name="viewport" content="width=device-width, initial-scale=1">
{{< /highlight >}}

You can see an example of this in action in the [starter template](#starter-template).

### Box-sizing

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

{{< highlight css >}}
.selector-for-some-widget {
box-sizing: content-box;
}
{{< /highlight >}}

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot

For improved cross-browser rendering, we use [Reboot]({{< docsref "/content/reboot" >}}) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.
