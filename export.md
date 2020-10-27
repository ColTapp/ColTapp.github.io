---
layout: default
title: Export
---
# Export 

For further use in data analysis, some metrics on colonies can be exported. This is based on colonies that were already found in the program. This page descibes the export options. Most variables are exported as a three-column table, containing the frame number, the colony number and the exported data of interest, grouped with similar variables. See SI Fig. 4 from manuscript for some illustration on colonies.

<figure>
  <img src="https://github.com/ColTapp/ColTapp.github.io/blob/master/assets/images/ExportMenu.png" 
       alt=" Export menu overview" 
       width="100"
  <figcaption> Export menu overview (SI Fig.3 in manuscript) </figcaption>
  
</figure>

## Metadata export

This option exports several analysis parameters that were used for analysis, including (when set):
- image number
- image folder
- the spatial calibration factor
- plate radius and position, or region of interest polygon vertices
- image mode (Greyscale or RGB)
- detection radius threshold
- time of data export

## Export options

Data delimiter in the CSV, export unit (µm / pxl) can be chosen. A subpart of the data can be exported rather than the whole data, on specific frames (images) or colonies. For this specify numbers in one of those formats:
- a list of frames/colonies spearated by commas e.g. 1,3,4,6,8 => values outside range will be ignored
- a list in the form Start:Gap:End, e.g. 2:3:13 will export 2,5,8,11.
- in the case of colonies, a list number identifier specified as a single negative value (for list identifiers, see main GUI)



