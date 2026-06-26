---
layout: post
date: 2026-05-16 12:00:00-0400
inline: true
related_posts: false
---

<div id="news-card-wrapper-8" style="
    max-width: 548px; 
    margin: 2rem auto; 
    background: transparent; 
    overflow: hidden; 
    border-radius: 8px;
    border: 1px solid #333;
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
">
    <div id="linkedin-container-8" style="position: relative; width: 552px; left: -2px;"></div>
</div>

<script>
(function() {
  const container = document.getElementById('linkedin-container-8');
  const wrapper = document.getElementById('news-card-wrapper-8');
  const isMobile = window.innerWidth <= 600;

  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:activity:7458501029249175552";
  
  // Keep the iframe's internal width/height fixed to prevent scrollbars
  iframe.style.width = "552px"; 
  iframe.style.height = "800px"; 
  iframe.style.display = "block";
  
  /* 
     VISUAL HEIGHT
  */
  const visibleHeight = isMobile ? 750 : 645;
  wrapper.style.height = visibleHeight + "px";

  container.appendChild(iframe);

  function adjustAlignment() {
    if (window.innerWidth > 600) {
        // Restore the crop
        container.style.left = "-4px"; 
        container.style.transform = "none";
        wrapper.style.height = visibleHeight + "px";
    } else {
        // Mobile fluid scaling
        const scale = wrapper.offsetWidth / 552;
        container.style.transform = `scale(${scale})`;
        container.style.transformOrigin = "top left";
        container.style.left = "0";
        // Scale the height perfectly to match
        wrapper.style.height = (visibleHeight * scale) + "px";
    }
  }

  adjustAlignment();
  window.addEventListener('resize', adjustAlignment);
})();
</script>