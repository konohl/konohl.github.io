---
layout: page
permalink: /repositories/
title: Repositories
description: Edit the `_data/repositories.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and repositories.
nav: true
nav_order: 4
---

<style>
  /* Scoped Fe4Ni9 card — not in theme SCSS. */
  .repo.repo-fe4ni9 {
    flex: 1 1 50%;
    width: 50%;
    max-width: 50%;
  }
  .fe4ni9-card {
    display: flex;
    align-items: center;
    box-sizing: border-box;
    width: 100%;
    margin: 0;
    padding: 8px 10px;
    text-align: left;
    color: #434d58;
    background: #fff;
    border: 1px solid #e4e2e2;
    border-radius: 4.5px;
    font-family: "Roboto", "Segoe UI", Ubuntu, "Helvetica Neue", sans-serif;
    font-size: 13px;
    line-height: 1.25;
  }
  .fe4ni9-card__body {
    flex: 1 1 auto;
    min-width: 0;
  }
  .fe4ni9-card__title {
    margin: 0 0 5px;
    color: #2f80ed;
    font-size: 15px;
    font-weight: 600;
    line-height: 1.25;
  }
  .fe4ni9-card__row {
    display: flex;
    align-items: flex-start;
    margin: 2px 0;
    color: #434d58;
    font-size: 13px;
    font-weight: 700;
  }
  .fe4ni9-card__icon {
    flex: 0 0 16px;
    width: 16px;
    height: 16px;
    margin: 1px 6px 0 0;
    fill: #4c71f2;
  }
  .fe4ni9-card__label {
    flex: 0 0 auto;
    width: 7.6em;
    margin-right: 6px;
    white-space: nowrap;
  }
  .fe4ni9-card__value {
    flex: 1 1 auto;
    min-width: 0;
    white-space: nowrap;
  }
  .fe4ni9-card__value--wrap {
    white-space: normal;
  }
  .fe4ni9-nobr {
    white-space: nowrap;
  }
  .fe4ni9-card__ring {
    display: block;
    flex: 0 0 110px;
    width: 110px;
    height: 110px;
    margin-left: 6px;
    object-fit: contain;
  }
  /* Keep a white card in dark mode so the ring plot stays readable. */
  html[data-theme="dark"] .fe4ni9-card {
    background: #fff;
    border-color: #e4e2e2;
    color: #434d58;
  }
  @media (max-width: 767.98px) {
    .repo.repo-fe4ni9 {
      flex: 1 1 100%;
      width: 100%;
      max-width: 100%;
    }
    .fe4ni9-card {
      font-size: 14px;
      padding: 12px 14px;
    }
    .fe4ni9-card__title {
      font-size: 16px;
    }
    .fe4ni9-card__row {
      font-size: 14px;
      align-items: center;
    }
    .fe4ni9-card__label {
      width: 9.5em;
    }
  }
  @media (max-width: 575.98px) {
    .fe4ni9-card {
      flex-direction: column;
      align-items: stretch;
    }
    .fe4ni9-card__ring {
      flex-basis: auto;
      width: 150px;
      height: 150px;
      margin: 8px auto 0;
    }
  }
</style>

## GitHub users

{% if site.data.repositories.github_users %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
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
