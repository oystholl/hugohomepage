+++
title = "Well Bore Stability Plots"
published = true
weight = 80
+++

![]({{< relref "" >}}images/plot-window/WellBoreStability.png)

ResInsight can create **Well Bore Stability** plots for Geomechanical cases. These plots are specialized [Well Log Plots]({{< relref "welllogsandplots" >}}) and contain a visualization of [Formations]({{< relref "formations" >}}), [Well Path Attributes]({{< relref "wellpaths" >}}#well-path-attributes) as well as a set of well path derived curves in two different tracks. 

The third track contains curves showing different stability gradients (all normalized by mud weight):

- **FG**: Fracture Gradient for sands based on Kirsch.
- **OBG**: Overburden stress gradient: Stress component S_33.
- **PP**: Pore pressure.
- **SFG**: Shear Failure Gradient for shale based on Stassi-d'Alia.
- **SH**: Minimum horizontal stress.

The fourth track contains curves showing the angular orientation of the well path as azimuth (deviation from vertical) and inclination (deviation from x-axis) in degrees.

These plots can be created from the context menu for a well path in the 3D view or from the the context menu of the Well Log Plots entry in the 2D Plot Window. In the former case the well bore stability plot will be created for the selected **Well Path**. In the latter case it will be created for the first well path in the well path list and the well path for the entire plot can be changed with the [Change Data Source Feature]({{< relref "welllogsandplots" >}}#change-data-source-for-plots-and-curves).

In order to calculate **FG**  and **SFG** these curves the following input parameters are required:

| Curve | Required Parameters            |
|-------|--------------------------------|
|  FG   | Pore Pressure (PP), Poissons' Ratio |
|  SFG  | Uniaxial Compressive Strength (UCS) |

These parameters may be read in in the following ways. The numbering for import is order of preference if multiple sources are found.

| Parameter     | Default | Import mechanisms |
|---------------|---------|-------------------|
| PP | Hydrostatic PP (TVD x 9.81 / 100 bar) | 1. Grid (Grid units), 2. LAS-file as mud-weight (Variable: "PP", Units: kg / m^3), 3. Element Property Table (Variable: "POR", Units: Pascal)|
| Poissons' Ratio | 0.25 | 1. LAS-file (Variable: "POISSON_RATIO"), 2. Element Property Table (Variable: "POISSON_RATIO")|
| UCS             | 100 bar | 1. Las-file (Variable: "UCS", Units: bar), 2. Element Property Table (Variable: "UCS", Units: Pascal) |

![]({{< relref "" >}}images/plot-window/WellBoreStabilityCreation.png) ![]({{< relref "" >}}images/plot-window/WellBoreStabilityCreation2.png)
