---
layout: default
title: Options
---
# Options

The default parameters of each functionality of ColTapp can be tuned by the user within the _Options_. The _Options_ window is divided into four tabs : _Global_, _Detect_, _Main_ (_TL_ or _EP_) and _Visualize_. 

## Global
While the latter tabs regroup parameters corresponding to each corresponding tab of the main panel, the first tab, _Global_ (left panel of the following figure), regroups all parameters which apply globally, whatever the analysis step.

_Color to grayscale method selection_

Colored RGB images are transformed into grayscale images for many image analysis steps (colony detection, colony kymograph derivation from time-lapse images). ColTapp offers 16 different methods for grayscale conversion. 
Using one of the three RGB channels is computationally quick and generally precise enough, but in some special cases, the user may want to use a different conversion, as for example a transformation to other classical color spaces (e.g. CIELAB) and using one of the generated channels. The inbuilt MATLAB function rgb2gray which uses a weighted image conversion, retaining information of all three color channels, is also available. With "Select RGB to grayscale method from examples" the user may visualize the result of each different method (as shown in the right panel of the following Figure) and select the most appropriate method.
<figure>
  <img src="{{site.url}}/assets/images/Options_Global_wGrayscale.png" alt="Global tab" height="800px"/>
  <figcaption> Global tab of the Options (Part of Fig. S2 of the publication) and grayscale conversion methods </figcaption>
</figure>

_Visualize on image_

The user can use toggles to chose which data should be visualized directly on the images in the main panel.
<figure>
  <img src="{{site.url}}/assets/images/Visualize_on_image.png" alt="Visualize on image" height="70%"/>
  <figcaption> Visualization on main panel image </figcaption>
</figure>
The _Redefine lighting correction area_ button allows a user to chose a new subset of the image as input to the [lighting correction algorithm](https://coltapp.github.io/detect.html).

_Reference growth data_

When extracted a automatically from an analyzed control experiment, the [reference appearance time](https://coltapp.github.io/refparam.html) of that experiment is 
averaged using the mean, by default. Yet, users concerned by the presence of outliers in the growth control experiment may chose to use the median (or any user-defined quantile) via this tab.

_Save options_

Autosave, back-up save

_Reset active list_

ColTapp allows to group colonies into [lists](https://coltapp.github.io/detect.html) to use certain downstream functions only on the indicated subset of colonies. User can remove all colonies from the active list on the main panel with this button.

## Detect

_Image preprocessing_

Default:Adaptive, Global, none
Binarization sensitivity
Should the user want to detect white colonies on a darker background,

_Colony detection parameters_

## Main-TL

_Define radii-tracking parameters_

_Define appearance time parameters_

_Additional possibilities_

## Main-EP

## Visualize

After analyzing a time-lapse series, a quick visualization of the colony growth curves can be displayed by clicking on the _Radius vs Time_ button of the _Visualize_ tab of the main panel. In the _Options_ the user may chose to plot these curves 1) in raw units: pixels/frame or 2) in more biologically meaninful units, i.e micrometers/time. A user may also chose 3) a log-y axis, as this could enable to visualize an exponential curve as a linear slope (typically if the first growth phase is macroscopically detectable, which is not the case in the following example.
<figure>
  <img src="{{site.url}}/assets/images/Options_Visualize.png" alt="Options Visualize" height="70%"/>
    <figcaption> Visualize tab of the Options and example of colony growth curves visualization</figcaption> 
</figure>

In addition, the user can chose to visualize the colony size distribution on a given (or multiple) frame(s) with an histogram. The parameter _number of histogram bins_ can be inputted by the user.

