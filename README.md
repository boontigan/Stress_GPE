# Lithospheric stress field from gravitational potential energy (GPE)
The repository stores python notebooks using to compute the global lithospheric stress field using gravitational potential energy
This include 3 main folders
## Input
Input folder stores notebook used to create the input file to submit to Abaqus to calculate the global lithospheric stress field
It consist of the following notebooks
- 0_Main_input_ABQSA.ipynb : User can run all the input notebook through this notebook. It will call the other as functions
- 1_GetCrust1andTDL.ipynb : Import the crustal structure from crust1.0 and mantle structure from TDL model
- 2_GEOM.ipynb : Create the crustal geometry which including density and thickness of each layer of the lithosphere
- 3_GPE.ipynb : Calculate the gravitational potential energy for each column of the lithosphere also calculate the mean outward pressure and different from the reference column
- 4_Interpolate.ipynb : Interpolate the GPE that we calculate from step 3 to the grid point that utilized by ABAQUS
- 5_ABAQUS : Write the .inp file to submit to ABAQUS

## Extract
Extract folder stores noetbook used to extract the abaqus output and caculate the stress that suitable for interpretation.
It consist of the following notebooks
- 0_Main_ABQSA.ipynb : User can run all the extract notebook thourgh this notebook. It will call the other as fuctions
- 1_CalcAnglesABQSA.ipynb : Calculate the grid location of the abaqus output file
- 2_GetStressABQSA.ipynb : Extract the stress from .dat file from ABAQUS
- 3_RotateABQSA.ipynb : Rotate the stress that we obtain from abaqus to the North-East coordinate
- 4_AddStressABQSA.ipynb : Sum up the stress if the user have stress from more than one sources (in case you have stress from other model i.e. mantle flow)
- 5_InPlaneABQSA.ipynb : Calculate the stress in North-East coordinate in the in-plane principle stress
- 6_RegimeABQSA.ipynb : From the magnitude of the principle stress we obtain from 5, stress regimes are calculated 
## Analysis
Analysis folder stores notebook used to plot the stress map and also compare the result with the observational data (the world stress map)
- 1_WSM : Import the world stress map data and interpolate that into the grid of the stress model
- 2_Plot : Plot the stress model using pygmt
- 3_Analys : Calculate the accuracy of the model compared with the interpolated world stress map
