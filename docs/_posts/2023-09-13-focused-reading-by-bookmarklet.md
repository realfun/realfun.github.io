---
layout: post
title:  "Focused Reading by Bookmarklet"
date:   2022-07-03 03:01:16 -0700
categories: Bookmarklet
---

Monitors are big, attention is narrow.

When reading websites and focus on the article, I often can't help but felt distracted by the surroundings on the rest of the page. So I asked chatgpt to create a solution for me, it gives some javascript code that actually works!

Here is the code:
{% highlight javacript%}
javascript:(function() {
      const main = document.querySelector('article, .article-content') || document.querySelector('main, .main-content');
      const overlay = document.createElement('div');
      if (main) {
        main.style.cssText = `z-index: 1001; position: relative; background: #fff;%60;
        overlay.style.cssText = `position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.8); z-index: 1000;`;
        document.body.appendChild(overlay);
      }
})();
{% endhighlight %}

I created a bookmarklet for this:

<a href="javascript:(function() {    const main = document.querySelector('article, .article-content') || document.querySelector('main, .main-content');    const overlay = document.createElement('div');    overlay.style.cssText = `position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.8); z-index: 1000;`;    if (main) {        main.style.cssText = `z-index: 1001; position: relative; background: #fff;%60;%20%20%20%20}%20%20%20%20document.body.appendChild(overlay);})();">Focus</a>

Just drag it onto your bookmark bar, and try it out with websites. So far it only works for typical websites where they use `article` or `main` properly. Feel free to modify it!
