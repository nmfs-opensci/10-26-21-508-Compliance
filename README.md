# 10-26-21 NMFS R UG meeting 508 Compliance

Discussion of 508 Compliance and R Markdown documents. [Reference material](https://github.com/nmfs-openscapes/10-26-21-508-Compliance/tree/main/reference)

## Meeting Notes

[Google Drive Notes](https://docs.google.com/document/d/16cfqref6zZ5touRYN5VfLN8Caj-i7p7gREo2QkWMARU/edit?usp=sharing) Only accessible to NOAA staff.

[Recording of the session](https://drive.google.com/file/d/1-KQd2sur0l1UxWtvl03smYR9WexdzVXZ/view?usp=sharing) Only accessible to NOAA staff.

Issues discussed were focused on PDF and Word reports not html.

* Compliant palettes
* alt-text for Figures
* tables
* testing your documents for accessibility and text-to-speech compatibility.


## Adding alt-text to figures

* GitHub issue on this topic https://github.com/rstudio/rmarkdown/issues/1867#issuecomment-918809374 


Sarah: Big issue is alt-text in pdf

Abigail: has some GitHub code to add alt-text

   * Convert to Word then to export to PDF to get the alt-text.
   * https://github.com/atyrell3/AKesp/blob/main/R/functions.R. `render_fig` function here. It just pastes in the figure from an image file, but it could be re-worked to create the figure within R

Andy Beet has a example markdown code that will add the alt-text to figures in Word https://github.com/andybeet/508

Eli added an Rmd with some tests and examples https://github.com/nmfs-openscapes/10-26-21-508-Compliance/blob/main/example-alttext-to-word.Rmd

Basically this is the code `![Figure caption](fig.png "this will be the alt-text")`

RMarkdown and knit to html now allows alt-text tag: https://www.r-bloggers.com/2021/04/new-in-knitr-improved-accessibility-with-image-alt-text/

For equations: https://rpruim.github.io/s341/S19/from-class/MathinRmd.html


### How to write alt-text

[Example MadLib for NMFS reports](https://docs.google.com/document/d/1Vmzcr8pSaL-ox5bcqbnpcg6NQxvoGyCWLj4maIoVgm8/edit) NOAA staff access only.
 
Example: *Time series describing the long-term sea surface temperature on the Northeast Shelf. The X-axis shows time in years ranging from 1852 to 2019 and the Y-axis shows temperature in degrees celsius ranging from 10 to 14 degrees. The overall trend is increasing. In the last ten years, the temperature has continued to increase.*

[BrailleR package](https://github.com/ajrgodfrey/BrailleR) (Jonathan Goodfrey): Will automatically create alternative text for a plot (ggplot).  {ggplot2} works with {braille-r}.


## Palettes

Richard McBride: {viridis} can do 508 compliance palettes.

The nmfs color palette in the NMFS toolbox is the official 508 compliant color set from comms. The NMFS color palette: https://github.com/nmfs-general-modeling-tools/nmfspalette.   Point of the NMFS palette is to take the comms guidance to apply the palette. Incidental that those are compliant.

Here's the pdf that shows the NMFS colors. I got this from the Comms folks at the AKRO https://drive.google.com/file/d/1CAtChh5z1XucyXLx72yJWz6F-sdU9mP6/view?usp=sharing. This is what was put into the nmfs color palette. If that's helpful

https://drive.google.com/file/d/1-UuTsuMPHzzD-EzweGeOEU_2zWuseltD/view?usp=sharing. FWIW - a branding guide also given to me by the AKR

The NOAA brand guidance and templates is now available on an internal Google site (Inside Fisheries). You'll find a link to that in the [Google Drive Notes](https://docs.google.com/document/d/16cfqref6zZ5touRYN5VfLN8Caj-i7p7gREo2QkWMARU/edit?usp=sharing) Only accessible to NOAA staff.

## Help for testing for accessibility

Test colors: http://medialab.github.io/iwanthue/.  https://www.color-blindness.com/coblis-color-blindness-simulator/

https://wave.webaim.org/

Check your text by listening to it be read aloud

Word: Go into to Review panel and click "Read Aloud". It'll read the alt-text.

PDFs:
  
  * Adobe Acrobat Reader has a text reader in it so just open your PDF in that and use View: Read Aloud
  * @Voice Aloud app for your Android phone is nice too.


## Tables

{flextable} is great exp for Word. https://ardata-fr.github.io/flextable-book/index.html

508 compliance and tables in PDFs is tough. Merged columns is a problem. See table examples in www.github.com/nwfsc-assess/sa4ss


## Themed presentations

Here is the vignette on xaringan themed presentations https://nmfs-general-modeling-tools.github.io/nmfspalette/articles/ThemedPresentations.html

The .Rmd template is here: https://github.com/nmfs-general-modeling-tools/nmfspalette/blob/main/vignettes/xaringan_template.Rmd you specify colors directly in the template but could easily pick other colors from the branding guide if these weren't high contrast enough

## Making R Markdown documents accessible

   * line length is important. Add returns to your code.
   * using child elements can make Rmd really hard to read.

The styler package for RStudio does check wrapping, indents, etc. according to the tidyverse style guide. Not sure how comprehensive the checks are and how they comply with 508. https://github.com/r-lib/styler

## Workflows

Here are some workflows that different people talked about

1. Build reports in R Markdown to Word
2. Change colors for 508 compliance. viridis palette was commonly used nmfs-palette is also 508 compliant.
3. Post-processing in Word to add alt-text.
4. Check output for accessibility (see links).
5. Save from Word to PDF. **Make sure to use the 'optimize for accessibility' option when you save** otherwise the alt-text won't be captured and the text to speech can get garbled.

Kelli's Workflow for assessment reports to PDF

* Relies on a template from which all reports are derived  www.github.com/nwfsc-assess/sa4ss

Emily's Workflow

* R package to Word. Post-processing of alt-text in Word.


