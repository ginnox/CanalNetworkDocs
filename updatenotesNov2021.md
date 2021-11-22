# Update Notes (Nov 2021)

The update for the period is packaged separately. Download the updates from the following links:

[Download iCAD Version 2.2.8.7512](Update Binaries/iCAD21.exe)

[Download CanalNETWORK Version 1.5.0.1245](Update Binaries/CanalNetwork.exe)

[Download iCAD Bridge 4.4.1](Update Binaries/iCAD Bridge.dvb)

![](Images%20for%20Updates%20Nov21/BothVersions.png)

> IMPORTANT NOTE: The design criteria listing and content to default values from this release onwards has changed for (a) `Hydraulic_Design>Limiting Velocit`y, (b) `CBL_designSettings > Max. Drop Height`, and (c) `CBL_designSettings>Min Drop Spacing`. Previous projects done with the older listing REQUIRE polishing, or error will occur. Seek Technical support if you face this issue.

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
3. Minimize Wetted Perimeter

Subject to the following constraints.

<img src="https://render.githubusercontent.com/render/math?math=v_{min}<=v<=v_{max}">

<img src="https://render.githubusercontent.com/render/math?math=\Tau <= \Tau_{max}">

See details of this tool in the complete user manual.

![Image 007](Images%20for%20Updates%20Nov21/Image%20032.png)

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

## Limiting Velocity

Minimum and maximum values of permissible velocities can now be set explicitly under the Hydraulic_Design parameters group. See above figure, row number 23.

> Note: The name for the variable is changed respectively, and the number of inputs expeted is 2.

## LSec Drawing

Longitudinal Profile (LSec) drawings generate curve details along with other design information on LSec drawings  - following improvements to curve handling as described above - thus making a more complete presentation of design.

![Image 001](https://user-images.githubusercontent.com/88286426/140336407-5a6fa731-e200-4263-bfa1-3870f6c8b25a.png)

*Curve Presentation in longitudinal profile view drawing generated to AutoCAD drawing*

# UX Improvements

The following functionalities are introduced as new tools to allow faster and well informed design task handling for the user:

1. Multi-select button added to the tool bar: previously accessed only from `Edit > Multi-Select (Routes).` Now, the user can set it's state from the toolbar button, and also view its state always.

![](Images%20for%20Updates%20Nov21/Image%20008.png)

2. Increased Speed for Pan/Zoom operations: The number of graphic components on the paln view can grow significantly with out the user noticing it. This has direct bearing on the speed of zoom/ pan scroll actions. In addition to previous tool to toggle on/off route texts, in this version the user can choose to show or hide Node markers on the plan view.

![Image ShowHideNode](Images%20for%20Updates%20Nov21/Image%20009.png)

4. Faster selection of routes: Users select desired routes by right-clicking on each route individually. In this version, more options are provided in `Edit > Select Rotues`. This offers the user to select multiple routes with one click, from either:
   
   - `Select by Instanc`e: Using an instance in AutoCAD, or
   
   - `Select Sub Routes`: which selects all subroutes corresponding to an existing selection.

5. Manage exceptions (view and remove) for naming, and also newly introduced design criteria override accessible from `Edit > Route Exceptions > Manage Exceptions...`

6. Find text tool using `Ctrl + F`

7. Allow rounding of to Bottom width designs in `Workspace > Edit Preferences`. This allows to round of every design to desired precission that is suitable for construction as choosed by user.
   
   * Available precisions are 0.0 to 0.50.
   
   * Example 5.83 is changed to 15.80 using a precision of 0.10.
     
     

![](Images%20for%20Updates%20Nov21/Image%20033.png)

![](Images%20for%20Updates%20Nov21/Image%20034.png)

9. Warning to User on reload of routes

![](Images%20for%20Updates%20Nov21/Image%20035.png)

11. A new annotation option in `Explore Solutions > Annotations > min FSL-OGL`  to display the value of FSL-OGL, colored according to the settings in Design criteria.

12. Click a node on plan view to activate it in the profile view.

13. Clear Axis menu tool on Plan view axis

14. Increased speed for View > Auto Color Routes...

## Bug fixes

- fixed drop edit bugs when working with the last drop in segment.
- fixed undesired node invert change, while using the slider tool to control node elevations
- improved cleaning for invalid nodes and routes.
- polyline filtering to minimize data errors (short length routes, inappropriate profiles...)
- fixed missing detail on additional branch canals when exploring division box table data.
- fixed change of route tag to *Untagged*  on soft reload
- Fix to show text with the new show/ hide Node functionality
- Fixed station marker text which hides trailing zeros
- fix missing lining to cross-section generate to AutoCAD 
- fix to x-section ROW overshots on complex terrain and multiple cut/ fill areas
- Fix plan view generation bugs when float nodes are involved

## Under progress

The following features comprise the wish list for the next scheduled update (Dec2021). Note this date is subject to change.

* Custom Title blocks

* Drawing styling for colors and/ or layers organizatoin, and near-production quality drawing generation
