---
layout: post
date: 2026-03-25 12:00:00-0400
inline: true
related_posts: false
---

<!-- 
  WRAPPER: Standardized width (548px) to hide the 2px side borders.
  Overflow: hidden crops BOTH the side borders and the bottom dead space.
-->
<div id="news-card-wrapper-mar25" style="
    max-width: 548px; 
    margin: 2rem auto; 
    background: transparent; 
    overflow: hidden; 
    border-radius: 8px;
    border: 1px solid #333;
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
">
    <div id="linkedin-container-mar25" style="position: relative; width: 552px; left: -2px;"></div>
</div>

<script>
(function() {
  const container = document.getElementById('linkedin-container-mar25');
  const wrapper = document.getElementById('news-card-wrapper-mar25');
  const isMobile = window.innerWidth <= 600;

  const iframe = document.createElement('iframe');
  // LinkedIn Share Embed Link for Mar 25 post
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:share:7441840420986224640";
  
  // Set iframe height significantly taller than the post to prevent internal scrollbars
  iframe.style.width = "552px"; 
  iframe.style.height = "1100px"; 
  iframe.style.border = "none";
  iframe.style.display = "block";
  iframe.allowFullscreen = true;

  /* 
     VISUAL HEIGHT (The "Crop"): 
     This post is text-heavy, so it needs more height than the May 16th post.
     760px removes the bottom dead space perfectly for this content.
  */
  const visibleHeight = isMobile ? 1000 : 678;
  wrapper.style.height = visibleHeight + "px";

  container.appendChild(iframe);

  function adjustAlignment() {
    if (window.innerWidth > 600) {
        // Desktop: Perfect side-crop
        container.style.left = "-2px"; 
        container.style.transform = "none";
        wrapper.style.height = visibleHeight + "px";
    } else {
        // Mobile: Fluid scaling
        const scale = wrapper.offsetWidth / 552;
        container.style.transform = `scale(${scale})`;
        container.style.transformOrigin = "top left";
        container.style.left = "0";
        // Scale the height to keep the bottom crop tight on mobile
        wrapper.style.height = (visibleHeight * scale) + "px";
    }
  }

  adjustAlignment();
  window.addEventListener('resize', adjustAlignment);
})();
</script>