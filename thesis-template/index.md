---
layout: default
title: Experiments
---

<section class="hero" aria-labelledby="page-title">
  <p class="eyebrow">THESIS / VISUAL LABORATORY <span>2026</span></p>
  <h1 id="page-title">Small experiments,<br><em>made legible.</em></h1>
  <p class="lede">A field guide to the moving images, instruments, and observations that shape this thesis. Browse each study at your own pace.</p>
  <div class="hero-meta"><span><strong>03</strong> documented studies</span><span><strong>01</strong> recurring question</span><span>Updated September 2026</span></div>
</section>

<section class="intro-strip" aria-label="Reading guide"><span class="strip-label">HOW TO READ</span><p>Start with the description, then use the controls to isolate a moment or visual layer. The numbered markers are prompts, not conclusions.</p></section>

<main class="experiment-grid" aria-label="Experiments">
  {% for experiment in site.data.experiments %}
  <article class="experiment-card" data-experiment="{{ experiment.number }}">
    <div class="card-heading"><span class="index">{{ experiment.number }}</span><span class="tag">{{ experiment.tag }}</span><span class="year">{{ experiment.year }}</span></div>
    <h2>{{ experiment.title }}</h2>
    <p class="description">{{ experiment.description }}</p>
    <div class="media-frame" data-media>
      <img class="experiment-gif" src="{{ '/assets/img/' | append: experiment.gif | relative_url }}" data-gif-src="{{ '/assets/img/' | append: experiment.gif | relative_url }}" data-poster-src="{{ '/assets/img/' | append: experiment.poster | relative_url }}" alt="{{ experiment.alt }}">
      <div class="marker marker-one" aria-hidden="true">01</div><div class="marker marker-two" aria-hidden="true">02</div>
      <div class="media-caption"><span>LOOP / {{ experiment.loop }}</span><span class="status">PLAYING</span></div>
    </div>
    <div class="knob-panel" data-knob-panel>
      <div class="knob-row"><label for="focus-{{ experiment.number }}">Focus window</label><output id="focus-output-{{ experiment.number }}">{{ experiment.focus_default }}</output></div>
      <input id="focus-{{ experiment.number }}" type="range" min="0" max="100" value="{{ experiment.focus_value }}" aria-label="Choose focus window for {{ experiment.title }}" data-focus-range>
      <div class="range-labels"><span>context</span><span>transition</span><span>detail</span></div>
      <button class="play-toggle" type="button" data-gif-toggle aria-pressed="false"><span class="play-icon">Ⅱ</span> Pause loop</button>
    </div>
    <div class="observation"><span class="obs-label">VISIBLE IN THE GIF</span><p>{{ experiment.visible }}</p></div>
  </article>
  {% endfor %}
</main>

<section class="closing-note"><p class="eyebrow">A NOTE ON METHOD</p><p>These loops are deliberately small: enough motion to reveal a behavior, enough stillness to invite looking. Replace the sample studies with your own observations in <code>_data/experiments.yml</code>.</p></section>
