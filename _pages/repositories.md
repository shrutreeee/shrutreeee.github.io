---
layout: page
title: playground
permalink: /playground/
description: little daily games I play (instead of working)
nav: true
nav_order: 4

# Each game is one card. To use your own thumbnail, upload an image to
# assets/img/playground/ and remove the # in front of that game's image line.
# Without an image, the emoji is shown instead.
games:
  - name: Wordle
    url: https://www.nytimes.com/games/wordle/index.html
    emoji: 🟩
    # image: /assets/img/playground/wordle.png
  - name: Connections
    url: https://www.nytimes.com/games/connections
    emoji: 🟪
    # image: /assets/img/playground/connections.png
  - name: Crossword
    url: https://www.nytimes.com/crosswords
    emoji: ✏️
    # image: /assets/img/playground/crossword.png
  - name: Spelling Bee
    url: https://www.nytimes.com/puzzles/spelling-bee
    emoji: 🐝
    # image: /assets/img/playground/spelling-bee.png
  - name: Minute Cryptic
    url: https://www.minutecryptic.com
    emoji: 🕵️
    # image: /assets/img/playground/minute-cryptic.png
---

<style>
.playground-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 1.25rem;
  margin-top: 1.5rem;
}
.playground-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.6rem;
  padding: 1.1rem 0.75rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 0.75rem;
  text-decoration: none !important;
  color: var(--global-text-color) !important;
  transition: transform 0.15s ease, border-color 0.15s ease;
}
.playground-card:hover {
  transform: translateY(-3px);
  border-color: var(--global-theme-color);
}
.playground-thumb {
  width: 72px;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.6rem;
}
.playground-thumb img {
  max-width: 100%;
  max-height: 100%;
  border-radius: 0.6rem;
}
.playground-name {
  font-weight: 500;
  text-align: center;
}
</style>

<div class="playground-grid">
{% for game in page.games %}
<a class="playground-card" href="{{ game.url }}" target="_blank" rel="noopener noreferrer">
<div class="playground-thumb">
{% if game.image %}<img src="{{ game.image | relative_url }}" alt="{{ game.name }}">{% else %}<span>{{ game.emoji }}</span>{% endif %}
</div>
<span class="playground-name">{{ game.name }}</span>
</a>
{% endfor %}
</div>
