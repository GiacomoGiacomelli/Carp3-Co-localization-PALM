# CARP3 + flagellar tips

Available Files:

Elyra_Table_example: 
- Index
- First Frame: Frame at which an event firstly appear
- Number Frames: (relevant only when grouping)
- Frame Missing: (relevant only when grouping)
- Position X [nm]: (0 to 51200)
- Position Y [nm]: (0 to 51200)
- Precision [nm]
- Number Photons
- Background Variance
- Chi square
- PSF half width [nm]
- Channel: relevant only for dual color
- Z Slice: relevant only for Z stacks 

Script_R1_ROI_mod (ROI modification script):
- Input: ROIs obtained via Fiji -> need to be named Cell*.txt
- Output: ROIs ready to be used for "PALM data analysis" script -> R.Cell*.txt

Script_R2_PALM analysis (PALM data analysis):
- Input: ROIs obtained from "Script_R1_ROI_mod"
- Input: Elyra_Table_Example
- Output: Channel_#_updatedtableX (Elyra table drifted according to the ROIs - Channel specific)
- Output: AreaListX.RData (ROIs - both channels give the same output)
- Output: Channel_#_flagella_drifted_filtered.txt (PALM_analysis_output example)

PALM_analysis_output example: (first 13 columns are the same as the "Elyra_Table_example")
- CellName: ROI file name (R.Cell*.txt)
- CellDiameter: Diameter of the ROI in nm
- CellArea: Area of the ROI in square nm

Script_R3_Gest (Gest): Estimates the nearest neighbour distance distribution function G(r) from a point pattern in a window of arbitrary shape.
- Input: AreaListX.RData (ROIs) or ROIs obtained from "Script_R1_ROI_mod"
- Input: OutputTableX.txt (PALM_analysis_output example)
- Output: Gest plot, Gest(experimental-theoretical) plot
