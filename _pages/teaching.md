---
layout: page
permalink: /teaching/
title: teaching
description: Courses I teach at the University of Hong Kong in Earth and Planetary Sciences and in the Common Core curriculum.
nav: true
nav_order: 6
---

<style>
.teaching-soundtrack {
  position: absolute;
  width: 1px;
  height: 1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  opacity: 0;
  pointer-events: none;
}
.teaching-soundtrack figure {
  margin: 0;
}
</style>

<div class="teaching-soundtrack" aria-hidden="true">
{% include audio.liquid path="assets/audio/original-composition.mp3" autoplay=true %}
</div>
<script>
(function () {
  var audio = document.querySelector(".teaching-soundtrack audio");
  if (!audio) return;
  var tryPlay = function () { return audio.play(); };
  var p = tryPlay();
  if (p && p.catch) {
    p.catch(function () {
      var start = function () {
        tryPlay();
        document.removeEventListener("click", start);
        document.removeEventListener("keydown", start);
        document.removeEventListener("touchstart", start);
      };
      document.addEventListener("click", start);
      document.addEventListener("keydown", start);
      document.addEventListener("touchstart", start);
    });
  }
})();
</script>

{% include courses.liquid %}
