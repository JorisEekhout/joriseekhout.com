+++
presentation_type = "1"

project = "juan-de-la-cierva-incorporacion"
authors = ["**JPC Eekhout**"]
date = "2023-10-10"
title = "Soil erosion and river morphodynamics in SPHY"
description = "Oral presentation Soil erosion and river morphodynamics in SPHY"

location = "SPHY User Days, Wageningen, the Netherlands"
dates = "October 10-11"

abstract = ""

captions = ["In this presentation I will show the results of two studies in the context of the impact of climate change on soil erosion, which involved new additions to the SPHY model.", 
"Previously we implemented the Morgan-Morgan-Finney (MMF) process-based soil erosion model in SPHY, which accounts for the most relevant soil erosion processes. We also implemented a sediment transport module, accounting for reservoir sedimentation.", 
"The MMF model accounts mostly for small-scale erosion processes, such as sheet and rill erosion. The first part of the presentation will focus on these smaller scale processes, while the second part will be on larger scale processes, such as gully and channel erosion.", 
"Climate change impact assessments involve much uncertainty, which is summarized here in the uncertainty cascade, including uncertainty from climate models, post-processing of climate data, hydrological models and soil erosion models.", 
"We try to quantify this uncertainty by applying SPHY in climate change impact assessments. For instance, bias-correction methods could lead to decreasing or increasing soil erosion, which also happens to individual climate models.", 
"Soil erosion models also account for much uncertainty, where some models project decreasing and other increasing erosion rates, depending on the model concept.", 
"This uncertainty can be accounted for by using model ensembles, such as climate model ensembles and hydrological model ensembles. That is why we thought it would be interesting to apply this also for soil erosion models.", 
"We implemented a soil erosion model ensemble in SPHY, which consisted of 5 process-based soil erosion models. The implementation involved some modifications related to ponding, water depth calculations and ground cover.", 
"We applied the model ensemble to a semi-arid catchment in southeast Spain. The land cover is dominated by natural vegetation, where about 1/3 is used for agriculture.", 
"This slide shows the results of the reference scenario, in which we determined the ensemble median from the individual soil erosion maps obtained from the 5 models. High erosion rates are obtained from agricultural areas, while natural cover shows lower rates.", 
"We quantified the model uncertainty using the coefficient of dispersion, which show high values where uncertainty is high. After detailed analysis we found that uncertainty is correlated with slope, which is related to differences in model assumptions.", 
"Then we applied the model to climate change scenarios, where we obtained decreasing soil erosion when annual and extreme precipitation decreases and vice versa. In both cases uncertainty increases, which urges the use of model ensembles in climate change impact assessments.", 
"Initially we tried to account for large-scale erosion processes by forcing the soil erosion model by accumulated runoff, which gave unrealstically high erosion rates. This was fixed by turning off the runoff processes for large upstream areas. Still we wanted to account for these processes.", 
"Therefore, we changed the SPHY model, where sheet erosion is obtained from MMF forced by local erosion. Sediment will be transported through the catchment through rills and channels, while accounting for erosion and deposition in these two model domains.", 
"We initially implemented a simple sediment transport equation forced by discharge. However, more advanced equations were needed, which were functions of water depth and flow velocity, not accounted for by the SPHY model.", 
"So we updated the water routing using the travel time algorithm from PCRaster. This function needs flow direction, channel storage and flow velocity as input. The channel storage is obtained as the sum of the channel storage from the previous time step and the local runoff.", 
"The flow velocity is obtained from the water depth, which is a function of the discharge. We used an iteration to obtain the discharge, where the iteration stops when the discharge difference between two iteration is smaller than a threshold (model parameter).", 
"Channel dimensions are needed to apply the travel time algorithm, including channel width and depth, and floodplain width. Also the Manning's roughness for the channel and floodplain are needed and a map that differentiates between hillslope and channel cells.", 
"We implemented two sediment transport equations for rills and three for channels. The morphodynamics module is based on the accucapacity algorithm from PCRaster, which requires sediment storage and transport capacity as input.", 
"The model accounts for sedimentation of reservoirs and check dams, for which we revised the existing algorithm in SPHY.", 
"We applied the new model to a Mediterranean catchment in southeast Spain. I will show the results of a land use change scenario in the Rogativa subcatchment, which is characterized by reforestation and check dam construction between 1956 and 2016.", 
"In 1956, sheet erosion accounted most to the sediment balance, while the majority of the sediment was deposited in the rills. Channel erosion accounted for about 50% to the sediment yield at the catchment outlet.", 
"Reforestation caused a decrease in sheet erosion, but also in channel erosion because of a reduction in runoff due to increased evapotranspiration. Check dam construction was mostly responsible for the 80% decrease in sediment yield at the catchment outlet.", 
"This slide summarizes the work on the soil erosion model ensemble and channel processes as implemented in the SPHY model. We also implemented an irrigation module, re-infiltration, an input utility and made modifications to the NetCDF input utility."]
+++