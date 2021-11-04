# Update Notes (Nov 2021)



The following major enhancements and features are made available in this release.

## File management Utility

Open project folder option included to allow easy access to the data files of user projects.



![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-17-27-08-image.png)

*Quick access to project folder for data management*



## Undo/Redo functionality

Unlimited number of Undo/redo transactions are registered in-process to allow the user flexibility in the use of the software.

In addition, the scope of the transaction for undo and/or redo task is now expanded to include the following user interactions:

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

![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-17-23-29-image.png)

*New tool to design bed slope for limiting design criteria, showing results of constrained optimization solution for `Min So`*





## Curve handling

During import of routes, automatic identification and reading of curve data is introduced. 

The same functionality is included to the  `AlignmentProfile` tool in iCAD, allowing users to work with curves easily. Routes importedi with profile data (or whose data is is imported using `Soft Reload`) is also rendered to AutoCAD drawing while generating LSec drawings.

![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-16-43-48-image.png)

*Alignment curve in AutoCAD.*



![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-16-45-45-image.png)

*Curve presentation in plan and profile views*





> Notee: Geometric design of curves is now fully entertained in AutoCAD environment. Once imported, the user has no option or tools to change any of the curve parameters.





## Variable drop height

Drop structure sizing is one of the key design tasks carried out by the engineer, and deciding on the heights and positoin of these drops requires factring multiple consideraations and is a time consuming task. The update in this version incorporates a feature to automatically insert drops depending on the variation of the terrain.



![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-17-15-10-image.png)

*LSec drawing showing variable drop heigh inserted on a longitudinal profile view.*

## Design Criteria Exception

Canal routes refer [every time they are refreshed] to the design criteria corresponding to their level or generation. To override some of these parameters as the site condition may require, users have to change junction node and canal segment assembly criteria. This makes the job time consuming, particularly for long canal routes.

This update includes tools to allow modification of the design criteria and apply it to an entire route.

![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-17-17-07-image.png)

*Variable editor showing option to set design criteria to a current route.*



## LSec Drawing

Longitudinal Profile (LSec) drawings generate curve details along with other design information on LSec drawings  - following improvements to curve handling as described above - thus making a more complete presentation of design.



![](C:\Users\Dell\AppData\Roaming\marktext\images\2021-11-04-17-07-18-image.png)

*Curve Presentation in longitudinal profile view drawing generated to AutoCAD drawing*



## Bug fixes

- fixed drop edit bugs when working with the last drop in segment.
- fixed undesired node invert change, while using the slider tool to control node elevations
- improved cleaning for invalid nodes and routes.
- 

## Under progress

Title blocks
Drawing styling
OPtimization tool for lining 
