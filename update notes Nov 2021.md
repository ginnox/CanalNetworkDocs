The updates in the november release include the following features

## File management Utility
Open project folder option included to allow easy access to the data files of user projects.


## Undo/Redo functionality
Infinite number of Undo/redo transactions are registered to allow the user flexibility in the use of the software.

In addition, the scope of the transaction for undo/redo task is now expanded to include the following user interactions:

1. Add AutoCAD route object to layout view
2. Remove route object (and associated junciton nodes) from layout view
3. Manual delete of node
4. Manual additoin of node
5. Drpp height, location edits on longitudinal design
6. Node editing, segment editing on longitudinal design


## Optimal bed slope design function
An interactive tool allows users to critically analyze the current or desired canal flow section and easily apply it to the desired segment of a given canal route. The tool incorporates a built in optimization algorithm to find canal parameters that satisfy differnt objective functions. 

In the current release two objective funcions are included.



1. Minimize Bed Slope
2. Maximize Bed Slope

Subject to the following constraints.

<img src="https://render.githubusercontent.com/render/math?math=v_{min}<=v<=v_{max}">


<img src="https://render.githubusercontent.com/render/math?math=\Tau <= \Tau_{max}">

See details of this tool in the complete user manual.

## Curve handling
During import of routes, automatic identification and reading of curve data is introduced. 

The same functionality is included to the [AlignmentProfile] tool in iCAD, allowing users to work with curves easily.
Note: geometric design of curves is now fully entertained in AutoCAD environment, Once imported, the user has no option or tools to change any of the curve parameters.

## Variable drop height

## Design Criteria Exception
Canal routes refer [every time they are refreshed] to the design criteria corresponding to their level or generation. To override some of these parameters as the site condition may require, users have to change junction node and canal segment assembly criteria. This makes the job time consuming, particularly for long canal routes.

This update includes tools to allow modification of the design criteria and apply it to an entire route.

![image](https://user-images.githubusercontent.com/88286426/140291915-e4ab0ab7-5278-407b-90f8-e8c7810d5f0f.png)

## LSec Drawings
Longitudinal Profile (LSec) drawings generate curve details along with the other informations, making a more complete presentation of design.


## Bug fixes
- drop edit (last of segment)
- others
- Unwanted node invert change, while using the slider tool to control node elevations.
- 

## Under progress
Title blocks
Drawing styling
OPtimization tool for lining 

