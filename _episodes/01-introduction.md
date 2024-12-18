---
title: "Introduction"
teaching: 30
exercises: 10
questions:
- "What is luminosity?"
- "What is the difference between instantaneous and integrated luminosity?"
- "Why is knowing the luminosity important?"
- "How is luminosity measured?"
objectives:
- "Know what luminosity is and why it is important"
- "Know how luminosity is measured"
keypoints:
- "Luminosity is a measure of how many collisions are delivered to and recorded by the detector."
- "Instantaneous luminosity is usually expressed as the number of collisions per square centimeter per second."
- "Integrated luminosity is the integral of instantaneous luminosity over time and is a measurement of data size. It is usually expressed in units of inverse cross section."
- "Knowing the luminosity is important to determining and measuring accelerator and detector performance and operation. It is also an essential component for measuring cross sections and for setting limits on beyond-SM processes."
- "Measurement of luminosity is done with muiltple systems in the CMS detector."
---

> ## References
> You can find several [papers](/reference.html#papers) with much more technical detail and several [articles](/reference.html#articles) with additional (less formal) information in the [References](/reference.html).
{: .callout}

## Instantanous Luminosity

In the context of the LHC, instantaneous luminosity $$ \mathcal{L}_{inst} $$, corresponds to the number of interactions produced when bunches of protons are crossed.
Roughly speaking, it refers to the "real-time rate of interactions".
During 2022, groups of more than 100 billion protons were crossed as often as 40 million times per second yielding an overall average of 46 interactions per crossing (pileup) within the CMS detector.

![Interactions per crossing (pileup) for 2015-2023](https://cmslumi.web.cern.ch/publicplots/pileup_allYears.png){:width="60%"}

More precisely, instantaneous luminosity quantifies the ability of particle accelerator to produce a certain number of interactions.
It represents a proportionality factor between rate of interactions $$ \left( \frac{dN}{dt} \right) $$ and the cross-section ($$ \sigma $$):

$$ \frac{d\mathrm{N}}{dt} = \mathcal{L}_{inst} \cdot \sigma $$

Thus, instantaneous luminosity is usually expressed in the cgs units of $$ \mathrm{cm^{-2} s^{-1}} $$.
Units of "barns" are also used frequently, where $$ 1 \mathrm{b} = \mathrm{10^{-24} cm^{2}} $$, thanks to [two Purdue University physicists working on the Manhattan Project in 1942](https://www.symmetrymagazine.org/article/february-2006/hitting-the-broad-side-of-a-classified-barn).
As an example, let's *very approximately* calculate the total Higgs Boson production rate at CMS:

> ## 1.1 Total Higgs boson production rate at CMS
> * During [November 2022](https://cmsoms.cern.ch/cms/fills/summary?cms_date_from=2022-11-01&cms_date_to=2022-11-30&cms_fill_stableOnly=true), the LHC routinely delivered instantanous luminosities close to $$ \approx 2 \times 10^{34} \mathrm{cm^{-2} s^{-1}} $$ $$ \left( 0.02 \mathrm{pb^{-1} s^{-1}} \right) $$ at CMS
> * The total production cross section of Standard Model Higgs boson at $$ \sqrt{s} = 13.6 \mathrm{TeV} $$ is nearly $$ \approx 60 \mathrm{pb} $$ ([see table 11.2 in the 2024 PDG](https://pdg.lbl.gov/2024/reviews/rpp2024-rev-higgs-boson.pdf))
>
> What is the rate of Higgs production at CMS?
>
> $$ \frac{d\mathrm{N_{Higgs}}}{dt} = \mathcal{L}_{inst}^{\mathrm{peak}} \cdot \sigma_{\mathrm{Higgs}}^{\mathrm{total}} $$
> 
<!--
/poll "1.1 What is the rate of Higgs production at CMS?" "120 Hz" "0.012 Hz" "1.2 Hz"
> > ## Solution
> > $$ \approx 0.02 \mathrm{pb^{-1} s^{-1}} \times 60 \mathrm{pb} \approx 1.2 \mathrm{Hz} $$
> {: .solution}
-->
{: .challenge}

## Integrated Luminosity

Instantaneous luminosity is aggregated over a certain period of time to obtain integrated luminosity:

$$ \mathcal{L}_{int} = \int \mathcal{L}_{inst} dt $$

It is commonly used to quantify the "amount of data" delivered by the accelerator or recorded by the experiment.
Units of inverse femtobars $$ \mathrm{fb^{-1}} $$ are frequently used in CMS.

![Cumulative delivered and recorded luminosity versus time for 2015-2023 (pp data only)](https://cmslumi.web.cern.ch/publicplots/multiYear/int_lumi_allcumulative_pp_run2and3.png){:width="60%"}

To illustrate, we can *very roughly* estimate the total number of Higgs bosons produced during 24 hours at CMS:

> ## 1.2 Total Higgs bosons produced at CMS during 24 hours
> * During [2022-Nov-01](https://cmsoms.cern.ch/cms/summaries/daily_summary?year=2022&month=11&day=1), CMS recorded $$ \approx 1000 \mathrm{pb^{-1}} $$ during a 24-hour period
> * The total production cross section of Standard Model Higgs boson at $$ \sqrt{s} = 13.6 \mathrm{TeV} $$ is nearly $$ \approx 60 \mathrm{pb} $$ ([see table 11.2 in the 2024 PDG](https://pdg.lbl.gov/2024/reviews/rpp2024-rev-higgs-boson.pdf))
>
> How many Higgs bosons were produced at CMS during these 24 hours?
>
> $$ \mathrm{N_{Higgs}} = \mathcal{L}_{int}^{\mathrm{24hr}} \cdot \sigma_{\mathrm{Higgs}}^{\mathrm{total}} $$
> 
<!--
/poll "1.2 How many Higgs bosons can be produced at CMS during 24 hours?" "60" "6000" "60000"
> > ## Solution
> > $$ \approx 1000 \mathrm{pb^{-1}} \times 60 \mathrm{pb} \approx 60 \times 10^{3} $$
> {: .solution}
-->
{: .challenge}

## Importance of Luminosity

Along with the center of mass energy, instantanous luminosity is the most significant performance parameter for any particle accelerator.
Real-time monitoring of instantaneous luminosity is critical for the accelerator to carry out beam tuning and collision optimization.
It is also essential for the CMS trigger system in order to pre-scale (throttle) the trigger rates.

Measuring integrated luminosity *precisely* is crucial since it contributes to the systematic uncertainty for nearly all physics searches and measurements.
The uncertainty in the integrated luminosity is often the dominant systematic uncertainty in EWK cross-section measurements.
We can emphasize the impact of the integrated luminosity uncertainty by considering a relatively rare process:

> ## 1.3 Total Higgs bosons decaying to muon pairs at CMS
> * During 2022, CMS recorded around $$ \approx 38 \mathrm{fb^{-1}} $$ of good-quality data with 1.4% uncertainty (see [Luminosity recommendations for Run 3 analyses](https://twiki.cern.ch/twiki/bin/view/CMS/LumiRecommendationsRun3#2022))
> * The total production cross section of Standard Model Higgs boson at $$ \sqrt{s} = 13.6 \mathrm{TeV} $$ is nearly $$ \approx 60 \mathrm{pb} $$ ([see Table 11.2 in the 2024 PDG](https://pdg.lbl.gov/2024/reviews/rpp2024-rev-higgs-boson.pdf))
> * The branching ratio for $$ H \rightarrow \mu \mu $$ is nearly $$ \approx 2 \times 10^{-4} $$ ([see Table 11.3 in the 2024 PDG](https://pdg.lbl.gov/2024/reviews/rpp2024-rev-higgs-boson.pdf))
>
> What is the minimum and maximum expected event yield given the uncertainty in integrated luminosity?
>
> $$ \mathrm{N}_{H \rightarrow \mu \mu}^{2022} = \left( \mathcal{L}_{int}^{2022} \pm \delta \right) \cdot \sigma_{\mathrm{Higgs}}^{\mathrm{total}} \cdot \mathcal{B}_{H \rightarrow \mu \mu} $$
> 
<!--
/poll "1.3 Given the luminosity uncertainty, what are the upper and lower bounds of Higgs -> dimuon produced at CMS during 2022?" "[292.5, 307.5]" "[297.5, 302.5]" "[299.875, 300.125]" "[615, 585]" "[625, 575]"
> > ## Solution
> > $$ \leq \left( 38 + \frac{1.4}{100} \cdot 38 \right) \cdot 10^{3} \mathrm{pb^{-1}} \cdot 60 \mathrm{pb} \cdot 2 \times 10^{-4} \approx 462 $$\
> > $$ \geq \left( 38 - \frac{1.4}{100} \cdot 38 \right) \cdot 10^{3} \mathrm{pb^{-1}} \cdot 60 \mathrm{pb} \cdot 2 \times 10^{-4} \approx 450 $$
> {: .solution}
-->
{: .challenge}

## Luminosity Measurement

CMS has two dedicated systems for measuring luminosity, both located $$ z \approx \pm 1.8 \mathrm{m} $$ from the interaction point and radius $$ \approx 6 \mathrm{cm}$$:

Fast Beam Condition Monitor (BCM1F)
: C-shaped PCBs arranged into two rings at each side of CMS with 6 double-pad silicon sensors per c-shape
: Precise timing measurements ($$6.25 \mathrm{ns}$$ per bin), via two independent read out systems (VME & $$\mu$$TCA), facilitate separation of collision products from machine-induced background

![BCM1F C-shape](https://cds.cern.ch/record/2765247/files/2021-05-20%2015.19.28.jpg?subformat=icon-1440){:width="60%"}

Pixel Luminosity Telescope (PLT)
: 16 "telescopes" (8 per side of CMS) with three hybrid silicon pixel sensors per telescope
: Fast cluster-counting signal readout ($$40 \mathrm{MHz}$$), in parallel to full pixel data readout

![Pixel Luminosity Telescope](https://cds.cern.ch/record/2777045/files/2021-06-29%2011.19.34.jpg?subformat=icon-1440){:width="60%"}

In addition, several sub-detectors are used for luminosity measurement, among them:

PCC (Pixel Cluster Counting)
: Counts the mean number of pixel clusters in the most "stable" modules of the silicon pixel detector

Hadronic Forward (HF)
: Steel absorber with quartz fibers to detect Cherenkov light histogrammed as function of bunch crossing and read out via two independent systems (HFET & HFOC)

> ## Which detector is more photogenic?
>
> [https://indico.cern.ch/event/1239959/surveys/4059](https://indico.cern.ch/event/1239959/surveys/4059)
{: .challenge}



## Luminosity Calibration

The precise determination of integrated luminosity is particularly challenging at hadron colliders, in part due to the theoretical predictions being generally less precise compared to $$ e^{+} e^{−} $$ colliders (e.g. uncertainties in the parton distribution functions and precision of parton-level cross-section calculations).
A sub-detector can easily measure "relative" luminosity on an arbitrary scale based on the measured event rate.
The complexity lies in the determination of "absolute" luminosity, which involes re-scaling the measured event rate by a proportionality factor, $$ \sigma_{vis} $$, derived from the properties of the colliding beams.
This scaling factor may be thought of as a way to account for the sub-detector's particular acceptance and response.

At the LHC, the primary technique to determine the absolute luminosity scale is the van der Meer (vdM) scan method, based on dedicated beam-separation scans.
The size and shape of the interaction region is measured by recording the relative interaction rates as a function of the transverse beam separation.
After adopting several assumptions (e.g. transverse and longitudinal beam densities are Gaussian, density functions are factorizable into $$x$$- and $$y$$-dependent components, etc.), the visible cross-section can be expressed as

$$ \sigma_{vis} = \mu_{vis}^{\mathrm{max}} \frac{2 \pi \Sigma_{x} \Sigma_{y}}{n_{1} n_{2}} $$

where $$ \mu_{vis}^{\mathrm{max}} $$ is the peak visible interaction rate per bunch,
$$ n_{1} $$ and $$ n_{2} $$ are the numbers of particles in each of the two bunches,
and $$ \Sigma_{x} $$ and $$ \Sigma_{y} $$ correspond to the effective beam overlap widths in each scan plane.
Thus, luminosity can be determined from the *number of particles per bunch* and the *geometrical overlap of the two beams (luminous region)*.

![Luminosity scan](https://atlas.cern/sites/default/files/2023-01/countingcollisions.png){:width="60%"}

![Rate vs separation](https://brildpg.web.cern.ch/public/lum-22-001/Figure_002-a.png){:width="40%"}

### Calibration ($$ \sigma_{vis} $$) corrections

Several systematic effects can affect the measurement of $$ \sigma_{vis} $$.
These represent a major contribution to the final uncertainty in the measurement of integrated luminosity.

Orbit drift & beam position corrections
: Time-dependent changes of the transverse beam positions (orbit drift) that affect the beam separation are monitored with the DOROS beam positions monitors (BPM)
: After considering nominal beam positions, linear orbit drift corrections, and predicted beam-beam deflection, residual deviations are applied as corrections to the beam positions

Length scale calibration
: During the beam separation scans, the beam positions are steered with LHC corrector magnets; thus, the nominal beam position is derived from the magnet currents
: These nominal beam positions are corrected using the beamspot position extracted from reconstructed vertices during dedicated length-scale ("Hobbit") scans

Beam-beam effects
: The electromagnetic interaction between proton bunches changes their transverse position (beam-beam deflection) and their density distribution (dynamic-β effect)
: The effect of beam-beam deflection is calculated analitically from the Bassetti–Erskine formula and the dynamic-β effect is parametrized using numerical simulations

Factorization bias
: The estimation of the luminous area from an $$x-y$$ scan pair assumes that the transverse proton bunch densities can be expressed as uncorrelated functions in $$x$$ and $$y$$
: This assumption is tested by using multiple 2D fit functions to model the beam overlap shape while comparing their consistency for several luminometers

Bunch current measurement and corrections
: Bunch current is measured with the fast bunch current transformers (FBCT) and the total beam current with the direct current current transformers (DCCT)
: "Spurious" charges (ghosts👻 in empty bunch slots and out-of-time satellites🛰 orbiting a filled bunch) are measured by longitudinal density monitors (LDMs)

> ## Dominant uncertainties in the absolute luminosity scale ($$ \sigma_{vis} $$)
> * factorization bias
> * beam-beam effects
> * beam position corrections
{: .callout}

### Integration (detector-specific) corrections

The vdM scan program is carried out with a small number of well-separated proton bunches with low bunch intensities.
In order to extrapolate the resulting $$ \sigma_{vis} $$ to high-pileup data-taking conditions, several corrections need to be estimated and applied.

Out-of-time pileup corrections
: Corrections for contributions due to spill-over of electronic signals (type-I) and exponentially decaying afterglow due to activation of detector material (type-II)

Stability and linearity
: Gradual efficiency loss for each luminometer (mainly due to radiation damage) is monitored and corrected for based on the analysis of emittance scans (fast luminosity separation scans run often under physics production conditions) and by comparing the consistency between multiple luminometers
: The consistency of detector response as a function of pileup is compared between several luminometers to estimate the non-linearity of each luminometer

{% include links.md %}
