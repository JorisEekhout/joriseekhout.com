---
title: "Large-scale Soil Erosion Modeling"
date: 2019-06-15
draft: true
twitter_img: "img/blog/catchment_TC_SY.png"
---

**Recently, I have published a few articles on the impact of climate change on water security and potential adaptation strategies. The backbone of these articles is the SPHY model we have developed over the last few years. In this blog post I will tell how we developed the model and how we applied the model to the Segura catchment. Please check out all related articles in the [Publications section](/publications/).**

In 2015 I started as a postdoctoral researcher at the [Soil and Water Conservation Research Group](http://www.soilwaterconservation.es/) (CEBAS-CSIC). I was contracted on the [ADAPT project](/projects/adapt/), which aimed to evaluate climate change adaptation through Sustainable Land Management (SLM), with a focus on both hydrology and soil erosion. The study was performed in a large-scale Mediterranean catchment (the Segura River catchment, Southeast Spain). Before I started working on this project, I did not have much experience in modeling. During my PhD, I only gained experience with some hydrodynamic models, such as Delft-3D and SOBEK-1D. Within the ADAPT project, we wanted to apply a large-scale hydrological model, coupled with a soil erosion model, which were both new subjects for me. Through a collaboration with the Dutch-Spanish consultancy company [FutureWater](https://www.futurewater.eu/) we decided to apply the [SPHY](http://www.sphy.nl/) model, a spatially-distributed process-based hydrological model. So we had one part of the objective covered.

{{< figure src="/img/blog/sphy.png" alt="SPHY model">}}

In a previous FutureWater project, the SPHY model was already equipped with the MUSLE soil erosion model. Initially we thought that the MUSLE soil erosion model could be well enough to do the job. However, this model has some disadvantages. It is an empirical model and therefore does not fit well within the process-based SPHY model. Also many input variables are ill-defined. So as time passed, I was getting more and more in favor of coupling a process-based soil erosion model to the SPHY model. We found the Morgan-Morgan-Finney (MMF) soil erosion model, which fitted much better within the SPHY model. Implementation of the MMF model into SPHY was not that difficult, especially since I got some experience in changing other aspects of the SPHY model (written in [Python](https://www.python.org/) and [PCRaster](http://pcraster.geo.uu.nl/)). In 2018 the [SPHY-MMF](https://doi.org/10.5194/esurf-6-687-2018) model saw the light. See the video abstract below to get an impression of the main features of the new soil erosion module. 

<div class="video__embeded u-margin-top-small u-margin-bottom-small">
    <iframe class="video__iframe" src="https://www.youtube.com/embed/yP1o5w3VEN8" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
</div>

Process-based soil erosion models are often thought of being data demanding. While you certainly need some data to apply the SPHY-MMF model, most datasets are already demanded by the hydrological model, such as climate forcing, a digital elevation model, soil properties and a land use map. For the soil erosion module only land use-specific data is required, for instance plant height and stem density. Other input data are obtained from the hydrological model, including canopy cover and precipitation (throughfall). Therefore, the SPHY-MMF model can be applied to any environment. 

{{< figure src="/img/blog/catchment_TC_SY.png" alt="Catchment processes in the SPHY-MMF model">}}

Like with all models, some parts of the model is better represented than others. Like the figure shown here, the model accounts for sediment transport in the rivers. Currently, the soil erosion modules overestimates erosion in the river cells. One of the future plans is to develop a channel erosion module, which should improve channel erosion estimates. Furthermore, for the European Horizon 2020 project [COASTAL](https://marmenorcoastal.wordpress.com/), we want to apply the SPHY model to the Campo de Cartagena catchment. For this application, we are thinking to develop a irrigation module and nutrient transport module. These modules are very relevant for catchments with a lot of irrigated crops, such as the Campo de Cartagena catchment.

**The SPHY-MMF model is launched as SPHY v3.0, which also includes improvements related to glacier processes, plant water stress, open-water evaporation and surface runoff. The model is available from the [SPHY Github repository](https://github.com/FutureWater/SPHY). See [this presentation](/presentations/2019-sphy-user-day/) I gave during the first SPHY User Day, for an overview of the main improvements I have made to SPHY v3.0.**