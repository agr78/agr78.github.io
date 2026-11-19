---
layout: post
date: 2026-11-18 12:00:00-0400
inline: true
related_posts: false
---
<style>
html, body { overflow-x: hidden !important; max-width: 100vw !important; }
/* LinkedIn renders this embed light or dark itself, inside the iframe.
   Which one varies by browser (dark in Safari, light in Brave on the
   same device) and we can't drive it from here. So keep the chrome on
   the site's own theme tokens: the frame always matches the page. */
#news-card-wrapper-10 {
  border: 1px solid var(--global-divider-color, #333);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}
html[data-theme="dark"] #news-card-wrapper-10 {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
}</style>
<div id="news-card-wrapper-10" style="width: 100%; max-width: 548px; margin: 2rem auto; background: transparent; overflow: hidden; border-radius: 8px; box-sizing: border-box; clear: both;"></div>
<script>
(function() {
  const wrapper = document.getElementById('news-card-wrapper-10');
  const container = document.createElement('div');
  container.style.position = 'relative';
  container.style.overflow = 'hidden';
  wrapper.appendChild(container);
  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:share:7528948356648226816";
  iframe.setAttribute('scrolling', 'no');
  iframe.style.width = "552px";
  iframe.style.height = "1000px";
  iframe.style.border = "none";
  iframe.style.display = "block";
  iframe.style.position = "absolute";
  iframe.style.top = "0";
  iframe.style.left = "0";
  iframe.style.transformOrigin = "top left";
  container.appendChild(iframe);
  const IFRAME_W = 552;
  const IFRAME_H = 1000;
  const DESKTOP_CROP_H = 811;
  const RIGHT_TRIM_PX = 4;

  const ua = navigator.userAgent;
  const isIOS = /iPad|iPhone|iPod/.test(ua) && !window.MSStream;
  // Every browser on iOS is WebKit (Apple requires it), so Firefox and
  // Chrome there lay out exactly like Safari and need the same ratio.
  const isIOSWebKit = isIOS;

  const MOBILE_CROP_RATIO = isIOSWebKit ? 0.92 : 0.812;

  function adjust10() {
    const ww = wrapper.clientWidth;
    if (window.innerWidth > 600) {
      iframe.style.transform = "none";
      container.style.width = (IFRAME_W - RIGHT_TRIM_PX) + "px";
      container.style.height = IFRAME_H + "px";
      container.style.left = "0px";
      wrapper.style.height = DESKTOP_CROP_H + "px";
    } else {
      const scale = ww / (IFRAME_W - RIGHT_TRIM_PX);
      const scaledFullH = Math.round(IFRAME_H * scale);
      const scaledCropH = Math.round(IFRAME_H * MOBILE_CROP_RATIO * scale);
      iframe.style.transform = "scale(" + scale + ")";
      container.style.width = ww + "px";
      container.style.height = scaledFullH + "px";
      container.style.left = "0";
      wrapper.style.height = scaledCropH + "px";
    }
  }
  window.addEventListener('load', adjust10);
  window.addEventListener('resize', adjust10);
  adjust10();
})();
</script>