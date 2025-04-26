---
layout: post
title:  "My Bookmarklet Collection"
date:   2025-04-25 22:36:00 -0700
categories: Bookmarklet
---

Bookmarklets are tiny JavaScript programs you stash in a browser bookmark and run with a click—no extension install,
no compile step. Once you know how to save one and write a few lines of JS (or ask ChatGPT to do it),
you can bend almost any webpage to your will, from stripping clutter to turning the page into a game of Asteroids.

It is a light version of Greasemonkey without installing anything.

What exactly is a bookmarklet?
==============================

A bookmarklet is simply a URL whose scheme is javascript: followed by inline code.
When you click the bookmark, the browser executes that code in the context of the current page,
giving you direct access to the DOM, cookies, and even your clipboard—within the
same-origin rules, of course. The trick first appeared in the late-1990s Netscape era
and quickly became a hacker’s Swiss-army knife for one-off tweaks that
didn’t merit a full browser extension. 

How to Use one (in 5 seconds)
==============================
1. Show your bookmarks bar if it is hidden in your favorite browser. (On Mac Chrome the hotkey is Command+Shift+B)
2. Drag one of the listed bookmarklet onto your bookmark bar(say, <a href="javascript:(function() { document.querySelectorAll('img').forEach(function(ele){ele.style='filter: grayscale(100%);'}); })();">Grayscale Page</a>).
3. Go to a relevant page, click the bookmarklet you added.

You can find more bookmarkes by asking ChatGPT/Grok/Gemini/Claude etc. or just search for it on internet.
Heads-up on security: the code runs with the same privileges as the site you’re on, and bookmarks are stored in plain text, so only install bookmarklets you trust.
One trick is to paste the link content in chatgpt and ask it for advice or just are ChatGPT to create one for you.

Some of my favorite ones
==============================

(If you find the bookmarklet title to be too long on the bookmark bar/list, just rename it after adding them)

  * <a href="javascript:(()=>{const j=['utm_','gclid','fbclid','mc_eid','mc_cid','ref','ref_src','igshid','mkt_','vero_conv'],u=new URL(location);[...u.searchParams.keys()].filter(k=>j.some(x=>k===x||k.startsWith(x))).forEach(k=>u.searchParams.delete(k));history.replaceState(null,'',u);navigator.clipboard.writeText(u.href);document.getElementById('__cleanToast')?.remove();let d=document.createElement('div');d.id='__cleanToast';d.textContent='✅ Clean URL copied';Object.assign(d.style,{position:'fixed',bottom:'20px',left:'50%',transform:'translateX(-50%)',background:'#333',color:'#fff',padding:'8px 14px',borderRadius:'4px',font:'14px/1.4 sans-serif',zIndex:999999,opacity:0,transition:'opacity .3s'});document.body.appendChild(d);requestAnimationFrame(()=>d.style.opacity=1);setTimeout(()=>{d.style.opacity=0;d.addEventListener('transitionend',()=>d.remove(),{once:!0})},2000);})()">Clean Copy</a>: single-click way to grab the “clean” version of the page you’re on, removes common marketing/analytics query strings ( utm_*, gclid, fbclid, etc. ).
  * <a href="javascript:(function() { document.querySelectorAll('img').forEach(function(ele){ele.style='filter: grayscale(100%);'}); })();">Grayscale Page</a>: Turns images on a webpage to grayscale, I used this to help my kids find reference images for Sketch practice.
  * <a href="javascript:(function(){document.querySelectorAll('*').forEach(function(e){e.style.userSelect='auto';e.style.webkitUserSelect='auto';e.style.MozUserSelect='auto';e.style.msUserSelect='auto'});document.oncopy=null;document.oncontextmenu=null;document.querySelectorAll('*').forEach(function(e){e.oncontextmenu=null});document.querySelectorAll('*').forEach(function(e){e.removeEventListener('selectstart',null,true);e.removeEventListener('mousedown',null,true);e.removeEventListener('mouseup',null,true)});alert('Text selection, copy, and right-click have been enabled!')})();">Enable Right Click & Copy</a>: Enable right click and enable selection copy on pages that disable them. Work for most cases.

NEW: <a href="javascript:(function(){let u=location.href;u.includes('github.com')&&(m=u.match(/github\.com\/(.+)/))&&m[1]?location.href=%27https://deepwiki.com/%27+m[1]:alert(%27Only works on GitHub URLs%27)})();">DeepWiki</a>: Github repo to Deep Wiki, a free encyclopedia of all GitHub repos, see <a href="https://x.com/silasalberti/status/1915821553465626791">this</a>.
