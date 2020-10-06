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
The centering of colony circles is crucial to track radii over time, especially at early timepoints when colonies are small. ColTapps includes automatic and manual center corrections executable with the buttons under _b_. Beforehand, it is strongly suggested to turn on _Autoconstrast_ or, even better, _Improve lighting_ which can be accessed in the _Detect_ tab of the GUI.  ColTapp offers an automatic center correction, by tentatively detecting circles on sub-images cropped from an early frame based on the location and radii of the colonies detected on the reference frame. These newly detected circles’ center coordinates are kept as colony center, unless they are farther away than a user-defined threshold from the original coordinates or if they are set to the center coordinates of another colony in close proximity. In these cases, the correction is skipped, and the colonies are added to a list for subsequent manual center correction. If no circle is detected at all because the colony is not yet visible at that timepoint, the same process is repeated 10 frames later. The user is able to monitor this process visually. The green circle is the one chosen by ColTapp as the correct center, red circles are discarded.
<figure>
  <img src="{{site.url}}/assets/images/TL2.png" alt="Center correction example" height="467px"/>
  <figcaption>Visualization of the automatic center correction. </figcaption>
</figure>

If the automatic center correction failed, manual center correction is available (_b_). The user is presented with cropped sub-images of each colony and can click manually on the correct center of each colony. Buttons to add the displayed colony to a list of colonies for which the center correction should be repeated 10 frames before or later are displayed. The colonies of these lists will be automatically displayed afterwards.

### Radius tracking over time
After all colonies are detected (and optionally the registration is enabled and center correction finished), radius tracking can be started with a simple click on the button _c "Track radii over time"_. This calculates kymographs for each colony from which radius growth curves are derived.
<figure>
  <img src="{{site.url}}/assets/images/TL1.png" alt="Kymograph"/>
  <figcaption>A polar transformation from the center of a colony is applied to each subimage of a colony. These transformed images are then averaged and the images of each frame stitched together to ceate a kymograph. (Part of Fig. 7 of publication)</figcaption>
</figure>

### Overlapping colonies
Neighboring colonies can be visible as blurry regions in the top of kymographs, hindering creation of clean binary images.
<figure>
  <img src="{{site.url}}/assets/images/TL3.png" alt="Example of overlapping colonies exclusion" height="70%"/>
  <figcaption>Overlapping colonies can cause blurry regions in the upper right part of a kymograph. The angles corresponding to the overlapping region are automatically excluded from the radial average calculation (Part of Fig. 7 of publication)</figcaption>
</figure>
To reduce this phenomenon, before the kymograph creation process, overlapping colonies are automatically detected and the ranges of angles corresponding to adjacent colonies are discarded from the polar transformed intensity data. If more than 90% of all angles are discarded because of overlap, the exclusion of angles is omitted completely, to avoid reducing the available data too much. The overlap detection functionality can be deactivated or tuned with Scale radius for overlap (accessible in Options). This scaling factor is multiplied to the radius of the focal colony from which center neighboring colonies are tested for overlap: by increasing it, a user may choose to discard ranges of angles corresponding not only to overlapping colonies but also very close colonies. Note that this increase might lead to high proportions of angles to be discarded. Decreasing the scaling factor leads to reduced ranges of excluded angles. This might be useful in densely populated plates to still achieve some overlap exclusion to increase quality of kymographs at earlier timepoints.

#*__still under construction__*
