---
layout: post
date: 2026-07-09 12:00:00-0400
inline: true
related_posts: false
---
<style>
html, body { overflow-x: hidden !important; max-width: 100vw !important; }
/* LinkedIn renders this embed light or dark itself, inside the iframe.
   Which one varies by browser (dark in Safari, light in Brave on the
   same device) and we can't drive it from here. So keep the chrome on
   the site's own theme tokens: the frame always matches the page. */
#news-card-wrapper-9 {
  border: 1px solid var(--global-divider-color, #333);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}
html[data-theme="dark"] #news-card-wrapper-9 {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
}
</style>
<div id="news-card-wrapper-9" style="width: 100%; max-width: 548px; margin: 2rem auto; background: transparent; overflow: hidden; border-radius: 8px; box-sizing: border-box; clear: both;"></div>
<script>
(function() {
  const wrapper = document.getElementById('news-card-wrapper-9');
  const container = document.createElement('div');
  container.style.position = 'relative';
  container.style.overflow = 'hidden';
  wrapper.appendChild(container);
  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:share:7480949423028719616";
  iframe.setAttribute('scrolling', 'no');
  iframe.style.width = "504px";
  iframe.style.height = "620px";
  iframe.style.border = "none";
  iframe.style.display = "block";
  iframe.style.position = "absolute";
  iframe.style.top = "0";
  iframe.style.left = "0";
  iframe.style.transformOrigin = "top left";
  container.appendChild(iframe);
  const IFRAME_W = 504;
  const IFRAME_H = 620; // was 493: too short for iOS to lay the card out in full
  const RIGHT_TRIM_PX = 4;
  const DESKTOP_TARGET_W = 548; // matches card 8's rendered width
  // Card height in iframe px. Absolute rather than a ratio of IFRAME_H so
  // the frame can be made taller without moving the crop.
  const DESKTOP_CONTENT_H = 468;
  const ua = navigator.userAgent;
  const isIOS = /iPad|iPhone|iPod/.test(ua) && !window.MSStream;
  // Every browser on iOS is WebKit (Apple requires it), so Firefox and
  // Chrome there lay out exactly like Safari and need the same ratio.
  const isIOSWebKit = isIOS;
  // iOS lays the card out ~18% taller, in line with cards 7, 8 and 10.
  const MOBILE_CONTENT_H = isIOSWebKit ? 552 : 483;
  function adjust9() {
    const ww = wrapper.clientWidth;
    if (window.innerWidth > 600) {
      const scale = DESKTOP_TARGET_W / (IFRAME_W - RIGHT_TRIM_PX);
      const scaledFullH = Math.round(IFRAME_H * scale);
      const scaledCropH = Math.round(DESKTOP_CONTENT_H * scale);
      iframe.style.transform = "scale(" + scale + ")";
      container.style.width = DESKTOP_TARGET_W + "px";
      container.style.height = scaledFullH + "px";
      container.style.left = "0px";
      wrapper.style.height = scaledCropH + "px";
    } else {
      const scale = ww / (IFRAME_W - RIGHT_TRIM_PX);
      const scaledFullH = Math.round(IFRAME_H * scale);
      const scaledCropH = Math.round(MOBILE_CONTENT_H * scale);
      iframe.style.transform = "scale(" + scale + ")";
      container.style.width = ww + "px";
      container.style.height = scaledFullH + "px";
      container.style.left = "0";
      wrapper.style.height = scaledCropH + "px";
    }
  }
  window.addEventListener('load', adjust9);
  window.addEventListener('resize', adjust9);
  adjust9();
})();
</script>