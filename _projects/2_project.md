---
layout: page
title: GRF17308120
description: <b>2023/2024 | Metals in Ore Nanodroplets</b> | Ab Initio MD and IR Spectroscopic Characterization of Hydrated Gold and Copper Clusters      
img: assets/img/1C_bw.jpg
importance: 2
category: work
giscus_comments: true
---

<div style="text-align: justify; font-size: 16px; margin-bottom: 1em;"><b>Project title: "Metals in Ore Nanodroplets: Ab Initio Molecular Dynamics and IR Spectroscopic Characterization of Hydrated Gold and Copper Clusters".</b> This research aims to investigate water nanodroplet structures and metal-enriched nanodroplets, focusing on their stabilities, high-temperature free energies, and IR spectral features, by using computational and experimental techniques, including CPMD simulations, IRMPD spectroscopy, and mass spectrometry for Cu, Ag, and Au ions and their complexes. </div>


    ---
    Project duration:        15/10/2020-14/04/2024
    Project Status:          On-going
    Funding Scheme:          GRF (General Research Fund)
    Research Field:          Earth Sciences, Chemical Sciences
    Keywords:                IR spectroscopy, metal clusters, Ore vapor, water nanodroplets
    Total Fund Awarded:      $441,074
    HKU Project Code:        17308120
    ---

<div class="row justify-content-sm-center">
    <div class="col-sm-12 mt-3 mt-md-0; margin-bottom: 3em;">
        {% include figure.liquid path="assets/img/17308120/17308120_I.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 3em;">
 <b>Fig.1</b> OPO/OPA IR laser and 7T ESI/FT-ICR mass spectrometer setup, featuring pulsed Nd:YAG laser, wave-tunable IR-OPO/OPA with a range of 800-4500 cm<sup>-1</sup>, FT-ICR MS ion transfer stage, an AgGaSe<sub>2</sub> wavelength extension to 625 cm<sup>-1</sup>, and 7T Bruker magnet</div>

<div class="row">

    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets//img/17308120/17308120_C.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/17308120/17308120_D.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 3em;">
    <b>Fig.2</b> Snapshots from BLYP Car-Parrinello MD simulations at 450K for AuCl and Au<sub>2</sub>Cl<sub>2</sub> dissolution in 50-water-molecule nanodroplets, illustrating various solvation states and surface interactions, including undissociated AuCl, deprotonated surface complexes, and dissociated surface species.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/17308120/17308120_H.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div style="text-align: justify; font-size: 14px; margin-bottom: 2em;">
    <b>Fig.3</b> CCSD(T)/aVDZ level of theory optimized 'structures' of [AuCl<sub>2</sub>]<sup>+</sup>(H<sub>2</sub>O)n with n=1-3; relative energies with VPT2 ZPE corrections given in brackets below; green = Cl, yellow = Au.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
