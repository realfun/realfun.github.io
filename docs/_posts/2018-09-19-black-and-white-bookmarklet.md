---
layout: post
title:  "Turn web images to black/white/grayscale with Bookmarklet"
date:   2018-09-19 13:01:16 -0700
categories: Bookmarklet
---

My daughter started to learn drawing a while back, recently she is working on sketching. A common homework is to find a greyscale front face to draw with. It is actually hard to find a good quality black and white images on google image search, comparably it is way easier to find normal color front-face images. I downloaded and converted a bunch with imagemagick awhile back, today it was all used up and she wants more.

Then I thought about it and created a simple bookmarklet with this code

{% highlight javascript %}
javascript:(function() {
    document.querySelectorAll('img').forEach(function(ele){
        ele.style='filter: grayscale(100%);'
    });
})();
{% endhighlight %}

If you are using Chrome, right click on the bookmark toolbar and Add Page, in the Name field input “GrayscaleAllImgs”(actually it could be anything), then in the URL field, paste the entire line of code shown above, then click Save.

Or, you can just drag the following to the bookmark toolbar:


<a href="javascript:(function() { document.querySelectorAll('img').forEach(function(ele){ele.style='filter: grayscale(100%);'}); })();">Grayscale</a>


Now you can try it out: in any page like [this one](https://www.google.com/search?q=front+face+headshot&hl=en&tbm=isch), then click the bookmark you just created, then tada~~~the images on the entire page turns black and white.

Notice that this doesn’t work well for some website where they put images on the background instead of normal &lt;img&gt; tag, normally if you right click the image to open the image in new tab, then click the “GracyscaleAllImgs” bookmark in new tab it will work.

Enjoy~
