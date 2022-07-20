# cmip6-awicm-eke
Jupyter notebooks used to calculate and analyze eddy kinetic energy in AWI-CM-1-1-MR's CMIP6 simulations.

Some notebooks can run independently of others, some must be run in a certain order. An example order: geostrophy_calculations, merge_velocity_datasets, running_mean_anomalies, 
EKE_calcualtions, observational_period_modeled_EKE_calculations, observed_EKE_calcualtions, area_weighting, area-integrated_ocean_basins, any/all visualization notbooks.

## Data Prep and Calculations

### geostrophy_calculations
In this notebook geostrophic velocities are computed from modeled daily sea surface height data on an unstructure ocean grid. 

### merge_velocity_datasets
Geostrophic velocity calculations break down around the equator due to a negligible Coriolis parameter. In this notebook the geostrophic velocities between 3S and 3N calculated
in 'geostrophy_calculations' are replaced with interpolated monthly data available directly as model output.

### running_mean_anomalies
Anomaly calculations relative to a reference period mean are not representative of variability when the mean state shifts to a point at which the reference period mean is no
longer representative of typical conditions. To account for shifting patterns of ocean circulation, ocean surface velocity anomalies are calculated relative to a running mean.

### EKE_calculations
Ocean surface velocities are used to calculate eddy kinetic energy. A running mean is also applied to the data to mask seasonality in time series analysis. FInally the metadata
of each file is changed to reflect the calculations.

### observational_period_modeled_EKE_calculations
For comparison with observed EKE, modeled EKE over the diration of the satelite altimetry period (1993-2020) is calculated using the same reference period employed for the
observational dataset (1993-2012).

### observed_EKE_calcualtions
EKE is calculated using geostrophic velocity anomalies from satelite altimetry observations. The EKE data is then remapped to the FESOM grid for a consistent comparison with
the modeled data.

### area_weighting
Cell area information from the FESOM mesh is used to area-weight the EKE data.

### area-integrated_ocean_basins
Time series of area-integrated EKE are computed for each of the selected ocean basins.


## Visualizations

### fig2
The spatial patterns of simulated and observed EKE during the observational period (1993-2020) are plotted. The spatial patterns of simulated EKE change between the early historical period (1860-1949) and the end of the 21st century (2061-2090) are plotted.

### fig3
The area-integrated time series of each ocean basin are standardized and plotted. Includes both model ensembles and observations.

### fig4
The relationship between EKE and mean global surface temperature (MGST) rise is plotted. The rate of change of EKE in terms of MGST anomaly is calculated.

