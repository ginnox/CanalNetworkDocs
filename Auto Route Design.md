# Longitudinal Route Design

Longitudinal design of routes is the stage where the engineer spends significant time working on individual canal routes, and exploring design scenarios. CanalNETWORK offers an interactive graphic environment with rich annotation to guide design process effectively.

Longitudinal design stage requires that the below workflow tasks are completed adequatedly:

1. Resolved network 

2. Established network

3. Profile extracted

Once the above stages are complete, and data from each is accessible (See here for available ways to manage different data and make them accessible for CanalNETWORK), longitudinal profile design can continue.

## Start Longitudinal Design

There are two ways to start the longitudinal design of a canal route:

1. In the plan view, zoom or pan to the desired roure, and left-click on it. 
   
   Note: Right click does not load the profile data to the profile view axis.
   
   Note: Make sure the Multi-Select option is diabled, in `Edit > Multi-Select` or the toolbar button. 

2. Press `Ctrl+K` or go to `Workspace > Pick Route (AutoCAD`),

Both options load and render longitudinal profile data, along with canal controls and flow profile information to the Profile view axis. 

> Note: The longitudinal design task follows a down-stream design approach, that is componenets of the route, including controls, drops, and segment assembly information, are positioned and designed from upstream end to downstream end.

The user can interact with the design as follows.

### Adjust Control Inverts

Controls comprise key components in longitudinal design of routes. They represent acual control structures, such as Turn outs and division boxes. The primary task of the engineer can be to design the invert levels of these controls.



> Note: Canal Controls, represented as vertical bars in the profile view axis, represent invert and hydraulic information at and upstream of the control location.



Controlling inverts and other hydraulic characteristics hosted by the control is possible from the `Node Panel` at the right side of the interface. 



It is important to note that, all values displayed for a control node, are an exact copy of the design criteria, applied during canal sizing operation.  Hence, any edit the user does for the control is effectively over-riding the provissions of the design criteria.



Select a control node in the profile view. Then: 

![](Images%20for%20Updates%20Nov21/Image%20012.png)

To change the invert level upstream of the control:

* Use Node Invert Level edit box to directly input elevation values

* Use the left `<` and right `>` arrow to increment the current value of the invert level for the control



> Note: The algorithm maintains the settings in the design criteria regardless of the the user inputs. Hence, there is a limit to how high or low the invert can be raised or lowered. For instance, any control can not be raised above the level that is maintained by the bed slope of the upstream canal section.



![](Images%20for%20Updates%20Nov21/Image%20013.png)



There are two ways to change invert level downstream of the control:

* Set Exit Drop: Type the desired value directly the Exit Drop edit box (with respect to upstream invert level.) Typically, this value is a negative value representing a drop in elevation calculated with respect to the upstream invert.

* Set Head Loss: Check the HL option box, and type a desired head loss value. This is also typically a negative value indicating the desired headloss to maintain as the flow transitions through the control. This process, calculates an exit drop at the control that can satisfy the desired head loss amount, and apply to the control.



![](Images%20for%20Updates%20Nov21/Image%20014.png)

Change how drops are located upstream of the selected control, by:

* Change or set a fit height *fitHt* for drop positioning at `Use Fit Height` edit box. Drops are located in one of three ways:
  
  * *fitHt* <=0 ensures that drops are inserted where the bed level is exactly *fitHt* units below the OGL 
  
  * *fitHt*  >0 ensures that drops are inserted where the FSL level is exactly *fitHt* units above the OGL.
  
  * *fitHt* =-99 ensures that there is no drop inserted upstream of the current control.

* Check the `Fit DBL for No Drop` option to set *fitHt* to -99.



![](Images%20for%20Updates%20Nov21/Image%20015.png)

To Change the bed slope upstream of the control,

* edit the `Change Bed Slope` edit box to desired value. This is typicall a positive value equal to the desired canal slope (H:V).

* Click on the drop down menu at the right of the edit box, to pick from a set of default values.



![](Images%20for%20Updates%20Nov21/Image%20016.png)

Finally, to change the functions of the control:

* By default, all controls are configured as Turnout structures. To change the function of the control to a division box structure, check the Division Box option. This will invoke hydraulic calculation and design algorithm to size and position the control along with its branch canal(s) appropriately.





To reapply the default criteria set for the entire route, thereby removing any and all overrides done manually, the user must resize the canal. See part of this guide on [Design Criteria creation and use]()  for more details.



### Adjust Drops

Drops are created automatically following the variation of the ground level. They are positioned strictly per the provisions of CBL_designSettings parameter set in the design criteria. See [Design Criteria Creation and Use]() for the meaning and use of each of these variables.



For many reasons, the automated design output will not satisfy the engineers desires. Each drop can be edited and adjusted as follows:

To change the location of the drop:

* Click on the desired drop. An interactive tool appears reading station location for the new locatio of the drop. Click at the desired new location, and the drop is repositioned to a new station.



To change manually change the location and/or height of the drop:

* right click on the desired drop, and choose Adjust Drop conext menu item. This will start a dialog box. 

* Enter the desired station,  and click on Apply. The drop is repositioned accordingly.

* Enter a desired drop height, and click apply. The drop height us adjusted accordingly.



> Note: User inputs are guided by allowable values for the specific drop.





* 

* 



1. *fitHt* specification 

2. **

### Adjust Canal Assembly for Segments

### Solving for optimal flow section for individual segments

Flow sections for individual segments, and the wider network of canals in general, are often expected to perform under established constraints that include:

* minimum non-silting velocity

* maximum non-scouring velocity

* Maximum allowable shear stress

The flow section design tool offers the capabilty to interactively vary the bed slope of a given canal segment and see impacts on above parameters. The accepted design detail can be applied to the segment at the end.

This tool is availiable for a single segment in the profile view, and accesible from the `Indicator Button` in the `Assembly Pannel` pannel.

To start it, select a desired segment from the profile view. The `Indicato Button` will be active. Click on it. The *Canal Section Design* interface will pop up.

[ ] figure.

> Note: this interface starts with the hydraulic design parameters for the selected segement, and no data entry is required.

The main purpose of this interface, among others, may be to anlyze the variation of the flow section as the slope varies. As the slope is varied, by dragging the vertical bar the flow section and corresponding flow velocity and sheat stress developed are computed and displayed. The colored scales on the gauge bars provide feedback on appropriateness of the slope.

The Solver function offers a key tool to determine the best fitting slope that respects the constraints for limiting velocity and shear stress set in the design criteria.

### Creating and Managing Annotations

# Using Advanced tools for longitudinal design

## Override design criteria (Exception)

## AutoDesign

By default, the software generates a tentaive longitudinal profile for the route upon refreshing the profile view. Characteristics of this tentaive design include, bur are not limited to, the following:

* applies the set design slope from the design criteria for the specific route through out the reach

* automatically positions the invert levels of controls to ensure flow of water down stream. To this end, controls may be fixed for no drop structure upstream of the control location, or with drop structure depending on available gradient.

For many reasons, this tentative design will not meet operational requirements. For example, slope must vary depending on the ground level variation. Accordingly flow velocity varies. Further more minimum flow level above ground leve is often a strict requirement. This tentative design does not, however, account for this.

Auto Design tool implements a sophisticated algorithm to factor all the above requireemnts during design work. In the latest version, Auto Design tool is improved to complete longitudinal design of routes faster. The tool now generates the best achievable bed level profile for the given set of conditions to the route. The given set of conditions are as depicted in:

* design criteria provisions, most notably the following:
  
  * maximum and minumum allowable velocities, 
  
  * allowable shear stress.
  
  * allowable minimum FSL above OGL

* variation of ground level in the entire reach of the route

Once again, the careful selection and setting of design criteria for canal routes can not be overemphasized. It affects the outputs of the automatic design, and hence directly impacts the time an engineer spends to complete the design of a single route.

## 

## Auto Designing a single segment

## Auto Designing a single route

# Design aids available for completing design of routes

Annotation minFSLoGL

Annotate frop

Math tool on ivert edit box

## AutoDesigning a selection of routes
