---
layout: default
title: Detect colonies
---
# Detect colonies

We will refer to the letters on the image below for the following instructions:
<figure>
  <img src="{{site.url}}/assets/images/Detect_1.png" alt="GUI overview"/>
  <figcaption>GUI overview (modified Fig S1 from manuscript) </figcaption>
</figure>


## Setup
### Spatial calibration (*a*)
Three options to define a pixel to micrometer spatial calibration factor are available:
<figure>
  <img src="{{site.url}}/assets/images/Detect_2.png" alt="GUI overview"/>
  <figcaption> Set spatial calibration (a) </figcaption>
</figure>
1. Enter the known diameter of a circle (e.g. 89’000 micrometers for the inner circle of a standard agar plate) in the editable field and click the _Use reference circle_ button below. A proposed circle is automatically detected and displayed. Either confirm this circle or alter it by clicking on three points on the circle which you want to utilize.
2. Enter any known distance in the editable field and click the _Use reference distance_ button. A ruler will be displayed on the image. The ruler should be scaled and moved appropriately and confirmed by hitting enter.
3. Directly enter the known spatial calibration factor and confirm with the button _Use direct conversion_.
Also note that one can switch the default exporting unit from pixels to micrometers in here.
In _EP_ mode, the spatial calibration factor is only applied to the current frame. Propagate it from the current frame to all frames with _Options/Main-EP/Apply calibration factor to all frames_.

### Area of interest (*b*)
Automatic colony detection can be narrowed to the defined boundaries of an area of interest (AOI). Users can select the plate as AOI or draw a custom polygon on the image. Using an AOI is suggested to reduce computational time and reduce false positive detection outside the boundaries of e.g. an agar plate. 
In _EP_ mode, the spatial calibration factor is only applied to the current frame. Propagate it from the current frame to all frames with _Options/Main-EP/Apply AOI to all frames_.

### Color to grayscale transformation
Colored RGB images are transformed into grayscale images for all subsequent image analysis steps. ColTapp offers 16 different methods for grayscale conversion. These can be changed in the _Global_ section of the _Options_ (*h*). Examples are shown below
<figure>
  <img src="{{site.url}}/assets/images/Detect_4.png" alt="RGB to grayscale conversion"/>
  <figcaption> RGB to grayscale conversion examples, accessible through _Options_ (h) </figcaption>
</figure>


### Grayscale image quality (*c*)
Mainly for visualization and manual correction of detected colonies, the grayscale images can be enhanced with either an auto-contrast toggle (*c*) or using a lighting correction algorithm to remove glares and flares (see example below).
<figure>
  <img src="{{site.url}}/assets/images/Detect_3.png" alt="Image enhancement"/>
  <figcaption> Image enhancement (c) </figcaption>
</figure>

### Detect colonies (*d*)
Automatic colony detection can be started with the _Find Colonies_ button (*d*). If in _TL_ mode, the function is executed on the current frame while in _EP_ mode, the user is asked to enter the frames on which the colony search should be executed. Accuracy and computational speed can be increased by specifying a narrow range of minimal and maximal radius. The range can be specified either by inserting values in pixel in _Options_ (*h*) or can be derived automatically from the smallest and biggest circle drawn on the currently displayed image with the button _Define radius range_ (*d*).
Refer to the [manuscript] (https://doi.org/10.1101/2020.05.27.119040) for details on the image analysis steps used.

### Manual correction of detected colonies (*e*)
Addition of non-detected colonies and false positive removal is possible through simple mouse-guided operations (*e*). Addition can be activated by either the button _(C) Add_ or the indicated shortcut _C_. Left-click on a colony center, hold and drag shown circle to border of colony, release and click once to confirm. Additionally, if the tickbox _Add/Remove with click_ is activated, colony addition can directly be started with a left-click colony center (hold and drag as described above).
Individual circles can be removed with the button _(R) Remove_ or the indicated shortcut _R_. Left-click inside a circle to remove it. Additionally, if the tickbox _Add/Remove with click_ is activated, a scroll-wheel (middle mouse button) click on inside a circle removes it. Removal of entire zones can be started with the button _(T) Clear in_ or the indicated shortcut _T_. Place edges of a polygon on the image with left-clicks and confirm with a double-click. Removal of all circles outside of a drawn polygon can be started with the button _(Z) Clear out_ or the indicated shortcut _Z_.
The button _(backslash) Undo_ or the indicated shortcut _backslash_ is used to undo up to seven of the last colony addition/removal steps.

### Generating lists of colonies (*f*)
ColTapp allows to group colonies into lists to use certain downstream functions only on the indicated subset of colonies. Additionally, ColTapp automatically generates some lists with certain functions (e.g. detecting close centers or reported failure of kymograph derived radius, see [Time-lapse] (https://coltapp.github.io/timelapse.html) page). The currently active list is displayed in the dropdown menu and can be changed there. By clicking on the entry _new_, a new user-named list is generated.
The _+/-_ button allows to add/remove colonies to/from the active list by clicking at it.
