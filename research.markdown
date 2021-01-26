---
layout: page
title: Research
permalink: /research/
---

![](assets/images/japanese-waves-painting.jpg)

Current projects:

I am actively working on research related to:  
* [Ocean boundary layer mixing](#BLT)
  * [energetic Planetary Boundary Layer](#ePBL)
  * [Boundary Layer Paramaterizations](#BLParam)
  * [Langmuir turbulence and its parameterization](#LT)  
  * [Ocean model mixed layer evaluation](#MLD)
  * [Machine learning and OSBL parameterization](#ML)
* [Ocean and Wave Model Development](#Devel)
  * [MOM6](#MOM6)
  * [WW3](#WW3)
  * [Wave-Ocean Coupling](#WavOce)
* [Air-sea gas flux parameterizations](#GasFlux)  

<a name="BLT"></a>  
# Boundary Layer Turbulence and its parameterization  

The near-surface layer of the ocean hosts a variety of turbulent processes that act together to determine how water and its properties are mixed.  My research primarily focuses on processes that drive vertical mixing in this near-surface regime, through which atmospheric and ocean interior properties are ultimately exchanged.  This problem is important for understanding how the ocean works and its role in weather and climate over a variety of timescales.  This includes the intense turbulence driven by extreme winds and waves under a tropical cycle, diurnal cycles of heating and cooling, and seasonal cycles of turbulence and boundary layer entrainment/detrainment.

Much of my work focuses on developing parameterizations, or sub-models within an ocean circulation model that are designed to take information from the model (e.g., currents, waves, stratification, and surface fluxes of heat and momentum) and tell the model how much mixing occurs.  This is necessary because the models are specifically designed to address relatively large-scale problems, such as circulation on scales ranging from several kilometers to planetary scales, but mixing is a small-scale process dealing with fluctuations that occur on scales of meters and smaller.  The model therefore doesn't simulate the necessary information to directly resolve turbulence, hence the need to build these sub-model "parameterizations".

<a name="ePBL"></a>
### energetic Planetary Boundary Layer

There are numerous approaches to parameterizing the turbulence in the ocean for ocean circulation models.  Within [MOM6](https://github.com/NOAA-GFDL/MOM6), we have implemented a parameterization called the energetic Planetary Boundary Layer, or ePBL.  This parameterization is based on decades old ideas about the bulk energy budgets that drive boundary layer turbulence, which Robert Hallberg (NOAA-GFDL) used as motivation for developing this scheme.  I have worked closely with Bob to continue developing this boundary layer parameterization and extend its usefulness for resolving vertical structure in the boundary layer (a missing feature in original bulk boundary layer approaches).  We have specifically focused the development of ePBL on having skill in simulating boundary layer properties for models used in climate prediction, but I am actively working on extensions to further improve its performance in transient and extreme conditions.

Bob and I recently published a paper introducing the ideas behind ePBL and how we have engineered the parameterization to work optimally in the regime of climate modeling, where computational performance becomes particularly important: [Reichl and Hallberg, 2018](https://www.sciencedirect.com/science/article/pii/S1463500318301069).

<a name="BLParam"></a>
### Boundary Layer Parameterizations

While ePBL is our parameterization of choice in MOM6, there are numerous other approaches for the boundary layer that can have advantages in a variety of conditions.  One such model, KPP, has been one of the most popular choices for boundary layer turbulence parameterization in ocean models for over two-decades.  I have worked extensively with KPP, including evaluating its performance in the [CVMix](https://github.com/CVMix) project: [Van Roekel et al., 2018](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2018MS001336).  We continue to consider KPP and its utility in ocean models.  While I am much more focused on ePBL these days, I remain interested in understanding the differences between ePBL and KPP and what we can learn from situations where the two models agree versus situations where they do not.

<a name="LT"></a>
### Langmuir Turbulence

I have worked extensively to understand the role of surface waves via Langmuir turbulence in ocean surface boundary layer mixing, including writing two chapters of my Ph.D. disseration on this topic.  We often work with Large Eddy Simulations (high-resolution fluid dynamics models that directly simulate the length-scales where turbulent kinetic energy is produced in the boundary layer) that solve a special form of the Navier-Stokes equations, known as the Wave-Averaged Navier-Stokes equations.  These equations introduce additional turbulent production mechanisms and change the overall behavior of the boundary layer due to the presence of surface waves via the Stokes drift.

Specific research topics related to Langmuir turbulence that have interested me lately include:
* Investigating Langmuir turbulence characteristics under a hurricane in LES and observations: 
[Rabe et al., 2014](https://journals.ametsoc.org/view/journals/phoc/45/3/jpo-d-14-0030.1.xml), [Wang et al., 2018](https://journals.ametsoc.org/view/journals/phoc/48/9/jpo-d-17-0258.1.xml), [Wang et al., 2019](https://journals.ametsoc.org/view/journals/phoc/49/12/jpo-d-19-0093.1.xml).
* Developing new parameterizations for boundary layer mixing that include Langmuir turbulence for hurricanes:
[Reichl et al., 2016](https://journals.ametsoc.org/view/journals/phoc/46/3/jpo-d-15-0106.1.xml), and in ePBL:
[Reichl and Li, 2019](https://journals.ametsoc.org/view/journals/phoc/49/11/jpo-d-18-0258.1.xml).
* Comparing various Langmuir turbulence parameterizations: [Li et al., 2019](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2019MS001810).

<a name="MLD"></a>
### Mixed Layer Analysis in Ocean Models  

I am actively working to develop new methods to use Argo data to evaluate boundary layer parameterizations in ocean models.

<a name="ML"></a>
### Machine Learning for OSBL Parameterization  

I am part of a [new project](https://m2lines.github.io/) to improve climate modeling using machine learning.  We are looking to hire a postdoc for [this work]({% link _posts/2021-01-25-new-position.markdown %}).

<a name="Devel"></a>
# Ocean and Wave Model Development  

I am an active contributor to the development of NOAA's [WAVEWATCH III](https://github.com/NOAA-EMC/WW3) surface wave model and [MOM6](https://github.com/NOAA-GFDL/MOM6) ocean model.

<a name="MOM6"></a>
# Modular Ocean Model 6

In MOM6 I have contributed code to improve boundary layer parameterizations and include surface wave effects.  I am an active member of the MOM6 development team and have contributed to the development of GFDL's most recent round of climate model configurations.  These models include:
* GFDL's OM4 Ocean Sea-Ice Simulator: [Adcroft et al., 2019](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2019MS001726).
* GFDL's CM4 Climate Simulator: [Held et al., 2019](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2019MS001829).
* GFDL's ESM4.1 Earth System Simulator: [Dunne et al., 2020](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2019MS002015).

<a name="WW3"></a>
# WAVEWATCH III

In WAVEWATCH III I have contributed code to compute sea-state dependence wind stress parameterizations, Stokes drift information for coupled models, and am actively working to add more complete tripolar grid support.

Over the Summer of 2020 I hosted Avery Barnett (from Grinnell College) as a Princeton-CIMES intern to evaluate WAVEWATCH performance under hurricanes.  Avery earned  [an award](https://cimes.princeton.edu/news/cimes-intern-avery-barnett-recognized-2020-sacnas) for her research presentation on this work at the annual [SACNAS](sacnas.org) conference.

<a name="WavOce"></a>
# Wave-Ocean Model Coupling

Much of my research is motivated on the role of waves in the coupled weather and climate system.  This requires developing coupled modeling systems, such as a new configuration of WW3 with MOM6 I have worked on.  This research will lead to a GFDL-FMS model coupler compatible wave-ocean configuration.

During my Ph.D. I looked into the role of including sea-state dependent Langmuir turbulence in hurricane ocean simulations using a coupled WAVEWATCH III-Princeton Ocean Model configuration:
[Reichl et al., 2016b](https://journals.ametsoc.org/view/journals/mwre/144/12/mwr-d-16-0074.1.xml).

<a name="GasFlux"></a>
# Air-sea gas flux parameterization

I am collaborating with [Luc Deike (Princeton)](https://ldeike.princeton.edu/) to better understand the role of breaking waves and bubbles in air-sea gas fluxes.  Luc and I began our collaboration to investigate how important it is to include sea-state information in gas flux parameterizations.  Recently, we published our first study to begin to probe this exciting problem:
[Reichl and Deike, 2020](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2020GL087267).
