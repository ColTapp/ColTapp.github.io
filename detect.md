---
layout: default
title: Colony detection
---
# Colony detection
The detection tab of ColTapp includes functions to find colonies on plates and many auxilliary functions.
<figure>
  <img src="{{site.url}}/assets/images/Detect_1.png" alt="Detection tab" height="550px"/>
  <figcaption>GUI overview (modified Fig S1 from manuscript) </figcaption>
</figure>

### Grayscale image quality (*c*)
Mainly for visualization and manual correction of detected colonies, the grayscale images can be enhanced with either an auto-contrast toggle (*c*) or using a lighting correction algorithm to remove glares and flares (see example below).
<figure>
  <img src="{{site.url}}/assets/images/Detect_3.png" alt="Image enhancement" height="450px"/>
  <figcaption> Image enhancement (c) </figcaption>
</figure>

### Detect colonies (*d*)
Automatic colony detection can be started with the _Find Colonies_ button (*d*). If in _TL_ mode, the function is executed on the current frame while in _EP_ mode, the user is asked to enter the frames on which the colony search should be executed. Accuracy and computational speed can be increased by specifying a narrow range of minimal and maximal radius. The range can be specified either by inserting values in pixel in _Options_ or can be derived automatically from the smallest and biggest circle drawn on the currently displayed image with the button _Define radius range_ (*d*).
Refer to the [manuscript](https://doi.org/10.1038/s41598-020-72979-4) for details on the image analysis steps used.

### Manual correction of detected colonies (*e*)
Addition of non-detected colonies and false positive removal is possible through simple mouse-guided operations (*e*). Addition can be activated by either the button _(C) Add_ or the indicated shortcut _C_. Left-click on a colony center, hold and drag shown circle to border of colony, release and click once to confirm. Additionally, if the tickbox _Add/Remove with click_ is activated, colony addition can directly be started with a left-click on the colony center (hold and drag as described above).
Individual circles can be removed with the button _(R) Remove_ or the indicated shortcut _R_. When the crosshair appears, left-click inside a circle to remove it. Additionally, if the tickbox _Add/Remove with click_ is activated, a scroll-wheel (middle mouse button) click inside a circle removes it. Removal of entire zones can be started with the button _(T) Clear in_ or the indicated shortcut _T_. Place edges of a polygon on the image with left-clicks and confirm with a double-click. Removal of all circles outside of a drawn polygon can be started with the button _(Z) Clear out_ or the indicated shortcut _Z_.
The button _(backslash) Undo_ or the indicated shortcut _backslash_ is used to undo up to seven of the last colony addition/removal steps.

### Generating lists of colonies (*f*)
ColTapp allows to group colonies into lists to use certain downstream functions only on the indicated subset of colonies. Additionally, ColTapp automatically generates some lists with certain functions (e.g. detecting close centers or reported failure of kymograph derived radius, see [Time-lapse](https://coltapp.github.io/timelapse.html) page). The currently active list is displayed in the dropdown menu and can be changed there. By clicking on the entry _new_, a new user-named list is generated.
The _+/-_ button allows to add/remove colonies to/from the active list by clicking at it.
