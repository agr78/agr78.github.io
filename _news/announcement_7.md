---
layout: post
date: 2026-03-25 12:00:00-0400
inline: true
related_posts: false
---
<style>
html, body { overflow-x: hidden !important; max-width: 100vw !important; }
</style>
<div id="news-card-wrapper-mar25" style="width: 100%; max-width: 548px; margin: 2rem auto; background: transparent; overflow: hidden; border-radius: 8px; border: 1px solid #333; box-shadow: 0 4px 12px rgba(0,0,0,0.3); box-sizing: border-box; clear: both;"></div>
<script>
(function() {
  const wrapper = document.getElementById('news-card-wrapper-mar25');
  const container = document.createElement('div');
  container.style.position = 'relative';
  container.style.overflow = 'hidden';
  wrapper.appendChild(container);
  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:share:7441840420986224640";
  iframe.setAttribute('scrolling', 'no');
  iframe.style.width = "552px";
  iframe.style.height = "1100px";
  iframe.style.border = "none";
  iframe.style.display = "block";
  iframe.style.transformOrigin = "top left";
  container.appendChild(iframe);
  const IFRAME_W = 552;
  const IFRAME_H = 1100;
  const DESKTOP_CROP_H = 678;

  // Detect real mobile Safari (iOS WebKit), excluding Chrome/Firefox on iOS
  // which report Safari-like UA strings but identify via CriOS/FxiOS.
  const ua = navigator.userAgent;
  const isIOS = /iPad|iPhone|iPod/.test(ua) && !window.MSStream;
  const isChromeOrFirefoxOniOS = /CriOS|FxiOS/.test(ua);
  const isMobileSafari = isIOS && !isChromeOrFirefoxOniOS;

  const MOBILE_CROP_RATIO = isMobileSafari ? 0.69 : 0.615;

  function adjust7() {
    const ww = wrapper.clientWidth;
    if (window.innerWidth > 600) {
      iframe.style.transform = "none";
      container.style.width = "552px";
      container.style.height = IFRAME_H + "px";
      container.style.left = "-2px";
      wrapper.style.height = DESKTOP_CROP_H + "px";
    } else {
      const scale = ww / IFRAME_W;
      const scaledFullH = Math.round(IFRAME_H * scale);
      const scaledCropH = Math.round(IFRAME_H * MOBILE_CROP_RATIO * scale);
      iframe.style.transform = "scale(" + scale + ")";
      container.style.width = ww + "px";
      container.style.height = scaledFullH + "px";
      container.style.left = "0";
      wrapper.style.height = scaledCropH + "px";
    }
  }
  window.addEventListener('load', adjust7);
  window.addEventListener('resize', adjust7);
  adjust7();
})();
</script>