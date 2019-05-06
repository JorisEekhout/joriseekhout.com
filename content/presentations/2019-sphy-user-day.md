+++
presentation_type = "1"

project = "juan-de-la-cierva"
authors = ["JPC Eekhout", "J de Vente"]
date = "2019-03-18"
title = "SPHY v3.0: What’s new?"
description = "Oral presentation SPHY v3.0: What’s new?"

location = "SPHY-model User Day, Wageningen, The Netherlands"
dates = "March 18"

abstract = ""

captions = ["In this presentation we show the most important changes we have made to the SPHY model, which ultimately will be released as SPHY v3.0.",
"Here I will show changes to the model structure, two new modules, several new process formulations, new utilities and some future plans",
"The new structure contains of three folders, i.e. the root folder with all the code that is essential to run the model, the modules folder with modules that can be switched on or off, and the utilities folder with some stand-alone tools",
"Our main contribution to the SPHY model was the development of two new modules. The soil erosion module is based on the Morgan-Morgan-Finney model and simulates three soil erosion processes: detachment by raindrop impact, detachment by runoff and immediate deposition", 
"In the calculation of the deposition, the model accounts for soil roughness (bare soil or tilled soil) and for vegetation roughness that can be obtained from regular-spaced vegetation, with stem density and stem diameter as input, or from irregular vegetation, with the Manning's coefficient as input", 
"Sediment is transported through the catchment based on the transport capacity of the flow, which is determined from a roughness coefficient, the accumulated runoff and slope. Sediment is deposited when the flux is larger than the transport capacity",
"In the case of reservoirs, the sediment is trapped at the reservoir with a reservoir specific trapping efficiency",
"Since soil erosion often occurs during high intensity rainfall events, we implemented infilitration excess surface runoff. The infiltration capacity is inspired by the Green-Ampt formula and is mainly obtained from soil hydraulic properties. We included a parameter (alpha) that sets the fraction of the daily rainfall in the hour with the highest intensity, which is needed to determine surface runoff",
"Actual evapotranspiration is determined from the potential evapotranspiration, multiplied by two factors. Originally, the reduction factor for dry conditions is determined with this equation, with the actual soil moisture, wilting point and permanent wilting point as input. The wilting point is only soil dependent, it is determined from pedotransferfunctions",
"In reality, it should also be vegetation dependent, because one species of plant can be in stress conditions under a certain soil moisture, while another species are not under stress. Therefore, we have implemented the plant water stress equation from Allen et al (1998) to account for plant specific stress conditions",
"The model now accounts for open-water evaporation. You will have to provide a map with the fraction open-water (0-1). Within the advanced routing module, the storage of the reservoirs and lakes is corrected for open-water evaporation",
"We have implemented pedotransferfunctions from Saxton and Rawls (2006), which need soil texture maps (sand and clay), organic matter and a bulk density factor for the root zone and subzone",
"Before, all reporting options were in a list at the end of the config file, which was a bit inconvenient. So we implemented a new way by means of a csv file and we also added some additional reporting options",
"We are planning to implement several modules to be able to apply SPHY in the Campo de Cartagena (Spain) for the COASTAL project (EU Horizon 2020). We will develop an irrigation and nutrient transport module. Furthermore, the soil erosion module overestimates soil erosion in channel cells, hence, we want to incorporate a better representation of channel erosion processes",
"Thanks you for your attention"]
+++