# SedimentFlux_ConMods

README: ConMod Aeolian Sediment Transport and Litter Retention Data Repository
Overview

This repository contains data and analysis related to the effects of Connectivity Modifiers (ConMods) on aeolian sediment transport and resource retention in dryland environments. ConMods are galvanized mesh structures designed to disrupt sediment transport pathways and enhance site stability by reducing wind-driven soil loss and increasing litter retention. The data and associated scripts provide insights into how ConMod porosity, height, and spacing influence horizontal sediment flux, based on model simulations and field experiments.

Data Collection & Modeling Approach

Aeolian Sediment Transport Modeling

Aeolian sediment transport was estimated using the Aeolian EROsion (AERO) model (Edwards et al., 2022), which predicts horizontal sediment flux based on surface wind friction velocity and the threshold shear velocity of soil particles. The model was parameterized using a Generalized Likelihood Uncertainty Estimation (GLUE) framework with data from the National Wind Erosion Research Network (Webb et al., 2016).
To determine the optimal ConMod height, porosity, and spacing, a Latin Hypercube Sampling (LHS) approach was used to generate 1,000 unique parameter sets, which were then used to parameterize the model. Simulations were conducted across a range of wind speeds (8-20 m/s) with site-specific soil characteristics from a location on the Colorado Plateau.

The shear velocity ratio for ConMods was determined using published literature on porous fences (Lima et al., 2017; Li & Sherman, 2015; Bradley & Mulhearn, 1983). Model output includes horizontal sediment flux (g m⁻¹ d⁻¹) under various ConMod configurations, allowing assessment of the potential for reducing wind-driven soil erosion.

Litter Retention Field Experiment

To assess the effects of ConMods on within-site resource retention, data from a 2016 field experiment in Canyonlands National Park (Fick et al., 2016) was analyzed. This study measured litter depth in bare ground plots with and without ConMods. Litter depth was recorded at two sampling periods (June 2014 and October 2014) and analyzed using one-way ANOVA to test for treatment effects.

Repository Contents

This repository includes both data files and analysis scripts for processing and visualizing results.

Data Files
1.	conmod_full_dataset.xlsx – Full dataset of horizontal sediment flux predictions across different ConMod parameter configurations.
2.	litter_capture_data.csv – Field data on litter retention in ConMod and bare ground plots.
3.	metadata_conmod_full_dataset.xlsx – Metadata describing the variables and structure of the conmod_full_dataset.xlsx file.
4.	metadata_litter_capture_data.xlsx – Metadata describing the litter_capture_data.csv file.

Analysis Scripts
1.	Horizontal_sediment_flux_graph.R – R script for visualizing reductions in horizontal sediment flux under different ConMod configurations.
2.	Marginal_distribution_graph.R – R script for analyzing parameter sensitivity and marginal distributions of model outputs.
3.	latinhypercubed_code.R – R script for generating Latin Hypercube Sampling (LHS) parameter sets.
4.	porosity_shearstrength_code.Rmd – R Markdown script for estimating shear velocity ratios based on ConMod porosity.

How to Use This Repository
1.	Explore the Data
o	Open metadata_conmod_full_dataset.xlsx and metadata_litter_capture_data.xlsx to understand the dataset structure.
o	Load conmod_full_dataset.xlsx for outputs of aeolian sediment flux.
o	Load litter_capture_data.csv for field-based comparisons of litter retention.
2.	Run Analysis Scripts
o	Use Horizontal_sediment_flux_graph.R and Marginal_distribution_graph.R to visualize sediment transport reductions.
o	Use latinhypercubed_code.R to regenerate parameter distributions if needed.
3.	Reproduce Model Simulations
o	Modify inputs in the porosity_shearstrength_code.Rmd script to explore alternative parameterizations of shear velocity effects.

Limitations & Considerations
•	The AERO model does not explicitly calculate net soil loss, as it does not account for deposition processes. Sediment flux estimates should be interpreted as indicators of erosion potential rather than absolute soil loss values.
•	Litter retention data were collected in a controlled experimental setting, and results may not directly translate to all field conditions.
•	The model assumes unvegetated conditions between ConMods; natural vegetation effects are not explicitly incorporated.

References

•	Bradley, E. F., & Mulhearn, P. J. (1983). Field measurements of the flux of wind-blown sand. Boundary-Layer Meteorology, 25(1), 167-191.
•	Edwards, B. L., et al. (2022). Parameterizing wind erosion models for rangelands: A process-based approach. Journal of Arid Environments, 198, 104693.
•	Fick, S. E., et al. (2016). Vegetation and sediment trapping effectiveness of artificial windbreaks in drylands. Geomorphology, 273, 345-356.
•	Gillan, J. K., et al. (2016). Wind erosion and dust emission impacts from off-road vehicle activity in a Mojave Desert shrubland. Aeolian Research, 21, 65-76.
•	Li, B., & Sherman, D. J. (2015). Aerodynamic and sediment transport characteristics of porous fences. Geomorphology, 245, 76-85.
•	Lima, A. R., et al. (2017). Effects of porosity on wind sheltering efficiency of artificial barriers. Environmental Fluid Mechanics, 17(4), 659-675.
•	Okin, G. S. (2008). A new model of wind erosion in the presence of vegetation. Journal of Geophysical Research: Earth Surface, 113(F2).
•	Webb, N. P., et al. (2016). The National Wind Erosion Research Network: Building a standardized long-term dust monitoring program. Aeolian Research, 22, 23-36.
