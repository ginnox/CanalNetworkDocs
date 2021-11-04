# Update Notes (Nov 2021)



The following major enhancements and features are made available in this release.

## File management Utility

Open project folder option included to allow easy access to the data files of user projects.



![Image 003](https://user-images.githubusercontent.com/88286426/140335886-6ab2310c-44b1-484b-9cc6-082a12a2cd2c.png)

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

Users can also clear transaction manually.


## Optimal bed slope design function

An interactive tool allows users to critically analyze the current or desired canal flow section and easily apply it to the desired segment of a given canal route. The tool incorporates a built in optimization algorithm to find canal parameters that satisfy differnt objective functions. 

In the current release two objective funcions are included.

1. Minimize Bed Slope
2. Maximize Bed Slope

Subject to the following constraints.

<img src="https://render.githubusercontent.com/render/math?math=v_{min}<=v<=v_{max}">

<img src="https://render.githubusercontent.com/render/math?math=\Tau <= \Tau_{max}">

See details of this tool in the complete user manual.


![Image 007](https://user-images.githubusercontent.com/88286426/140336164-1c00e855-7b1a-47d4-96ac-e7d6f5e6cf33.png)

*New tool to design bed slope for limiting design criteria, showing results of constrained optimization solution for `Min So`*





## Curve handling

During import of routes, automatic identification and reading of curve data is introduced. 

The same functionality is included to the  `AlignmentProfile` tool in iCAD, allowing users to work with curves easily. Routes importedi with profile data (or whose data is is imported using `Soft Reload`) is also rendered to AutoCAD drawing while generating LSec drawings.


![Image 002](https://user-images.githubusercontent.com/88286426/140336241-8026c0d6-e85f-45cd-b946-6c70d1999bdb.png)

*Alignment curve in AutoCAD.*


![Image 004](https://user-images.githubusercontent.com/88286426/140336281-8e3e889f-7a8f-42ad-9ec5-48cbe906fa51.png)

*Curve presentation in plan and profile views*



> Note: Geometric design of curves is now fully entertained in AutoCAD environment. Once imported, the user has no option or tools to change any of the curve parameters.





## Variable drop height

Drop structure sizing is one of the key design tasks carried out by the engineer, and deciding on the heights and positoin of these drops requires factring multiple consideraations and is a time consuming task. The update in this version incorporates a feature to automatically insert drops depending on the variation of the terrain.




![Image 005](https://user-images.githubusercontent.com/88286426/140336347-dd63382e-8f5d-49b1-9209-86dd6dc3cb52.png)

*LSec drawing showing variable drop heigh inserted on a longitudinal profile view.*

## Design Criteria Exception

Canal routes refer [every time they are refreshed] to the design criteria corresponding to their level or generation. To override some of these parameters as the site condition may require, users have to change junction node and canal segment assembly criteria. This makes the job time consuming, particularly for long canal routes.

This update includes tools to allow modification of the design criteria and apply it to an entire route.


![Image 006](https://user-images.githubusercontent.com/88286426/140336385-a6745b28-8943-4976-ba53-b3593ff9c5b6.png)

*Variable editor showing option to set design criteria to a current route.*



## LSec Drawing

Longitudinal Profile (LSec) drawings generate curve details along with other design information on LSec drawings  - following improvements to curve handling as described above - thus making a more complete presentation of design.


![Image 001](https://user-images.githubusercontent.com/88286426/140336407-5a6fa731-e200-4263-bfa1-3870f6c8b25a.png)

*Curve Presentation in longitudinal profile view drawing generated to AutoCAD drawing*



## Bug fixes

- fixed drop edit bugs when working with the last drop in segment.
- fixed undesired node invert change, while using the slider tool to control node elevations
- improved cleaning for invalid nodes and routes.
- polyline filtering to minimize data errors (short length routes, inappropriate profiles...)


## Under progress

The following features comprise the wish list for the next scheduled update (Dec2021). Note this date is subject to change.
* Custom Title blocks

* Drawing styling for colors and/ or layers organizatoin, and production quality drawing generation

* Optimization entry for lining cost function

* and more...


