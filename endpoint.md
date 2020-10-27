---
layout: default
title: Endpoint
---
# Endpoint sequence

Functions specific for endpoint image analysis can be found in the **Main-EP** tab.
<figure>
  <img src="{{site.url}}/assets/images/EP0.png" alt="Endpoint tab of GUI" height="620px"/>
  <figcaption>Endpoint tab of ColTapp GUI. Part of Fig. S1 of the publication </figcaption>
</figure>
Some very late appearing colonies may not be observed at the optimal time for colony size observation (e.g. 24h). In that case, we suggest capturing image(s) at later timepoint(s) (e.g. 48h). ColTapp allows the user to overlay images (tickbox _a_) taken from the same plate at different times to ease detection of very late growing colonies which did not yet appear at an earlier timepoint. ColTapp assumes that a folder under analysis contains multiple images from the same timepoint and requires the user, upon the first engangement of the _Overlay_ tickbox, to navigate to a folder containing the same set of images with matching order, acquired at another timepoint. If multiple folders are linked (see below), the image folder for the overlay can be selected with the dropdown-menu (_a_).
The colonies visible on later timepoint but not on the currently loaded main folder can be marked as colonies with a radius of 0 pixel (Button _b_ or shortcut _n_).

To achieve similar image orientation at both timepoints during photography, the user may place a mark on the edge of the plate as reference. Users can manually align images which have not been captured in the exact same orientation by clicking at two matching positions on the images of the two (or more) timepoints (Button _e_). The inbuilt MATLAB function fitgeotrans is used to fit a geometric transformation to the pairs of points with a nonreflective similarity to estimate rotation and translation of the two images to align.


