---
layout: default
title: Options
---
# Options

The default parameters of each functionality of ColTapp can be tuned by the user within the _Options_. 

The _Options_ window is divided into four tabs : _Global_, _Detect_, _Main_ (_TL_ or _EP_) and _Visualize_. The latter tabs regroup parameters corresponding to each of the main panels' corresponding tab, the first tab, _Global_ (left on the following figure), regroups all parameters which apply globally, whatever the analysis step.

## Global

### Color to grayscale method selection
Colored RGB images are transformed into grayscale images for many image analysis steps (colony detection, colony kymograph derivation from time-lapse images). ColTapp offers 16 different methods for grayscale conversion. 
Using one of the three RGB channels is computationally quick and generally precise enough, but in some special cases, the user may want to use a different conversion, as for example a transformation to other classical color spaces (e.g. CIELAB) and using one of the generated channels. The inbuilt MATLAB function rgb2gray which uses a weighted image conversion, retaining information of all three color channels, is also available. With "Select RGB to grayscale method from examples" the user may visualize the result of each different method (as shown in the right panel of the following Figure) and select the most appropriate method.
<figure>
  <img src="{{site.url}}/assets/images/Options_Global_wGrayscale.png" alt="Global tab" height="800px"/>
  <figcaption> Global tab of the Options (Part of Fig. S2 of the publication) and grayscale conversion methods </figcaption>
</figure>

### Visualize on image
- The user can use toggles to chose which data should be visualized directly on the images in the main panel.
<figure>
  <img src="{{site.url}}/assets/images/Visualize_on_image.png" alt="Visualize on image" height="70%"/>
  <figcaption> Visualization on main panel image </figcaption>
</figure>
- The _Redefine lighting correction area_ button allows a user to chose a new subset of the image as input to the [lighting correction algorithm](https://coltapp.github.io/detect.html).

### Reference growth data
When extracted automatically from an analyzed control experiment, the [reference appearance time](https://coltapp.github.io/refparam.html) of that experiment is 
averaged using the mean, by default. Yet, users concerned by the presence of outliers in the growth control experiment may chose to use the median (or any user-defined quantile) via this tab.

### Save options
Autosave, back-up save

### Reset active list
ColTapp allows to group colonies into [lists](https://coltapp.github.io/detect.html) to use certain downstream functions only on the indicated subset of colonies. User can remove all colonies from the active list on the main panel with this button.

## Detect

### Image preprocessing
- Default:Adaptive, Global, none
- Binarization sensitivity
- Should the user want to detect white colonies on a darker background,

### Colony detection parameters
- The _Circle detection_ mode (Regionprops or direct) (default: Regionprops)
- The _imfindcircle sensitivity_ (default:0.94)
- The _Minimal Radius_ (default:20 pixels)
- The _Maximal Radius_ (default:65 pixels)
- The _Scale bounding box_ (default:1.35)
- The _Min distance from border_ (default:10 pixels)
- The _Foreground bias_ (default:0.17)
- The _Min area foreground_ is the proportion (default:0.7)
- The _Max overlap (2 circles)_ is the proportion (default:0.9)
- The _Min rad difference_ (default:10 pixels)
- The _Min center distance_ (default:20 pixels)
- The _Max total overlap_ is the proportion (default:0.95)
- The _Start iterative overlap_ is the proportion (default:0.8)
- The _Final min center distance_ (default:2 pixels)


## Main-TL

### Define radii-tracking parameters
- The _Reference frame_, on which colonies are found and from which the radii are tracked on the other frames, is set to the last frame of the time-lapse by default. 
- The _Time interval_ between frames of a time-lapse serie is automatically detected upon import and if this automatical detection fails, the user is asked to define it. 
- The _Registration factor_ (κ) defines the subpixels resolution (1/κ) at which the image registration algorithm performs a 2-D rigid translation (default: 100)
- The _Kymograph threshold shift_ (default:0.17)
- The _Scale radius for overlap_ factor (default: 1) is multiplied to the radius of the focal colony from which [neighboring colonies are tested for overlap] (https://coltapp.github.io/timelapse.html). By increasing it (>1), ranges of angles corresponding not only to overlapping colonies but also very close colonies will be discarded from the kymograph creation process. Note that this increase might lead to high proportions of angles to be discarded. Decreasing the scaling factor (<1) leads to reduced ranges of excluded angles. This might be useful in densely populated plates to still achieve some overlap exclusion to increase quality of kymographs at earlier timepoints. Note that if more than 90% of all angles are discarded because of overlap, the exclusion of angles is omitted completely, to avoid reducing the available data too much. 
- This overlap detection functionality can be completely removed by the user by ticking the _overlap exclusion_ tickbox.
- The images can be transformed with the lighting correction algorithm in the [_Detect_ tab ](https://coltapp.github.io/detect.html). The resulting enhanced images are typically meant to improve visualization for the user, and by default not used downstream for image analysis. However, a user can tick the box _Use enhance images_ if willing to use these transformed images as input for the _Radii tracking_ algorithm.

### Define appearance time parameters

- The _Apperance time threshold mode_ defines the unit of the threshold a colony radius should reach for the colony to be macroscopically detectable. (default: micrometers)
- The _Detection threshold radius_ defines the value of the threshold a colony radius should reach for the colony to be macroscopically detectable. (default: 200)
- The _Number of frames for fit_ (default: 50)

### Additional possibilities
- _Process timelapse subset_
- _Manually process timelapse_
- _Recalculate kymograph radius_
- _Select curves to delete_ 
- _Restore deleted curves_
- _Reset registration_
- _Delete radius data of selected frames_
- _Scale detected radius_

## Main-EP
### Additional possibilities
- _Apply spatial calibration factor to all frames_
- _Apply area of interest to all frames_
- _Apply both to all frames_
- _Remove linked and overlay folders_

## Visualize

After analyzing a time-lapse series, a quick visualization of the colony growth curves can be displayed by clicking on the _Radius vs Time_ button of the _Visualize_ tab of the main panel. In the _Options_ the user may chose to plot these curves 1) in raw units: pixels/frame or 2) in more biologically meaninful units, i.e micrometers/time. A user may also chose 3) a log-y axis, as this could enable to visualize an exponential curve as a linear slope (typically if the first growth phase is macroscopically detectable, which is not the case in the following example.
<figure>
  <img src="{{site.url}}/assets/images/Options_Visualize.png" alt="Options Visualize" height="70%"/>
    <figcaption> Visualize tab of the Options and example of colony growth curves visualization</figcaption> 
</figure>

In addition, the user can chose to visualize the colony size distribution on a given (or multiple) frame(s) with an histogram. The parameter _number of histogram bins_ can be inputted by the user.

