---
layout: post
date: 2026-05-16 12:00:00-0400
inline: true
related_posts: false
---

<div id="news-card-wrapper-8" style="
    width: 95%; 
    max-width: 548px; 
    margin: 2rem auto; 
    background: transparent; 
    overflow: hidden; 
    border-radius: 8px;
    border: 1px solid #333;
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
    box-sizing: border-box;
    clear: both;
">
    <!-- The container width stays fixed so the LinkedIn layout doesn't break, we scale it instead -->
    <div id="linkedin-container-8" style="position: relative; width: 552px; left: 0;"></div>
</div>

<script>
(function() {
  const container = document.getElementById('linkedin-container-8');
  const wrapper = document.getElementById('news-card-wrapper-8');
  const isMobile = () => window.innerWidth <= 600;

  const iframe = document.createElement('iframe');
  iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:activity:7458501029249175552";
  
  // Fixed internal width to maintain the desktop crop/layout
  iframe.style.width = "552px"; 
  iframe.style.height = "800px"; 
  iframe.style.display = "block";
  iframe.style.border = "none";
  
  const baseVisibleHeight = 645; // Your desktop height

  container.appendChild(iframe);

  function adjustAlignment() {
    const wrapperWidth = wrapper.offsetWidth;
    
    if (window.innerWidth > 600) {
        // Desktop: Apply your specific crop offset
        container.style.transform = "none";
        container.style.left = "-8px"; 
        wrapper.style.height = baseVisibleHeight + "px";
    } else {
        // Mobile: Calculate scale based on the actual width of the phone screen
        // We subtract 2px to account for the wrapper borders
        const scale = (wrapperWidth - 2) / 552;
        
        container.style.transform = `scale(${scale})`;
        container.style.transformOrigin = "top left";
        container.style.left = "0";
        
        // Scale the wrapper height proportionally so no gap appears below
        wrapper.style.height = (800 * scale) + "px";
    }
  }

  // Run on load
  iframe.onload = adjustAlignment;
  adjustAlignment();
  
  // Run on resize
  window.addEventListener('resize', adjustAlignment);
})();
</script>