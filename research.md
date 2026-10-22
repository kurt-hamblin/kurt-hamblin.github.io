---
layout: page
title: Research
---

**Uncovering Hidden Black Holes in the Distant Universe**<br>
PhD in Physics, University of Kansas. Defended July 2026. Advisor: Allison Kirkpatrick.<br>
NASA FINNEST Fellow.
<!-- TODO: link to the dissertation (ProQuest) once it is available. -->

## Background

Almost every massive galaxy has a supermassive black hole at its center. When that black hole is actively pulling in gas, it can outshine the entire galaxy, and we call it an active galactic nucleus (AGN). Black holes and galaxies seem to have grown together: both star formation and black hole growth peaked about 2 to 6 billion years after the Big Bang, a period called cosmic noon, and have declined together since. Whether black holes actually shape their host galaxies is still an open question, and answering it requires finding AGN across their full range of properties.

That turns out to be hard. Many AGN are hidden behind dust, and many are faint enough that their host galaxy's starlight drowns them out. Optical, infrared, and X-ray methods each miss different AGN, and they all struggle with the same population: moderately bright AGN in dusty, star-forming galaxies, which is exactly what we expect to be common at cosmic noon.

JWST's mid-infrared instrument, MIRI, can see galaxies an order of magnitude fainter than Spitzer could. My dissertation used data from the MEGA survey (Backhaus et al. 2025), a JWST/MIRI survey of the Extended Groth Strip led by my advisor, and developed new ways to find the AGN that older methods miss.

## AGNBoost

The usual way to find AGN in infrared images is to compare a galaxy's brightness in a few filters and draw boundaries between AGN and star-forming galaxies. This breaks down with JWST data, because at certain redshifts star-forming galaxies have the same colors as AGN.

<figure>
  <video src="{{ '/assets/video/sed_color_animation.mp4' | relative_url }}" controls loop muted playsinline preload="metadata" aria-label="Animated color-color plot of AGN and star-forming galaxy models"></video>
  <figcaption>Star-forming galaxies can mimic the rising mid-infrared colors of AGN, as this animated color-color plot shows.</figcaption>
</figure>

AGNBoost is a machine learning model that uses all 11 JWST bands at once instead of just a few colors. For each galaxy, it predicts how much of the mid-infrared light comes from an AGN and estimates the galaxy's redshift, along with an uncertainty on both. I trained it on a million simulated galaxies, since very few real JWST galaxies have confirmed properties to learn from. It processes about 1000 galaxies in a few minutes on a laptop, compared to hours or days for traditional fitting.

On simulated galaxies, AGNBoost recovered AGN fractions and redshifts with outlier rates of a few percent. When I applied it to 748 MEGA galaxies, it found 131 AGN candidates (17.5%) and broadly agreed with traditional SED fitting.

## Chandra X-ray

X-rays are one of the most reliable signs of a growing black hole, since stars produce very few of them. The MEGA field already had about 800 ks of Chandra coverage, but the existing X-ray catalog only included sources bright enough to be found on their own.

Since JWST tells us exactly where every galaxy is, I reprocessed all 50 Chandra observations from scratch and measured the X-ray signal at the position of each of 3662 JWST galaxies. Knowing where to look made it possible to detect much fainter sources. I found 176 X-ray sources, and 113 of them (64%) were never cataloged before.

Comparing the X-ray and infrared results showed how much the two methods complement each other. Ten of the X-ray sources are heavily obscured AGN that look like ordinary galaxies in the infrared. I also found 52 candidates for low-luminosity AGN, which I followed up in the last part of my thesis.

## Low-luminosity AGN

The faintest AGN fall outside what AGNBoost was trained to find. To test the X-ray low-luminosity AGN candidates, I wrote a separate fitting method that splits a galaxy's JWST photometry into star-forming and AGN components and returns a probability distribution for the AGN contribution. The code is listed on the [Projects](/projects/low-luminosity-agn/) page.
<!-- TODO: add the headline result of the low-luminosity AGN analysis. -->

## What's next

I am now building an SED fitting code in JAX that models the X-ray and infrared emission from AGN together, which I proposed at the end of my dissertation.

## Links

**Code:** [AGNBoost on GitHub](https://github.com/kurt-hamblin/AGNBoost) · [Documentation](https://kurt-hamblin.github.io/AGNBoost/)

**Paper:** Hamblin et al. 2026, ApJ, 1002, 223 ([ADS](https://ui.adsabs.harvard.edu/abs/2026ApJ..1002..223H/abstract), [arXiv:2506.03130](https://arxiv.org/abs/2506.03130))
