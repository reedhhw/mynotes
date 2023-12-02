---
date: 2023-12-02T11:42
---

# UserScriptJS

disable-video-autoplay.user.js
// ==UserScript==
// @name Disable Video AutoPlay
// @icon https://hermit.chimbori.com/config/userscripts/play-box-lock-outline.svg
// @description Turn off AutoPlay for all HTML5 videos on the page
// @priority 100
// ==/UserScript==


(function() {
  var videoTags = document.querySelectorAll('video');
  for (var i = videoTags.length - 1; i >= 0; i--) {
    var videoTag = videoTags[i];
    console.log('Disable Video AutoPlay:', videoTag);
    videoTag.autoplay = false;
    videoTag.pause();
  }
})();


enable-text-copying.user.js
// ==UserScript==
// @name Force Enable Text Copying
// @icon https://hermit.chimbori.com/config/userscripts/content-copy.svg
// @description Force-enable text copying, even on sites that disable it.
// @priority 100
// ==/UserScript==


(function() {
  document.querySelectorAll("*").forEach(function(el) {
    el.style.webkitUserSelect = 'text';
  });
})();

enable-zoom.user.js
// ==UserScript==
// @name Force Enable Zoom
// @icon https://hermit.chimbori.com/config/userscripts/magnify-plus.svg
// @description Force-enable zooming on a site, even on sites that disable it.
// @priority 100
// ==/UserScript==
(function() {
  // Disallowing users from changing zoom levels is a user-hostile move.
  var scalableMetaViewport = 'width=device-width, initial-scale=1';
  var metaTag = document.querySelector('meta[name=viewport]');
  if (metaTag != null) {
    metaTag.content = scalableMetaViewport;
  } else {
    var metaTag = document.createElement('meta');
    metaTag.name = 'viewport';
    metaTag.content = scalableMetaViewport;
    document.getElementsByTagName('head')[0].appendChild(metaTag);
  }
  // Force the page to pick up the changes.
  document.body.style.opacity = .9999;
  setTimeout(function(){
    document.body.style.opacity = 1;
  }, 1);
})();


Write your Markdown content here. Read [neuron documentation](https://neuron.zettel.page/2011404.html) for syntax help.

