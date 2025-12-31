---
title: "Home"
---

<!-- Inline carousel-only styles (kept here so they don't clash with grid) -->
<style>
  .carousel { position: relative; overflow: hidden; }
  .carousel-track {
    display: flex;
    gap: 1rem;
    flex-wrap: nowrap;        /* keep in one row */
    overflow-x: auto;
    scroll-behavior: smooth;
    padding-bottom: .25rem;
    -ms-overflow-style: none; /* IE/Edge */
    scrollbar-width: none;    /* Firefox */
  }
  .carousel-track::-webkit-scrollbar { display: none; } /* WebKit */
  .carousel .card { flex: 0 0 300px; } /* slide width */
</style>

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.jpeg' | relative_url }}"
         alt="Michael Shoemaker"
         class="profile-pic">

    <div class="about-text">
      <h1>Hello World! I'm Ha Do</h1>
      <p>Associate Data Analyst @ AllegiantAir </p>
      <p>I build practical, production-like data engineering systems — orchestration, storage, transformations, serving, and observability — then explain the decisions behind them.</p>
      <p><strong>Core skills:</strong> Python · SQL · Linux · Airflow · Docker · S3</p>

      <p class="social-links">
        <a href="https://www.linkedin.com/in/ha-van-do/" target="_blank" aria-label="LinkedIn">
          <i class="fa-brands fa-linkedin"></i>
        </a>
        <a href="https://github.com/HaDo1802" target="_blank" aria-label="GitHub">
          <i class="fa-brands fa-github"></i>
        </a>
        <a href="mailto:havando1802@gmail.com" target="_blank" aria-label="Email">
          <i class="fa-solid fa-envelope"></i>
        </a>

      </p>
    </div>

  </div>
</section>

<!-- ===================== Quote Section ===================== -->
<style>
  .quote-section {
    background: linear-gradient(135deg, rgba(96, 165, 250, 0.08) 0%, rgba(96, 165, 250, 0.04) 100%);
    border: 1px solid rgba(96, 165, 250, 0.2);
    border-radius: 16px;
    padding: 3rem 2rem;
    margin: 3rem 0;
    text-align: center;
    backdrop-filter: blur(10px);
  }

  .quote-text {
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--text);
    margin: 0 0 1rem;
    font-style: italic;
    line-height: 1.8;
    letter-spacing: -0.5px;
  }

  .quote-author {
    font-size: 1rem;
    color: var(--accent);
    font-weight: 600;
    margin: 0;
    letter-spacing: 0.5px;
  }

  @media (max-width: 768px) {
    .quote-section {
      padding: 2rem 1.5rem;
    }

    .quote-text {
      font-size: 1.3rem;
    }
  }
</style>

<section class="quote-section">
  <p class="quote-text">"The goal is not to read a book, the goal is to become a reader."</p>
  <p class="quote-author">— James Clear</p>
</section>

<!-- ===================== Experience ===================== -->
<style>
  .timeline {
    position: relative;
    padding: 2rem 0;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 3px;
    height: 100%;
    background: linear-gradient(180deg, var(--accent), transparent);
  }

  .timeline-item {
    margin-bottom: 2rem;
    position: relative;
  }

  .timeline-item:nth-child(odd) .timeline-content {
    margin-left: 0;
    margin-right: 52%;
    text-align: right;
  }

  .timeline-item:nth-child(even) .timeline-content {
    margin-left: 52%;
    margin-right: 0;
    text-align: left;
  }

  .timeline-marker {
    position: absolute;
    left: 50%;
    top: 0;
    transform: translateX(-50%);
    width: 16px;
    height: 16px;
    background: var(--accent);
    border: 3px solid var(--bg);
    border-radius: 50%;
    z-index: 10;
  }

  .timeline-content {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.5rem;
    box-shadow: var(--shadow);
  }

  .timeline-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 8px;
    margin-bottom: 1rem;
  }

  .timeline-image-link {
    display: block;
    cursor: pointer;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .timeline-image-link:hover {
    transform: scale(1.02);
  }

  .timeline-image-link:hover .timeline-image {
    box-shadow: 0 8px 20px rgba(96, 165, 250, 0.3);
  }

  .timeline-company {
    font-size: 1.3rem;
    font-weight: 800;
    color: var(--accent);
    margin: 0 0 0.25rem;
  }

  .timeline-position {
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--text);
    margin: 0 0 0.35rem;
  }

  .timeline-dates {
    font-size: 0.9rem;
    color: var(--muted);
    margin: 0 0 0.8rem;
  }

  .timeline-description {
    color: var(--muted);
    line-height: 1.6;
    margin: 0 0 0.8rem;
  }

  .timeline-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin: 0;
  }

  .timeline-skill {
    display: inline-block;
    background: var(--accent);
    color: white;
    padding: 0.25rem 0.6rem;
    border-radius: 4px;
    font-size: 0.8rem;
    font-weight: 600;
  }

  @media (max-width: 768px) {
    .timeline::before {
      left: 10px;
    }

    .timeline-item:nth-child(odd) .timeline-content,
    .timeline-item:nth-child(even) .timeline-content {
      margin-left: 40px;
      margin-right: 0;
      text-align: left;
    }

    .timeline-marker {
      left: 10px;
    }
  }
</style>

<section id="experience" class="section">
  <div class="section-header">
    <h2>💼 Experience</h2>
  </div>
  
  <div class="timeline">
    {% for item in site.data.experience %}
    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="timeline-content">
        {% if item.image and item.company_link %}
        <a href="{{ item.company_link }}" target="_blank" rel="noopener" class="timeline-image-link" aria-label="Visit {{ item.company }} website">
          <img src="{{ item.image | relative_url }}" alt="{{ item.company }}" class="timeline-image">
        </a>
        {% elsif item.image %}
        <img src="{{ item.image | relative_url }}" alt="{{ item.company }}" class="timeline-image">
        {% endif %}
        <h3 class="timeline-company">{{ item.company }}</h3>
        <h4 class="timeline-position">{{ item.position }}</h4>
        <p class="timeline-dates">{{ item.start_date }} – {{ item.end_date }}</p>
        <p class="timeline-description">{{ item.description }}</p>
        {% if item.skills %}
        <div class="timeline-skills">
          {% for skill in item.skills %}
          <span class="timeline-skill">{{ skill }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<!-- ===================== Projects ===================== -->
<section id="projects" class="section">
  <div class="section-header">
    <h2>🚀 Projects</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">All repos →</a>
  </div>

{% assign projects_count = site.data.projects | size %}
{% if projects_count > 4 %}

<div class="carousel">
<button class="scroll-btn left" data-target="#projects-track" aria-label="Scroll projects left">‹</button>
<div id="projects-track" class="carousel-track" role="region" aria-label="Projects list">
{% for item in site.data.projects %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
<img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
alt="{{ item.title | escape }} thumbnail"
loading="lazy"
{% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
<p class="card-text">{{ item.description }}</p>
{% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
</div>
</div>
</article>
{% endfor %}
</div>
<button class="scroll-btn right" data-target="#projects-track" aria-label="Scroll projects right">›</button>
</div>
{% else %}
<div class="gallery">
{% for item in site.data.projects %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
<img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
<p class="card-text">{{ item.description }}</p>
{% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
</div>
</div>
</article>
{% endfor %}
</div>
{% endif %}

</section>

<!-- ===================== Videos ===================== -->
<section id="videos" class="section">
  <div class="section-header">
    <h2>🎥 Videos</h2>
    <a class="view-all" href="https://youtube.com/{{ site.youtube_channel }}" target="_blank" rel="noopener">Channel →</a>
  </div>

{% assign videos_count = site.data.videos | size %}
{% if videos_count > 4 %}

<div class="carousel">
<button class="scroll-btn left" data-target="#videos-track" aria-label="Scroll videos left">‹</button>
<div id="videos-track" class="carousel-track" role="region" aria-label="Videos list">
{% for item in site.data.videos %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
<img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
alt="{{ item.title | escape }} thumbnail"
loading="lazy"
{% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
{% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
</div>
</div>
</article>
{% endfor %}
</div>
<button class="scroll-btn right" data-target="#videos-track" aria-label="Scroll videos right">›</button>
</div>
{% else %}
<div class="gallery">
{% for item in site.data.videos %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
<img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
{% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
</div>
</div>
</article>
{% endfor %}
</div>
{% endif %}

</section>

<!-- ===================== Articles ===================== -->
<section id="articles" class="section">
  <div class="section-header">
    <h2>✍️ Articles</h2>
    <a class="view-all" href="https://medium.com/@{{ site.medium_username }}" target="_blank" rel="noopener">Medium →</a>
  </div>

{% assign articles_count = site.data.articles | size %}
{% if articles_count > 4 %}

<div class="carousel">
<button class="scroll-btn left" data-target="#articles-track" aria-label="Scroll articles left">‹</button>
<div id="articles-track" class="carousel-track" role="region" aria-label="Articles list">
{% for item in site.data.articles %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
<img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
alt="{{ item.title | escape }} thumbnail"
loading="lazy"
{% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
{% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
</div>
</div>
</article>
{% endfor %}
</div>
<button class="scroll-btn right" data-target="#articles-track" aria-label="Scroll articles right">›</button>
</div>
{% else %}
<div class="gallery">
{% for item in site.data.articles %}
<article class="card">
<a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
<img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
</a>
<div class="card-body">
<h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
{% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
<div class="card-actions">
{% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
<a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
</div>
</div>
</article>
{% endfor %}
</div>
{% endif %}

</section>

<!-- Tiny helper script for arrow buttons -->
<script>
(function () {
  function init(btn) {
    var targetSel = btn.getAttribute('data-target');
    var track = document.querySelector(targetSel);
    if (!track) return;
    var step = Math.max(300, Math.floor(track.clientWidth * 0.9));

    btn.addEventListener('click', function () {
      track.scrollBy({ left: btn.classList.contains('left') ? -step : step, behavior: 'smooth' });
    });

    function update() {
      var max = track.scrollWidth - track.clientWidth - 1;
      var x = track.scrollLeft;
      var leftBtn = track.parentElement.querySelector('.scroll-btn.left');
      var rightBtn = track.parentElement.querySelector('.scroll-btn.right');
      if (leftBtn) leftBtn.disabled = x <= 0;
      if (rightBtn) rightBtn.disabled = x >= max;
    }
    track.addEventListener('scroll', update, { passive: true });
    window.addEventListener('resize', update);
    update();
  }
  document.querySelectorAll('.scroll-btn').forEach(init);
})();
</script>
