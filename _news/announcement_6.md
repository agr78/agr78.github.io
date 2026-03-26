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
<div id="tweet-container" style="max-width: 547px; margin: 2rem auto; min-height: 400px;">
  <blockquote class="twitter-tweet">
    <a href="https://twitter.com/opencvlive/status/1991535528739762456"></a>
  </blockquote>
</div>

<script>
  function loadTwitter() {
    // 1. Check if the site is currently in Dark Mode
    // We check the 'data-theme' attribute or the system preference
    const isDark = document.documentElement.getAttribute('data-theme') === 'dark' || 
                   window.matchMedia('(prefers-color-scheme: dark)').matches;

    // 2. Clear the container to prevent double-loading
    const container = document.getElementById('tweet-container');
    container.innerHTML = `<blockquote class="twitter-tweet" data-theme="${isDark ? 'dark' : 'light'}">
      <a href="https://twitter.com/opencvlive/status/1991535528739762456"></a>
    </blockquote>`;

    // 3. Load/Reload the Twitter widget script
    const script = document.createElement('script');
    script.src = "https://platform.twitter.com/widgets.js";
    script.async = true;
    document.body.appendChild(script);
  }

  // Run on page load
  loadTwitter();

  // Run whenever the user toggles the theme button on your site
  const observer = new MutationObserver((mutations) => {
    mutations.forEach((mutation) => {
      if (mutation.attributeName === 'data-theme') loadTwitter();
    });
  });
  observer.observe(document.documentElement, { attributes: true });
</script>
