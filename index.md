---
title: ControllerBuddy
layout: index
---

## Welcome

<div class="centering-container slide-in-right">
  <div class="post-it">
      <div class="pin">
      <div class="shadow"></div>
      <div class="metal"></div>
      <div class="bottom-circle"></div>
    </div>
    <div class="welcome-headline">
      Your&nbsp;gamepad, your&nbsp;cockpit&nbsp;-
      <br>
      no&nbsp;compromises!
    </div>
    <div class="welcome-text">
      Ditch the expensive gear and fly with ease.
    </div>
    <div class="welcome-text">
      Enjoy any flight&nbsp;simulator
      <br>
      with a game&nbsp;controller.
    </div>
    <div class="welcome-text">
      Take off now with <strong>ControllerBuddy</strong>!
    </div>
  </div>
</div>

## Screenshots

<div class="centering-container">
<section class="splide">
  <div class="splide__track">
    <ul class="splide__list">
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_6.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_7.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_1.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_2.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_3.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_4.png">
      </li>
      <li class="splide__slide">
        <img src="https://raw.githubusercontent.com/bwRavencl/ControllerBuddy/master/screenshot_5.png">
      </li>
    </ul>
  </div>
</section>
</div>

## Video Tutorials

Watch these videos to learn how to set up ControllerBuddy, explore its core features, and understand what makes it unique.

### Relative Axes for Smooth Throttle Controls

<center>
  <iframe class="youtube-iframe" src="https://www.youtube.com/embed/akzzSO4chZo?rel=0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

### Installation and Updating

<center>
  <iframe class="youtube-iframe" src="https://www.youtube.com/embed/AYBr_zzQCqA?rel=0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

### User Interface Tour

<center>
  <iframe class="youtube-iframe" src="https://www.youtube.com/embed/aVGV_F0h148?rel=0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

{% if site.posts.size > 0 %}
## News

{% for post in site.posts %}
  <ul class="post-list">
    <li class="post-item">
        <a class="post-link" onclick="openViewer(event, '{{ post.url | relative_url | remove_first: "/" | escape }}')">{{ post.title }}</a>
        <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
    </li>
  </ul>
{% endfor %}
{% endif %}

## FAQ

{% for item in site.data.faq %}
  <div>
    <details class="faq-details">
      <summary class="faq-summary">{{ item.title }}</summary>
      <div class="faq-content">{{ item.content | markdownify }}</div>
    </details>
  </div>
{% endfor %}

## Profiles

All profiles listed below are available in the [ControllerBuddy-Profiles repository](https://github.com/bwRavencl/ControllerBuddy-Profiles){:target="_blank"}.

These profiles are continuously updated and refined by the author to ensure the best experience.

If you use the [ControllerBuddy-Install-Script](https://github.com/bwRavencl/ControllerBuddy-Install-Script) to set up ControllerBuddy, the latest versions of these profiles will be installed automatically.

You can use the official profiles as they are, or modify them - or create your own from scratch-according to your needs.

Click the links to view a visualization of each profile:

<dialog id="viewer-dialog" class="viewer-dialog fade-out">
  <iframe id="viewer-iframe" class="viewer-iframe"></iframe>
  <button class="close-button" onclick="closeViewer()"></button>
</dialog>

<div class="profiles-container">
    {% assign sorted_files = site.static_files | sort_natural: 'basename' %}
    {% for file in sorted_files %}
      {% assign relative_path = file.path | remove_first: '/' %}
      {% assign folder = relative_path | split: '/' | first %}
      {% if folder  == 'profiles' %}
        {% assign title = relative_path | split: '/' | last | replace: '_', ' ' | split: '.html' %}
        <button onclick="openViewer(event, '{{ relative_path }}')" class="profile-item">{{ title }}</button>
      {% endif %}
    {% endfor %}
</div>

## About

[ControllerBuddy](https://github.com/bwRavencl/ControllerBuddy){:target="_blank"} is free and open-source software made with ❤ by [Matteo Hausner (bwRavencl)](https://bwRavencl.de){:target="_blank"}.
