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


#*__still under construction__*
