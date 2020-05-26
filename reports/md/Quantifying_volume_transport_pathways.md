# Quantifying volume transports along pathways crossing Greenland-Shetland section in the VIKING20X model using Lagrangian particle tracking: a preliminary study.

The method relies on the idea that we can associate a volume transport with a particle, and that this volume transport remains constant (or changes only slowly) as we follow the particle. So like a streamtube.

This assumption is possibly only strictly valid in the absence of mixing, and possibly only for the mean flow, but anyway.. 

First, consider how to sample the velocity field with particles to accurately estimate the transport across a section, and enable us to track the volume transport upstream and downstream.

Each particle, $m$, has an associated volume transport, $V_m$, across the section given by:

$$ V_m = A_m \boldsymbol{{v_0}_m \cdot n_m}, $$


where $A_m$, $\boldsymbol{{v_0}_m}$, and $\boldsymbol{n_m}$ are the section area associated with particle $m$, the velocity, and the unit vector normal to the section at the point where particle $m$ crosses the section. 

Summing over $M$ particles gives total volume transport across the section of:

$$ V = \sum_{m=1}^{M} (A_m \boldsymbol{{v_0}_m \cdot n_m})$$

The $A_m$ depend on the initial distribution of particles on the section. We will distribute our particles randomly in x and z, and assume we have enough particles such that 

$$ A_m = \frac{A}{M}, \forall \ particles \ m$$

where A is the total section area.

## Greenland-Shetland section

The section is divided into three subsections, Greenland-Iceland, Iceland-Faroe, and Faroe-Shetland (haven't yet included Shetland-Scotland) as in the figure below, each will be treated separately.

![](https://i.imgur.com/h77Bzze.png)

> Figure 1 Greenland-Iceland-Faroe-Shetland(-Scotland) section.

## Viking20x model transports.

Before doing any particle tracking I tested whether the method of estimating transports outlined above could accurately reproduce the transports at the section. The comparison is shown in Figure 2, releasing 4000 particles on each subsection.

![](https://i.imgur.com/gFdBUgc.png)

> Figure 2 Volume transport across Iceland-Faroe and Faroe-Shetland subsections. Solid lines -- full calculation from model monthly mean fields, crosses -- estimate from random particle sample of 4000 particles. The low bias in Faroe-Shetland volume transport may be because the same random sampling has been used each month.

This suggests that using particle sampling to estimate the volume transport across through the section is a reasonable approach. The monthly variability is being captured. Possibly more particles should be used. Having said that, the following analysis uses fewer, 2000, particles on each subsection.

## Particle releases

Particles (2000) were released along each  subsection twice a year for the years 2014-2016 and tracked using the OceanParcels particle tracking model, including only advection and using Viking20x monthly mean velocity 3D velocity fields. Mid-June and mid-December release times were chosed as there appeared to be a seasonal cycle in the volume transports across the section with minima and maxima at these times. Example particle releases for each subsection are in Figure 3.

![](https://i.imgur.com/g7LboGy.png)
> Figure 3a Greenland-Iceland

![](https://i.imgur.com/fVfcBBs.png)
> Figure 3b Iceland-Faroe

![](https://i.imgur.com/1wRCU8v.png)
> Figure 3c Faroe-Shetland

Particles were run forwards for two years and backwards for two years from these release sites to identify the main sources and destinations with emphasis here being put on the northward branch of the circulation from the Atlantic to the Arctic.

## Particle tracks and animations

Plotting particle tracks and animations, gives an idea of the main northward routes. These run from the NE Atlantic, across our section through all three subsections, then northwards into the Nordic Seas along the Norwegian coast. Tracks of particles crossing each subsection are plotted in Figure 4. The animations are in separate files. In the animations particles are coloured by temperature, with sizes proportional to the volume transport associated with each particle.

![](https://i.imgur.com/NR3ESXn.png)
> Figure 4a. Particles crossing Greenland-Iceland subsection on 16 December 2014. All tracks. Particles are coloured by time with a 4-year scale. The crossing time is the mid-point of the scale.

![](https://i.imgur.com/vw7dTbd.png)
> Figure 4b. Particles crossing Greenland-Iceland subsection on 16 December 2014. Coming from the south through the Rockall Trough or west of Rockall, destination Nordic Seas.

![](https://i.imgur.com/Yydk4hK.png)
> Figure 4c. Particles crossing Iceland-Faroe subsection on 16 December 2016. All tracks. 

![](https://i.imgur.com/TCIYTNV.png)
> Figure 4c. Particles crossing Iceland-Faroe subsection on 16 December 2016. Coming from the south through the Rockall Trough or west of Rockall, destination Nordic Seas. 

![](https://i.imgur.com/lHvctiu.png)
> Figure 4e. Particles crossing Faroe-Shetland Channel on 16 December 2014. All tracks.

![](https://i.imgur.com/HgQj0o8.png)
> Figure 4f. Particles crossing Faroe-Shetland Channel on 16 December 2014. Coming from the south through the Rockall Trough or west of Rockall, destination Nordic Seas.


## Pathways of particles crossing the ridge

Examining the routes taken by particles, we can identify the main sources and destinations and display the particles as they cross the section coloured by source and destination region (Figure 4)

![](https://i.imgur.com/iwDB19j.png)
>Figure 4a Greenland-Iceland

![](https://i.imgur.com/thIkugn.png)
>Figure 4b Iceland-Faroe (top panel velocities, lower panel by source and destination)

![](https://i.imgur.com/O8Z2UrZ.png)
>Figure 4c Faroe-Shetland (top panel velocities, lower panel by source and destination)

## Quantifying transports by pathway

If we are carefull to count particles only on the subsection where they are first crossing the section (some tracks cross repeatedly in the four years modelled), and focussing on the northward flow, we can divide the tracks into two source regions: passing east and west of Rockall. This then gives the transport timeseries in Figure 5.

![](https://i.imgur.com/XW7xxQP.png)
>Figure 5 Northward transports across Greenland-Shetland section split by pathway west and east of Rockall.

The general picture is of approximately equal volumes of the water which ultimately reaches the Nordic seas travelling on pathways east and west of Rockall. The Faroe-Shetland Channel flow is dominated by the east Rockall pathways, the Iceland-Faroe subsection by west Rockall pathways, and the Greenland-Iceland northward transports are comparatively small.

## Next steps

The method of using the particle tracking to quantify transport along different pathways looks promising from these results. I think we are getting pathway information which is not provided by Eulerian analysis of transports across sections and volume budgets. Although Eulerian analysis with volume transports divided on isopycnal layers might provide similar results? There is clearly a 3-dimensional component to the transports, with some part (may 10-20%) of the northward flow through the Rockall Trough crossing flow from west of Rockall to enter the Nordic Seas across the Iceland-Faroe Ridge, and similarly for west Rockall flows crossing through the Faroe-Shetland Channel.

More particles are needed for more reliable results. As I'm not adding any diffusion to the tracks it will probably then be more efficient to use Ariane rather than OceanParcels which I used here. 

I think we should expand the number of sections studied, perhaps also releasing particles on a southern boundary at the OSNAP line and examining the model transports and pathways in and out of the bounded area. By recording temperature and salinity along tracks we can possibly also say something about heat and 'freshwater' transport pathways.

I'm not sure if any of this suggests different, or additional, areas where observations could be focussed to observe the overturning circulation. Most of the critical sections I think already have mooring arrays, although I was struck by the focus of northward flow to the Iceland-Faroe subsection and west through a narrow section west of outer Bailey (around 60.7N, 14.5W). Possibly most easily seen in the animations.

I haven't compared these results to observations or to other modelling results yet.








