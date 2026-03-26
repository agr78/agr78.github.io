---
layout: post
date: 2025-11-20 16:45:00-0400 
inline: true
related_posts: false
---
<!--- <blockquote class="twitter-tweet" data-theme="dark"><p lang="en" dir="ltr">On today&#39;s OpenCV live stream we&#39;re exploring ML and deep learning in CT, PET, and MRI, covering reconstruction, detection, and segmentation, while highlighting model interpretability, strategies for handling label noise, and methods for reducing bias in medical imaging workflows <a href="https://t.co/4cCxM5qCw4">pic.twitter.com/4cCxM5qCw4</a></p>&mdash; OpenCV Live (@opencvlive) <a href="https://twitter.com/opencvlive/status/1991535528739762456?ref_src=twsrc%5Etfw">November 20, 2025</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
---> 
<!--- <div style="max-width: 547px; margin: 2rem auto; text-align: center;">
  <blockquote class="twitter-tweet" data-theme="dark">
    <p lang="en" dir="ltr">
      On today's OpenCV live stream we're exploring ML and deep learning in CT, PET, and MRI, 
      covering reconstruction, detection, and segmentation, while highlighting model interpretability, 
      strategies for handling label noise, and methods for reducing bias in medical imaging workflows 
      <a href="https://t.co/4cCxM5qCw4">pic.twitter.com/4cCxM5qCw4</a>
    </p>
    &mdash; OpenCV Live (@opencvlive) 
    <a href="https://twitter.com/opencvlive/status/1991535528739762456?ref_src=twsrc%5Etfw">November 20, 2025</a>
  </blockquote>
</div>

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
--->
<div id="tweet-container" style="max-width: 547px; margin: 2rem auto; min-height: 450px;">
  </div>

<script>
  function updateTwitterTheme() {
    const html = document.documentElement;
    const body = document.body;
    
    // Check all common ways Jekyll themes signal Dark Mode
    const isDark = html.getAttribute('data-theme') === 'dark' || 
                   html.classList.contains('dark') || 
                   body.classList.contains('dark-mode') ||
                   window.matchMedia('(prefers-color-scheme: dark)').matches;

    const container = document.getElementById('tweet-container');
    
    // Clear and Re-inject the blockquote with the correct theme
    container.innerHTML = `
      <blockquote class="twitter-tweet" data-theme="${isDark ? 'dark' : 'light'}">
        <a href="https://twitter.com/opencvlive/status/1991535528739762456"></a>
      </blockquote>`;

    // Re-run the Twitter widget factory
    if (window.twttr && window.twttr.widgets) {
      window.twttr.widgets.load(container);
    } else {
      const script = document.createElement('script');
      script.src = "https://platform.twitter.com/widgets.js";
      document.head.appendChild(script);
    }
  }

  // Run on initial load
  setTimeout(updateTwitterTheme, 500); 

  // Toggle
  const observer = new MutationObserver(updateTwitterTheme);
  observer.observe(document.documentElement, { attributes: true });
  observer.observe(document.body, { attributes: true });
</script>
