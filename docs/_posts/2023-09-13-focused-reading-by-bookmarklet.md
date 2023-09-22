---
layout: post
title:  "Focused Article Reading tool with Bookmarklet"
date:   2023-09-14 00:00:16 -0700
categories: Bookmarklet
---

Monitors are big, attention is narrow.

When reading websites and focus on the article, I often can't help but felt distracted by the surroundings on the rest of the page. So I asked chatgpt to create a solution for me, it gives some javascript code that actually works!

Here is the code:
{% highlight javascript%}
javascript:(function() {
let D=document;
const M = D.querySelector('article, .article-content .rich_media_wrp') || D.querySelector('main, .main-content');
if (M) {
 let r = M.getBoundingClientRect();
 let clone = M.cloneNode(true);
 Object.assign(clone.style, {
  position: 'absolute',
  top: `${r.top}px`,
  left: `${r.left}px`,
  width: `${M.offsetWidth}px`,
  background: '#fff',
  zIndex: '1002',
  padding: '20px',
  boxSizing: 'border-box'
 });
 D.body.appendChild(clone);
 const overlay = D.createElement('div');
 overlay.style.cssText = `position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.8); z-index: 1000;`;
 D.body.appendChild(overlay);
}
})();
{% endhighlight %}

Note: `.rech_media_wrap` is an example of customization, it is used in wechat articles web version as of 2023/09/14.


I created a bookmarklet for this:

<a href="javascript:(function() %7B const main = document.querySelector('article, .article-content, .rich_media_wrp') %7C%7C document.querySelector('main, .main-content'); const overlay = document.createElement('div'); if (main) %7B main.style.cssText = %60z-index: 1001; position:relative; padding: 20px; background: %23fff;%60; overlay.style.cssText = %60position: fixed; top: 0; left: 0; width: 100%25; height: 100%25; background: rgba(0, 0, 0, 0.8); z-index: 1000;%60; document.body.appendChild(overlay); %7D %7D)();">Focus</a>

Just drag it onto your bookmark bar, and try click it on current page. So far it only works for typical websites where they use `article` or `main` properly. If you don't like the effect, refresh the page it will go away.

Feel free to tweak it, and remember to comment below about your secret tweaks!
