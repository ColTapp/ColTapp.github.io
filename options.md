---
layout: default
title: Options
---
# Options

The default parameters of each functionality of ColTapp can be tuned by the user within the _Options_. The _Options_ window is divided into four tabs : _Global_, _Detect_, _Main_ (_TL_ or _EP_) and _Visualize_. 

## Global
While the latter tabs regroup parameters corresponding to each corresponding tab of the main panel, the first tab, _Global_ (left panel of the following figure), regroups all parameters which apply globally, whatever the analysis step.
### Color to grayscale method selection
Colored RGB images are transformed into grayscale images for many image analysis steps (colony detection, colony kymograph derivation from time-lapse images). ColTapp offers 16 different methods for grayscale conversion. 
Using one of the three RGB channels is computationally quick and generally precise enough, but in some special cases, the user may want to use a different conversion, as for example a transformation to other classical color spaces (e.g. CIELAB) and using one of the generated channels. The inbuilt MATLAB function rgb2gray which uses a weighted image conversion, retaining information of all three color channels, is also available. With "Select RGB to grayscale method from examples" the user may visualize the result of each different method (as shown in the right panel of the following Figure) and select the most appropriate method.
<figure>
  <img src="{{site.url}}/assets/images/Options_Global_wGrayscale.png" alt="Global tab" height="800px"/>
  <figcaption> Global tab of the Options (Part of Fig. S2 of the publication) and grayscale conversion methods </figcaption>
</figure>
### Visualize on image
The user can use toggles to chose which data should be visualized directly on the images in the main panel.
<figure>
  <img src="{{site.url}}/assets/images/Visualize_on_image.png" alt="Visualize on image" height="550px"/>
  <figcaption> Visualization on main panel image </figcaption>
</figure>

### Reference growth data

### Save options

### Reset active list


## Detect
## Main-TL
## Main-EP
## Visualize

