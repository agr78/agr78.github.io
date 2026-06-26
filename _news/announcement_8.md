---
layout: post
date: 2026-05-16 12:00:00-0400
inline: true
related_posts: false
---
<style>
html, body { overflow-x: hidden !important; max-width: 100vw !important; }
</style>
<div id="news-card-wrapper-8" style="width: 100%; max-width: 548px; margin: 2rem auto; background: transparent; overflow: hidden; border-radius: 8px; border: 1px solid #333; box-shadow: 0 4px 12px rgba(0,0,0,0.3); box-sizing: border-box; clear: both;"></div>
<script>
(function() {
  const wrapper = document.getElementById('news-card-wrapper-8');
  const container = document.createElement('div');
  container.style.position = 'relative';
  container.style.overflow = 'hidden';
  wrapper.appendChild(container);

  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:activity:7458501029249175552";
  iframe.setAttribute('scrolling', 'no');
  iframe.style.width = "552px";
  iframe.style.height = "800px";
  iframe.style.border = "none";
  iframe.style.display = "block";
  iframe.style.transformOrigin = "top left";
  container.appendChild(iframe);

  const IFRAME_H = 800;
  const DESKTOP_CROP_H = 645;

  function adjust8() {
    const ww = wrapper.clientWidth;
    if (window.innerWidth > 600) {
      iframe.style.transform = "none";
      container.style.transform = "none";
      container.style.width = "552px";
      container.style.height = IFRAME_H + "px";
      container.style.left = "0px";
      container.style.right = "-8px";
      wrapper.style.height = DESKTOP_CROP_H + "px";
    } else {
      const scale = ww / 552;
      const scaledCropH = Math.round(DESKTOP_CROP_H * scale);
      const scaledFullH = Math.round(IFRAME_H * scale);
      const scaledNudge = Math.round(2 * scale);
      // Scale the iframe, then shift the container right by the scaled nudge
      iframe.style.transform = "scale(" + scale + ")";
      container.style.transform = "translateX(" + scaledNudge + "px)";
      container.style.width = ww + "px";
      container.style.height = scaledFullH + "px";
      container.style.left = "0";
      container.style.right = "0";
      wrapper.style.height = scaledCropH + "px";
    }
  }

  window.addEventListener('load', adjust8);
  window.addEventListener('resize', adjust8);
  adjust8();
})();
</script>