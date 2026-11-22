---
layout: page
permalink: /repositories/
title: Repositories
description: Molecular cluster structures and energies from our ongoing research, openly available.
nav: true
nav_order: 4
---

<style>
  /* Scoped Fe4Ni9 card — not in theme SCSS. */
  .repositories-users {
    align-items: stretch !important;
  }
  .repo.repo-fe4ni9 {
    flex: 1 1 50%;
    width: 50%;
    max-width: 50%;
    display: flex;
    align-items: stretch;
  }
  .fe4ni9-card {
    display: flex;
    align-items: center;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 8px 10px 8px 12px;
    text-align: left;
    color: #434d58;
    background: #fff;
    border: 1px solid #e4e2e2;
    border-radius: 4.5px;
    font-family: "Segoe UI", Ubuntu, "Helvetica Neue", Roboto, sans-serif;
    font-size: 11.5px;
    font-weight: 600;
    line-height: 1.3;
  }
  @media (min-width: 768px) {
    .fe4ni9-card {
      aspect-ratio: 467 / 195;
      height: auto;
    }
  }
  .fe4ni9-card__body {
    flex: 1 1 auto;
    min-width: 0;
    display: grid;
    grid-template-columns: 14px max-content 1fr;
    column-gap: 6px;
    row-gap: 2px;
    align-items: center;
  }
  .fe4ni9-card__title {
    grid-column: 1 / -1;
    margin: 0 0 4px;
    color: #2f80ed;
    font-size: 12.5px;
    font-weight: 600;
    line-height: 1.2;
    white-space: nowrap;
  }
  .fe4ni9-card__row {
    display: contents;
    color: #434d58;
    font-size: 11.5px;
    font-weight: 600;
  }
  .fe4ni9-card__icon {
    width: 14px;
    height: 14px;
    fill: #4c71f2;
  }
  .fe4ni9-card__label,
  .fe4ni9-card__value {
    white-space: nowrap;
    color: #434d58;
    font-size: 11.5px;
    font-weight: 600;
  }
  .fe4ni9-card__value a {
    color: inherit;
    text-decoration: none;
    font-weight: 600;
  }
  .fe4ni9-card__value a:hover,
  .fe4ni9-card__value a:focus {
    text-decoration: underline;
  }
  .fe4ni9-card__ring {
    display: block;
    flex: 0 0 auto;
    width: 108px;
    height: 108px;
    margin-left: 8px;
    object-fit: contain;
  }
  /* Dark mode: match the github-readme-stats "dark" card beside it. */
  html[data-theme="dark"] .fe4ni9-card {
    background: #151515;
    border-color: #e4e2e2;
    color: #9f9f9f;
  }
  html[data-theme="dark"] .fe4ni9-card__title {
    color: #fff;
  }
  html[data-theme="dark"] .fe4ni9-card__icon {
    fill: #79ff97;
  }
  html[data-theme="dark"] .fe4ni9-card__row,
  html[data-theme="dark"] .fe4ni9-card__label,
  html[data-theme="dark"] .fe4ni9-card__value {
    color: #9f9f9f;
  }
  html[data-theme="dark"] .fe4ni9-card__value a {
    color: inherit;
  }
  @media (max-width: 767.98px) {
    .repositories-users {
      align-items: center !important;
    }
    .repo.repo-fe4ni9 {
      flex: 1 1 100%;
      width: 100%;
      max-width: 100%;
    }
    .fe4ni9-card {
      height: auto;
    }
  }
  @media (max-width: 575.98px) {
    .fe4ni9-card {
      flex-direction: column;
      align-items: stretch;
    }
    .fe4ni9-card__title {
      white-space: normal;
    }
    .fe4ni9-card__ring {
      width: 110px;
      height: 110px;
      margin: 6px auto 0;
    }
  }
</style>

{% if site.data.repositories.github_users %}

<div class="repositories repositories-users d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/fe4ni9_card.liquid %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

---

{% endfor %}
{% endif %}
{% endif %}

## GitHub Repositories

{% if site.data.repositories.github_repos %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
