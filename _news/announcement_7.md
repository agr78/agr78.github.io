---
layout: post
date: 2026-03-25 12:00:00-0400
inline: true
related_posts: false
---

<!--- <div style="width:100%; margin:2rem 0; padding:0;">
  <div style="max-width:547px; margin:0 auto; position:relative; padding-bottom:100%; height:0; overflow:hidden; border:0; outline:none; transform: translateX(-80.5px);">
    <iframe
      src="https://www.linkedin.com/embed/feed/update/urn:li:share:7441840420986224640"
      style="position:absolute; top:0; left:0; width:100%; height:100%; border:0; outline:none;"
      allowfullscreen
      title="LinkedIn post">
    </iframe>
  </div>
</div> --->
<div id="linkedin-container" style="max-width:547px; margin:2rem auto;"></div>

<script>
const container = document.getElementById('linkedin-container');
const isMobile = window.innerWidth <= 600;

const iframe = document.createElement('iframe');
iframe.src = "https://www.linkedin.com/embed/feed/update/urn:li:share:7441840420986224640";
iframe.style.width = "100%";
iframe.style.border = "0";
iframe.style.display = "block";
iframe.allowFullscreen = true;

// adjust height for mobile vs desktop
iframe.style.height = isMobile ? "900px" : "700px";
if (!isMobile) {
  // compute left offset dynamically
  const containerWidth = container.offsetWidth; // outer container width
  const postWidth = 547; // LinkedIn internal post width
  const leftOffset = (containerWidth - postWidth) / 2 * -1; // negative shift to center

  iframe.style.position = "relative";
  iframe.style.left = `${leftOffset}px`;
}

// append iframe
container.appendChild(iframe);

// optional: recompute offset on resize
window.addEventListener('resize', () => {
  if (!isMobile) {
    const containerWidth = container.offsetWidth;
    const leftOffset = (containerWidth - 547) / 2 * -1;
    iframe.style.left = `${leftOffset}px`;
  }
});
</script>
