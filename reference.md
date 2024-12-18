---
layout: reference
title: "References"
---

## More info:

### `brilcalc`
* [BRIL Work Suite - `brilcalc` official documentation](https://cmslumi.web.cern.ch/)
* [`brilcalc` Quick Start](https://twiki.cern.ch/twiki/bin/viewauth/CMS/BrilcalcQuickStart)

### Articles
* [The Installation of the BRIL Luminometers: Preparing for a bright Run 3](https://cms.cern/news/installation-bril-luminometers-preparing-bright-run-3) (2021) (A.Delannoy)
* [Illuminating! Counting LHC Collisions with CMS](https://cms.cern/news/illuminating-counting-lhc-collisions-cms) (2021) (G.Krintiras)
* [Why precision luminosity measurements matter](https://home.cern/news/news/physics/why-precision-luminosity-measurements-matter) (2021) (P.Traczyk)
* [What is Luminosity (Symmetry Magazine)](https://www.symmetrymagazine.org/article/what-is-luminosity) (2021) (S.Charley)
* [Planning For Years of Luminosity Measurements with BRIL](https://cms.cern/news/planning-years-luminosity-measurements-bril) (2020) (P.Lujan)

### Papers
* [Luminosity measurement in proton-proton collisions at 13.6 TeV in 2022 at CMS](https://cds.cern.ch/record/2890833/) (2024) (CMS Collaboration)
* [Precision luminosity measurement in proton-proton collisions at s√= 13 TeV in 2015 and 2016 at CMS](https://arxiv.org/pdf/2104.01927) (2021) (CMS Collaboration)
* [Luminosity Determination At Proton Colliders](http://dx.doi.org/10.1016/j.ppnp.2014.11.002) (2015) (P.Grafstrom, W.Kozanecki)
* [Concept of luminosity](https://cds.cern.ch/record/941318/files/p361.pdf) (2006) (W.Herr, B.Muratori)
* [Luminosity considerations for the LHC](https://cds.cern.ch/record/260711/files/P00022101.pdf) (1994) (K.Eggert, K.Honkavaara, A.Morsch)
* [Calibration of the effective beam height in the ISR](http://cdsweb.cern.ch/record/296752/files/196800064.pdf) (1968) (S.van der Meer)

### Further references
* [LHC Programme Coordination - Luminosity Calibration](https://lpc.web.cern.ch/lumicalib.htm)
* [LHC Guide - FAQ](http://cds.cern.ch/record/2255762/files/CERN-Brochure-2017-002-Eng.pdf) (2017)
* [Instrumentation for beam radiation and luminosity measurement in the CMS experiment using novel detector technologies](https://indico.cern.ch/event/391665/contributions/1827269/attachments/1229512/1801668/Guthoff_VCI16_Poster.pdf) (2016) (M.Guthoff) 

## Glossary

Fill
: Increments once the LHC injects proton bunches into the LHC (more details: [CERN Control Centre "From the LINAC to the LHC" (2014)](https://videos.cern.ch/record/1750702))

Run
: Sub-section of a fill, increments each time the CMS central DAQ initates data taking

Lumi section
: Sub-section of a run, defined as $$ 2^{18} \cdot \mathrm{orbits_{LHC}} = 2^{18} \cdot \frac{\mathrm{N_{bunches}}}{\mathcal{f}_{\mathrm{crossing}}} = 2^{18} \cdot \frac{3564}{40 \times 10^{6} \mathrm{Hz}} \approx 23.3570304 \mathrm{s} $$

Lumi nibble
: Sub-section of a lumi section, defined as $$ 2^{12} \cdot \mathrm{orbits_{LHC}} \approx 0.3649536 \mathrm{s} $$

{% include links.md %}
