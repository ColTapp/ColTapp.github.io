---
layout: default
title: Time-lapse
---
#*__still under construction__*

# Radius tracking (time-lapse)
ColTapp can track the radius of detected colonies through time on time-lapse image series. First, all colonies need to be [detected]({{site.url}}/detect.html) on the latest (or a late) frame in a time-lapse series. All time-lapse associated functions are accessible through a dedicated tab on the GUI. The buttons are labeled with letters and text on this page referring to buttons uses these letters.
<figure>
  <img src="{{site.url}}/assets/images/TL0.png" alt="Time-lapse tab of GUI" height="620px"/>
  <figcaption>Time-lapse tab of ColTapp GUI. Part of Fig. S1 of the publication </figcaption>
</figure>

### Image drift correction (registration)
ColTapp can correct for slight image drift occuring in time-lapse imaging. This process is called image registration. The correction is not applied to the images themselves but to the detected centers of each colony resulting in a center for each colony and frame. Therefore, it is important that all colonies of interest are already detected before the drift correction is enabled. Enable and disable the drift correction with the toggle _a Registration_. To improve speed of the registration calculation, the user is asked to draw a small rectangular area on the image which is subsequentially used to automatically detect image drift. It is suggested to select a part of the image which includes clear edges (e.g. border of an agar plate) and does **not** include any changing parts (e.g. colonies). If the registration should be re-calculated, the user can remove the stored registration vector via _Options/ Main-TL tab/ Reset registration_.

### Colony center correction
The centering of colony circles is crucial to track radii over time, especially at early timepoints when colonies are small. It is strongly suggested to turn on _Autoconstrast_ or, even better, _Improve lighting_ which can be accessed in the _Detect_ tab of the GUI. ColTapp offers an automatic center correction, by tentatively detecting circles on sub-images cropped from an early frame based on the location and radii of the colonies detected on the reference frame. These newly detected circles’ center coordinates are kept as colony center, unless they are farther away than a user-defined threshold from the original coordinates or if they are set to the center coordinates of another colony in close proximity. In these cases, the correction is skipped, and the colonies are added to a list for subsequent manual center correction. If no circle is detected at all because the colony is not yet visible at that timepoint, the same process is repeated 10 frames later. The user is able to monitor this process visually. The green circle is the one chosen by ColTapp as the correct center, red circles are discarded.
<figure>
  <img src="{{site.url}}/assets/images/TL2.png" alt="Center correction example" height="467px"/>
  <figcaption>Time-lapse Visualization of the automatic center correction. </figcaption>
</figure>

If the automatic c
#*__still under construction__*
