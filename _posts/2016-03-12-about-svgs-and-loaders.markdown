---
layout: til
title:  "About SVGs and Loaders"
date:   2016-03-12 07:19:04 +0800
categories: til
tags: svg loader npm
---

Recently, I read about how [github was doing away with font icons in favor of SVGs][github-announcement]. Here's how I went about implementing it for one of my side projects.

Copy the svg you want from the [octicons repo][github-octicons] into your project's `assets` folder or something similar.

You can, of course, just paste the svg code manually to your html but they're very unwieldly. Open one up and see how the path attribute is a bit too long to be reasonably maintainable. Github recommended a helper function in their post. It's a tedious process with the way jsx is parsed [a bit differently][react-attributes] from html.

`npm install react-svg-loader` [(repo)][react-svg-loader]

Apparently, you can use a loader to specifically handle your svg files. This one in particular is straightforward. `react-svg-loader` just loads your svg files into something React-readable (e.g., camelCased classnames).

# Usage
{% highlight javascript %}

var Image1 = require('react-svg?es5=1!./image1.svg');
// or
var Image2 = require('babel!react-svg!./image2.svg');

// and use it as
<Image1 width={50} height={50}/>
<Image2 width={50} height={50}/>

{% endhighlight %}
[Check the full instructions over at the repo.][react-svg-loader]

[github-announcement]: https://github.com/blog/2112-delivering-octicons-with-svg
[github-octicons]: https://github.com/github/octicons/tree/master/svg
[react-svg-loader]: https://github.com/boopathi/react-svg-loader
[react-attributes]: https://facebook.github.io/react/docs/tags-and-attributes.html