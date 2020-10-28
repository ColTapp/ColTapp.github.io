---
layout: default
title: Reference growth parameters
---
# Reference growth parameters
Since colony growth parameters (e.g. colony linear radial growth rate) depend on strain characteristic properties (e.g. cell-to-cell adhesion) and agar medium composition/physical properties, reference growth parameters need to be measured with a control dataset for comparative analyses.

The user can define the reference radial growth rate and appearance time either by providing known values manually, or by directing ColTapp to a folder containing a control experiment monitored by time-lapse and already analyzed, to extract these parameters automatically. In this case, ColTapp obtains the mean of appearance time and radial growth rates of the control experiment’s colonies. Users concerned by the presence of outliers in the growth control experiment may change the mean to median (or any user-defined quantile) in the [Options](https://coltapp.github.io/options.html). 

The reference radial growth rate may be used for [apperance time estimation from endpoint images](https://coltapp.github.io/endpoint.html). The reference appearance time  can be used for calibration of the raw appearance time in given experimental conditions.
