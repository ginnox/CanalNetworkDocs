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

![](Images/Image%20012.png)

To change the invert level upstream of the control:

* Use Node Invert Level edit box to directly input elevation values

* Use the left `<` and right `>` arrow to increment the current value of the invert level for the control

> Note: The algorithm maintains the settings in the design criteria regardless of the the user inputs. Hence, there is a limit to how high or low the invert can be raised or lowered. For instance, any control can not be raised above the level that is maintained by the bed slope of the upstream canal section.

![](Images/Image%20013.png)

There are two ways to change invert level downstream of the control:

* Set Exit Drop: Type the desired value directly the Exit Drop edit box (with respect to upstream invert level.) Typically, this value is a negative value representing a drop in elevation calculated with respect to the upstream invert.

* Set Head Loss: Check the HL option box, and type a desired head loss value. This is also typically a negative value indicating the desired headloss to maintain as the flow transitions through the control. This process, calculates an exit drop at the control that can satisfy the desired head loss amount, and apply to the control.

![](Images/Image%20014.png)

Change how drops are located upstream of the selected control, by:

* Change or set a fit height *fitHt* for drop positioning at `Use Fit Height` edit box. Drops are located in one of three ways:
  
  * *fitHt* <=0 ensures that drops are inserted where the bed level is exactly *fitHt* units below the OGL 
  
  * *fitHt*  >0 ensures that drops are inserted where the FSL level is exactly *fitHt* units above the OGL.
  
  * *fitHt* =-99 ensures that there is no drop inserted upstream of the current control.

* Check the `Fit DBL for No Drop` option to set *fitHt* to -99.

![](Images/Image%20015.png)

To Change the bed slope upstream of the control,

* edit the `Change Bed Slope` edit box to desired value. This is typicall a positive value equal to the desired canal slope (H:V).

* Click on the drop down menu at the right of the edit box, to pick from a set of default values.

![](Images/Image%20016.png)

Finally, to change the functions of the control:

* By default, all controls are configured as Turnout structures. To change the function of the control to a division box structure, check the Division Box option. 

* This will throw the confirm dialog shown below.
  
  ![d](Images/Image%20001.png)

* If user resonds with Yes button, then, this will invoke hydraulic calculation and design algorithm to size and position the control along with its branch canal(s) appropriately.

* One can view the results of the hydraulic analysis by clicking on the R button next to the Division box check box. A report of the following form will be generated informing the user of the hydraulic analysis carried out, and the adjustments made to the inverts of the offtaking canals.
  
  ![d](Images/Image%20002.png)
  
  ![d](Images/Image%20003.png)

* The same button also redesigns the division box currently selected, for any changes that may have been made to invert levels, flow depths, or similar. A new report, and a new set of invert levels are calculated and applied to the offtaking canals corresponding to the modification made.

To reapply the default criteria set for the entire route, thereby removing any and all overrides done manually, the user must resize the canal. See part of this guide on [Design Criteria creation and use]()  for more details.

### Adjust Drops

Drops are created automatically following the variation of the ground level. They are positioned strictly per the provisions of CBL_designSettings parameter set in the design criteria. See [Design Criteria Creation and Use]() for the meaning and use of each of these variables.

For many reasons, the automated design output will not satisfy the engineers desires. Each drop can be edited and adjusted as follows:

![](Images/Image%20017.png)

To change the location of the drop:

* Click on the desired drop. An interactive tool appears reading station location for the new locatio of the drop. Click at the desired new location, and the drop is repositioned to a new station.

![](Images/Image%20018.png)

![](Images/Image%20019.png)

To manually change the location and/or height of the drop:

* right click on the desired drop, and choose Adjust Drop conext menu item. This will start a dialog box. 

* Enter the desired station,  and click on Apply. The drop is repositioned accordingly.

* Enter a desired drop height, and click apply. The drop height us adjusted accordingly.

> Note: User inputs are guided by allowable values for the specific drop.

Some times the last drop inserted in a canal segment can have odd values (not suitable for construction.) In such cases the user can make fine adjustment by typing in numeric expressions in the `Edit Node Invert` edit box inside the Node Panel.

![](Images/Image%20030.png)

In above snapshot, the drop height of 0.836 can be adjusted to 0.800 by adding 0.036 to the invert level of the downstream control. The result is shown below.

![](Images/Image%20031.png)

### Adjust Canal Assembly for Segments

The last area of control for the user to guide and influence longitudinal canal is the `Canal Assembly` panel. In this panel, information regarding the parameters that determine the shape and size of the canal section and its flow parameters can be adjusted. 

> Note: When a node is selected, this panel shows flow information in the segment upstream of the control. The small rectangular button, also known as Perfoamnce Indicator button, show the acceptability of the flow conditions. A red color indicates tells that either the velocity limits or the shear stress limits are not respected, and redesign is needed.

The user can interact with the canal assembly informaiton in many ways. Select ((click on the OGL profile line) a canal segment or reach in the profile view that you want to edit and follow below guideline:

![](Images/Image%20021.png)

To change the flow section, drop design or construction parameters:

* click on `Edit Assembly` drop down menu, and choose the relevant design option. This will open up a dialog to edit corresponding variables fot the canal segment. See [Design Criteria Setting and Use]() for details on each variable and their design implication.

![](Images/Image%20022.png)

To redesign the flow section by adjusting the slope within allowable performance criteria:

* Click on the `Perfoamcne Indicator` button. This will invoke a dedicated interface to interactively design the section. 

* After making the desired changes, close the interface. The user will be promted to apply the changes, and the profile view will update automatically to update the changes.

* See further below topic [Solving Optimal flow sections for Individual segments]() further below for guidance on using the solve function.

## Exploring Solutions

There are multiple ways to explore and interact with the solutions of a longitudinal profile design of a canal route. These are all accessible from the menu `Explore Solutions`.  These are categorized in to two groups, annotations and data tables.

### Creating and Managing Annotations

Users can create and manage various annotations to keep track of the changes happening, as well as ensure key criteria are met.

![](Images/Image%20024.png)

To show drop heights,  FSL-OGL value at controls, 

* Go to `Explore Solutions > Annotations > Drop Heights` to show drop heights for generated drops.

* Go to `Explore Solutions > Annotators > min FSL-OGL` to calculate FSL-OGL value at each control and render values by color in comparison with design criteria value.

To show hydraulic annotations such as OGL, CBL, FSL inforation:

* click on the appropriate annotator from `Explore Solutions > Annotators` and interactively position the cursor line. The results will be displayed.

![](Images/Image%20025.png)

An other imporant annotation available is cut and fill volume annotator. This tool can cumulate volumes of earth work for entire reach or between selected stations giving an insight in to the cost of the design. To view volume informaiton:

* Click on` Explore Solutions > Annotators > VCUT, VFIL` menu item. 

Yet another helpful annotation is available from `Explore Solutions > Annotatiors > LSec Details`. This will display details of the longitudinal design including station range and flow section details for each segment of route. In addition it also annotates canal curve information if avaiilable.

![f](Images/Image%20040.png) 

The above described annotations provide a quick and reliable overview of the hydraulic status of the canal. Some of the annotations also vary dynamically along with design changes by the user, to help decide whether design objectives are met.

### Viewing and copying table data

The other group of tools to explore solutions is viewing tabular data. The solution for longitudinal design of routes incorporates tabular data. These are accessible from Explore Solutions > Data Tables. There are five table data available for viewing.

![d](Images/Image%20041.png)

#### LSec Profile Data

This table shows extensive detail of profile data along with canal bed level and embankement formation data for the entire range of stations in the route. 

Note: The data are tabulated at exactly the same incremental stations generated during profile extraction.

![d](Images/Image%20042.png)

The table headers are explained in below schematics.

![s](Images/Image044.jpg)

*Schematic of a typical canal cross-section, showing details for unlined canal.*

![s](Images/Image%20043.jpg)

*Schematics of a typical canal cross-section, showing details for thin (left) and Thick (right) lined canals.*

aCut and aFil are determined by working out an exact analytical replica of the above geometric arrangement, and calaculting the area bounded in the corresponding regions. Typically, the analytical geometry is worked out for:

* a prevailing OGL (transverse profile)

* designed canal section geometry, such as bottom width, side slope and canal depth.

* superposed with values of *Cut Shape* and *Fill Shape* values input in construction variable settings, such as working space (in case of linings), berm width, cut/fill slopes and heights, number of berms, etc.

Hence, all results of the table can be considered an accurate representation of the built condition, given the transverse profile adequately represents the expected terrain variation at the particular station.

Bill of quantitiy estimates for earth works are estimated by cummulating areas of cut and fill at each succesive station, and applying the trapezoidal method. This method utilizes the approximation used for 'numerical integration', that breaks down areas in to trapezoids with more easily computable areas. 

![s](Images/Image%20043.png)

The trapezoidal method of volume estimation generalizes to:

![c](Images/Image%20044.png)

where x1, x2,... xn represent the station locations for the corresponding aCut and aFil funtion values. 

Note: Cart away volumes reported on BoQ table represent the total excavated/Cut volume multiplied with hardcoded loosness factor of 1.2.

### Exploring Flow Sections

This command generates the hydraulic design results for flow sections corresponding to each segment in the canal route.

![s](Images/Image%20045.png)

In the table, 

V: represents actual flow velocity in the canal section

Vchzy: Chezy's flow velocity in the canal section, estimated from:

v= c x (R/So)^(-1/2), and

c= NxR^(-1/6)

Vcr: Criteria velocity estimated from:

Vcrt= 0.546*y^0.64

Vratio: Velocity ratio determined from 

Vratio= Vchzy/Vcrt

Some practitioners recommend to accept design sections whose value for velocity ratio is close to unity.

### Exploring Controls

This menu command generates a list of all the controls in the canal route, that define the connection between succesive segments, as well as junction with brnach canals - if any.

![d](Images/Image%20046.png)

In the table, the following defintions apply to the terms listed:

Type: The function of the control, set to either Turnout or Division box.

US Invert: the invert level, or the CBL, just upstream of the control location.

DS Invert: the invert level, or CBL, just downstream of the control location. This accounts for any Exit Drop Height specified for the control - if any.

Fall Height: The difference between US and DS invert levels

FSD: Flow depth for the flow section corresponding to the segment upstream of the control location, and

FSL: the full supply level just before the control location.



### Exploring Drops

Similar to above commands, this command list all the vertical fall structures for the route.

![d](Images/Image%20047.png)

The table contains a rather long list of parameters for each drop:

Station: Location of the drop structure

<u>Discharge</u>: The design flow capacity of the drop passing through the structure.

<u>Crest Ht</u>: The height of the over flow crest above the US Invert level for the drop.

<u>Crest Width</u>: The width of the drop structure just before the overflow span at the crest, also extending to the stilling basin compartment.

<u>Fall Height</u>: The elevation difference between the US (Inlet) and DS(Outlet)  invert level of the drop, as defined below.

<u>Inlet, Outlet</u>: the invert level, or CBL, just upstream and DS of the drop location, respectively.

<u>Notch WIdt</u>h: The width of the overflow section just at the crest.

<u>Sill Height</u>: The height of the end sill provided for the drop, just before joining the continuing (downstream) canal reach

<u>Basin Length, WIdth</u>: The length, and width of the stilling basin to be provided

<u>Basin Thk</u>: The thikness of impervious floor to be provided under the stilling basin to ensure safety  against excessive uplift pressure. (this is dertermined assuming massonry material with a unit weight of 22KN/m3)

<u>US, DS Cutoff</u>: Depth of cutoff wall provided at begining and exit of the drop structure.

<u>Protection Length</u>: Recommended length of protection layer to be provided both upstream and downstream of the drop structure.



### Exploring Turnouts

This option specifically lists the relevant construction dimensions for each turnout structure found on the route. 

![s](Images/Image%20048.png)

The symbols for the dimensions are explained in the accompanying drawing below.

![  ](Images/CDSWC_str/Image%20003.png)

![sec](Images/CDSWC_str/Image%20004.png)

![sec2](Images/CDSWC_str/Image%20005.png)

*Figure: Tunrout Structure detail drawings from ECDSWC, with dimension detail corresponding to the symbols in the explore output table.*








### Exploring Division Boxes

Similar to turnouts, this command specifically lists the relevant contruction dimensions for each division box structure found on the route.

![s](Images/Image%20049.png)



The symbols for each dimension heading is described in the below drawing.



![d1](Images/CDSWC_str/Image%20001.png)

![d2](Images/CDSWC_str/Image%20002.png)

*Fig: Drawing for a typical division box from CDSWC, showing the deginition of symbols used in the table listing.*



### Copying table data and using in other applications

All the data presented in the form of a table can be used in other applications, e.g., report writing in MS Word or further data processing in MS Excel. The `Copy Table` button provided at the bottom of the table display interface just helps do that. To copy the data content of the table view interface, click on the button.

![d](Images/Image%20050.png)



Choose your preference as shown above, and jit Ok. The data is copied to the Windows Clipboard. You can now paste the data to your desired application and use it.



# Using Advanced tools for longitudinal design

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

## Solving for optimal flow section for individual segments

Flow sections for individual segments, and the wider network of canals in general, are often expected to perform under established constraints that include:

- minimum non-silting velocity

- maximum non-scouring velocity

- Maximum allowable shear stress

The flow section design tool offers the capabilty to interactively vary the bed slope of a given canal segment and see impacts on above parameters. The accepted design detail can be applied to the segment at the end.

This tool is availiable for a single segment in the profile view, and accesible from the `Indicator Button` in the `Assembly Pannel` pannel.

To start it, select a desired segment from the profile view. The `Performance Indicator Button` will be active. Click on it. The *Canal Section Design* interface will pop up.

![](Images/Image%20023.png)

> Note: this interface starts with the hydraulic design parameters for the selected segement, and no data entry is required.

The main purpose of this interface, among others, may be to anlyze the variation of the flow section as the slope varies. As the slope is varied, by dragging the vertical bar the flow section and corresponding flow velocity and sheat stress developed are computed and displayed. The colored scales on the gauge bars provide feedback on appropriateness of the slope.

To see how performance of the canal varies:

* change the slope by clicking on (or draging the marker) on the vertical slider bar representing the bed slope of the canal. The flow section, the resulting velocity and shear stress values change accordingly.

* The updated flow section is drawn, and also the details written to the `Results` area on the right of the interface.

The Solver function offers a convenient and automatic tool to determine the best fitting slope that respects the constraints for limiting velocity and shear stress set in the design criteria. 

* To find the minimum slope possible, change the `Goal `setting to `Min S`o, and hit Solve...

* To find the maximum slope possible, change the `Goal `setting to `Max S`o, and hit Solve...

In both cases, the results are generated accordingly.

![](Images/Image%20027.png)

Upon satisfactory design, close the dialog, and accept the Apply request in the dialog that appears.

Note, the following limitations apply:

- Minimum calculated slope can not be lower than 50 (50H: 1V)

- Maximum calculated slope can not be higher than 10,000 (10000H: 1V)

## AutoDesign for Route

The above procedure used for designing a single segment of a given route can be applied for an entire length of a route. To do so

* Go to `Workflow > Design and Analysis > Auto Design Current Route ` 

* The process will continue in the background (with out invoking the *Canal Section Design* interface), but applying the changes to the segments.

Note the following added functionalities in this use-case:

1. Automatically considers the available slope from the OGL

2. Automatic positioning of inverts attempting to respect minimum FSL-OGL value in the design criteria set, where possible.

To see the viability of the result from this auto-design process, the user can create and manage annotations - especially:

* Drop heights: looking out for non-standard drops that may have been created, and adjusting if necessary. (see below [Design Aids Available for Completing Design of Routes]() below.)

* minFSL-OGL: looking out for red-colored texts, indicating the desired criteria value is not met on those controls, and adjusting the inverts manually if needed. (See [Adjust Control Inverts]() above.)

## Override design criteria (Exception)

Canal routes, every time they are refreshed, refer to the design criteria corresponding to their level or generation. To override some of these parameters as the site condition may require, users have to change junction node and canal segment assembly criteria. This makes the job time consuming, particularly for long canal routes.

Instead, users can over ride the entire design criteria for a canal route and allow specific criteria for a route. 

![](Images/Image%20006.png)

To set override values and apply to the current route:

* Start the editror from Workspace > Manage Design Criteria > Set Edit Design Criteria... 

* Change the values of the desired parameters 

* Go to the final row, and for the *On Apply Use for* choose *Current Route*. 

* Hit `Apply `to complete.  This will review every aspect of the route to conform to the new set of criteria.

Note: The new set of criteria are also saved on to the exception data string for the route. This allows to re-visit the input data at a latter stage, and modify it. If not needed, it can be removed from `Edit > Route Exception > Manage Exceptions...`

Important: Exception design criteria EXCLUDE all variables in the command criteria group of variables.

## AutoDesigning a Selection of Routes

![](Images/Image%20007.png)

AutoDesign tool can be applied to a selection of routes in one go. To start the tool:

* Select the desired routes in the plan view (iwth Multi-select mode set to ON). Use available tools from `Edit > Select Routes` if needed.

* Go to `Workflow > Design and Analaysis > AutoDesign Route(s)...` 

This will start the process for all selected routes sequentially.

Important: It is important to revisit the designs for each route designed with the Auto tool, and make any adjustments before production.

*Note: AutoDesign task can not be undone. To reset to original tentative settings, select the route, apply Resize. Design parameters are reapplied. To view the updated view, click on the route in plan view, which will refresh the view in Profile View Axis.*


END.
