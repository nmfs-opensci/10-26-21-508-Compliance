# 10-26-21 NMFS R UG meeting 508 Compliance

Discussion of 508 Compliance and R Markdown documents. [Reference material](https://github.com/nmfs-openscapes/10-26-21-508-Compliance/tree/main/reference)

## Speakers

* [Kimberly Bastille - NOAA Affiliate]() and [Abigail Tyrell - NOAA Affiliate](): NEFSC Shiny app reports 
* [Kelli Johnson - NOAA Federal](): NWFSC Developing PDF (LATEX) Stock Assessment Reports
* [Emily Markowitz - NOAA Federal](): AFSC 508 compliance in word with R Markdown

## Notes

https://github.com/rstudio/rmarkdown/issues/1867#issuecomment-918809374 

State of the Ecosystem

* Build reports in R Markdown.
    * Madlib https://docs.google.com/document/d/1Vmzcr8pSaL-ox5bcqbnpcg6NQxvoGyCWLj4maIoVgm8/edit
    * Colors 508 compliance. viridis palette?
    * Post-processing to add alt-text

## Adding alt-text to figures

Sarah: Big issue is alt-text in pdf

Abigail: has some GitHub code to add alt-text

   * Convert to Word then to export to PDF to get the alt-text.
   * https://github.com/atyrell3/AKesp/blob/main/R/functions.R. `render_fig` function here. It just pastes in the figure from an image file, but it could be re-worked to create the figure within R

Kelli: RMarkdown and knit to html: https://www.r-bloggers.com/2021/04/new-in-knitr-improved-accessibility-with-image-alt-text/

Dylan Gomes: For equations: https://rpruim.github.io/s341/S19/from-class/MathinRmd.html

Jordan Watson - NOAA Federal9:25 AM

## Palettes

Richard McBride: {viridis} can do 508 compliance palettes.

Christine: The nmfs color palette in the NMFS toolbox is the official 508 compliant color set from comms. The NMFS color palette: https://github.com/nmfs-general-modeling-tools/nmfspalette.   Point of the NMFS palette is to take the comms guidance to apply the palette. Incidental that those are compliant.

Jordan Watson: Here's the pdf that shows the NMFS colors. I got this from the Comms folks at the AKRO https://drive.google.com/file/d/1CAtChh5z1XucyXLx72yJWz6F-sdU9mP6/view?usp=sharing. This is what Christine put into the nmfs color palette. If that's helpful

## Help for testing for accessibility

Molly: Has resources to do this

Sarah Gaichas: I have also used this in the past which has an improve for colorblind option: http://medialab.github.io/iwanthue/

Erin Steiner: I really like this website for testing/understanding colorblind palettes. https://www.color-blindness.com/coblis-color-blindness-simulator/

Sarah Gaichas: https://wave.webaim.org/


