# Design Production

There are different products that the user can generate from a succesfully compelted design for a canal route. These are three main groups of outputs.

1. Table data: 
   
   including design schedule table, table listing for structures/ controls, table listing for flow sections, as well as Setting-out table data.

2. Bill of Quantitity
   
   a report of a detailed and complete bill-of-quantity document suited for export to differnt formats (doc, html)

3. AutoCAD drawings
   
   Including Flow sections, Cross-sections, Longitudinal profile Design, and Plan Views

Below sections show how to generate these data.

### Table Data

Table data are results of design work for a particular canal route that can be presented as a table listing. The following are typical table data that can be generated for a selected route.

- LSec Profile Data

- FLow Section Data

- Schedule of Controls, Drops, Turnouts, and Division Boxes

See Exploring Solutions under Longitudinal Design of Canals Section, for details on each of these.

### Bill-of-Quantity

Bill of Quantity document is one of the key outputs of a design task. In CanalNETWORK product, this is a fully automated process. The output can be created in many different ways.

> Note: Often, the volume of cut and fill involved for a canal route is a design decision tool. To explore these values, the best way is to use the annotation tools from `Explore Solutions > Annotators`. See relevant section in this guide.

#### Preparing for BoQ extraction

Before BoQ can be extracted accurately, all elements of the canal route - i.e., profile data and structures data must be updated. To ensure all data for the elements correspond to the most recent design changes, fully exploring solutions is a mandatory step, especially before BoQ extraction. This ensures that every element of the canal route are upto date.

 This can be easily achieved by invoking the batch process from `Explore Solutions > Batch Processes > Batch Explore SubRoutes`.

![fig6](Images/Image%20017.png)

This will invoke the following dialog, indicating which level is selected currently (in this case TC) and to confirm which levels of canals to automatically explore and update.

Once can choose a single level, or multiple levels. In either case, a confirmation is requested that lists the name and number of canals that will be processed.

![fig7](Images/Image%20018.png)

![fig8](Images/Image%20019.png)

Confirm `Go` and all relevant canal routes are auotmatically updated for the latest design data. The following dialog confirms the actions taken.

![fig8](Images/Image%20026.png)

Note: BoQ created with out updated control and structures data can be incomplete, or inaccurate.

#### Bill of Quantity for a Canal Route

The general steps to creating a bill-of-quantity output is as follows:

1. Select the desired canal route(s) whose Bill-of-Quantity is desired in plan view.
   
   ![fig5](Images/Image%20020.png)

2. Go to `Explore Solutions > Data Tables > Generate Route BoQ` or `Explore Solutions > Batch Processes > Bill-of- Quantity`. The choice will depend on the user. The proceeding topics will cover different levels of BoQ outputs, and how to create them.
   
   ![figd](Images/Image%20027.png)

3. Set the desired reporting format, and accept. There are three options available: .rtf, .doc and .html options. While the former two create an editable text format suitable for MS Word, the last option creates and displays the output to the default browser. 
   
   ![figh](Images/Image%20028.png)
   
   Hit `Apply` when done. 
   
   ![figj](Images/Image%20029.png)
   
   Select `Open Report` to view the report. This will invoke the necessary applicaiton to view the report.
   
   ![figk](Images/Image%20030.png)

> Note: End-of-Route turnout structures are always excluded from Bill-of-quantity listing. 
> 
> Note: Closely spaced drops, whose placement creates an overlap during excavation, are skipped in BoQ. The user is notified accordingly, to resolve the issue and try again.

Below are the different types of BoQ reports that can be generated.

#### BoQ for Canal Segments

BoQ can be generated for a single segement of a route, that is the reach between any two control nodes. To do this:

1. Select the node at the downstream end of the desired segment in profile view. In the figure below the segment upstream of the node at arround STA 700 is selected.
   
   ![fig](Images/Image%20040.png)

2. Start the command from `Explore Solutions > Data Tables > Generate Route BoQ`. Follow the general steps to complete the process. Below is the extract for the segment. Notice, the report ONLY includes the range of the selected segment.
   
   ![figl](Images/Image%20041.png)

#### BoQ for Select group of Canals

Sometimes, extracting BoQ for selected group of canals may be needed. For this approach, the desired canals are instanced to an AutoCAD host object first. Then, using the `Explore Solutions > Batch  Processes > Bill of Quantity` will do the job. 

1. Enable Multi-Select from `Edit > Multi-Select`, and select the canal routes whose BoQ is desired in Plan view. This can be manually, by right clicking on each route. If the canals are branches of one parent canal, this can be conveniently done by first selecting the parent canal, and then using `Edit > Select Routes > Select Sub-Routes` menu command.
   
   ![figxx](Images/Image%20042.png)
   
   ![figk](Images/Image%20043.png)
   
   In the above example, this will select all the branches of the TC canal.

2. Prepare a host object in AutoCAD for the instance data. Then instance the selection from `Workflow > Prep Network > Create Instances`. 
   
   ![figbb](Images/Image%20044.png)
   
   This will list the objects currently selected. 
   
   ![fighh](Images/Image%20045.png)
   
   Confirm action, and AutoCAD will be in select mode. Pick the prepared host object.
   
   ![figx](Images/Image%20046.png)
   
   The Done dialog will confirm the results of the action.

3. Finally, use `Explore Solutions > Batch Processes > Bill of Quantity`. AutoCAD will be in select mode. Pick the host object prepared. 
   
   ![Figv](Images/Image%20047.png)
   
   The process will automatically update all data contents for each of instanced routes, and report status.
   
   ![fign](Images/Image%20048.png)
   
   Confirming Open Report will display the data extracted. Notice the title for the report indicating multiple routes are selected for the listing.
   
   ![figz](Images/Image%20049.png)
   
   Notice the title indicating multiple canals are selected for the BoQ listing.

#### Settings for BoQ generation.

Quantity listing depends on values set to selected paramters. There are three imprtant parameters that affect the level of detail considered for quantity extraction. 

1. Detailed or Summarized Listing

2. Considering Clearing Depth

3. Considering Structure locations 

These parameters cab be set flexibly by the user from `Workspace > Edit Preferences...` menue command.

![fig1](Images/Image%20016.png)

1. BoQ List of Items:
   
   Detailed [Default] lists each componenet of the canal route separately, often resulting in a very long list.
   
   Summarized: Using this option creates a listing that summarizes Canal Segments, Drops, Turnouts, and Division Boxes separately.
   
   ![figzx](Images/Image%20069.png)
   
   The above snapshot shows a summarized listing. Notice the description column for Canal, and Drops, explicitly listing summary for a number of segments and structures respectively.

2. Clearing Depth:
   
   0 [Default]: This is the default setting, that assumes no clearing activity, and sets the clearing depth for the quantity listing to zero. Excavation and fill works on canal segements are calculated to existing ground level (OGL) formation.
   
   d>0: Using this option does two things:
   
   (a) Change listing for Clearing to the specified depth
   
   (b) Account for specified depth of clearing, when calculating cut and fill areas at each station.
   
   ![figxsec](Images/Image%20070.png)
   
   ![figxm](Images/Image%20072.png)
   
   This schematic shows how clearing depth is considered for improving the accuracy of earth work estimates. Note also that, the clearing depth is exagerated for demonstration purposes. The shaded region represents area deductions and contributions to cut and fill data, respectively, extracted in Profile Data listing. 
   
   Note: After changing this setting, update the profile data for the route using `Explore solutions > Table Data > Profile Data`. Else, the changes are not captured in BoQ listing.
   
   Below example shows the difference in quantity for d=0, and d=20cm. Notice the highlighed difference in listed clearing depth, and corresponding volumes for Excavation, Cartaway, and Fill works.
   
   ![fig2](Images/Image%20071.png)

3. Structure Reaches
   
   No [Default]: this is the default setting, and reports cut and fill volume listing with out considering those due to the structures. Note, earth works are also reported for structures separately. Therefore, this may slightly increase the quantity listed for canal earth works.
   
   Yes: This option, considers structures location in calculating earth cut and fill volumes. In this method, the begining and ending of each structure including working space at both ends is used to exclude station items from calculation. For this method, if the strucures are explored, the designed lengths are used to determine the begining and end of each structure. If not, however, a default value is used as follows:
   
   Turn Outs: 
   
   - length before station= 1.2 + sqrt(Q)  Working Space
   
   - length after station= 3.0 + Working Space.
   
   Drops Structures:
   
   - Length before station= 1.25*Drop Height
   
   - Length after station= 2.25*Drop Height

4. As may be expected, cut and fill volumes to canal segments reduce with this option enables.

> Note: Only turnouts and drops are included in the recent version. Future versions will be updated to account division boxes as well.

### Longitudinal Profile (LSec) Drawing Generation

Generating longitudinal profiles drawings, also known as LSecs, can be done either for individual canals or for a group of canals. The latter will be uising the Batch Process commands. Either way, LSecs can be generated at any desired increments, if needed creating multiple LSec drawings for a single canal route.

#### Generating Longitudinal Profile drawing for single canal route

Click on the desired route object in Plan View. The longitudnal view will be displayed on the profile view axis. 

![im96](Images/Image%20096.png)

Then:

1. Go to `Explore Solutions > Plot to AutoCAD > LSec Profile`. If table data is not complete and available, you will be prompted to extract and try again.
   
   ![image097](Images/Image%20097.png)

2. In the dialog set the station range for which the drawing is required. You can click on the more option button at the top right, you will see that you can choose to generate a 1000m long range or the entire range. Choose appropriate option, or set your own, and hit `Apply`.
   
   ![image097](Images/Image%20098.png)

3. AutoCAD will be in select mode. Pick a bounding box where you want the drawing to be placed. This is often a rectangle object. (See below on scaling of drawings).

4. Next you will be prompted to input scaling. Accept the default 0,0 if you want the drawing to fit the box selected. For standard production, you will need to set your own values.
   
   ![image099](Images/Image%20099.png)

5. The drawing is generated in AutoCAD as shown below. It contains detailed route and curve information including drops, curve markers, and range labels.
   
   ![image100](Images/Image%20100.png)

#### Generating Longitudinal Drawing for multiple ranges of a canal route

Often, a canal route is too long to create a single profile drawing. Multiple drawings are required to do the job. This can be done using the batch process option. Start by selecting the route you want on plan view. 

![image100](Images/Image%20102.png)

Then:

1. Go to `Explore Solutions > Batch Process > LSec Plot to AutoCAD`. This will invoke the dialog where you can set the station ranges you want to generate. Use the option button to see default settings. 
   
   ![image102](Images/Image%20103.png)
   
   The values are input as follows: [Starting Station, Incremental Length, Ending Station]. For the figure shown above, the route is a little over 2000 meters long. So choosing the range setting of 0, 1000, 2099.55 will create LSec drawings each 1000m long until the end of the route.

2. When prompted, pick the bounding box object. This will be the area where the first drawing will be created. The next drawings will be generated next to this box (to the right) automatically.
   
   ![image104](Images/Image%20104.png)
   
   The progress is displayed in a dialog box.
   
   ![image107](images/Image%20106.png)
   
   All the LSecs in this session will be created using the scaling you provide here.
   
   ![image105](Images/Image%20105.png)
   
   You can see that two drawings are generated, although three is expected 0-1000, 1000-2000, and 2000-2099.55 The algorithm will combine small length drawings to previous ones for presentation quality. Hence the two drawings for station ranges from 0-1000, 1000-2095.5.

#### Creating Longitudinal Profile Drawings for multiple canal routes

The steps to creating profile drawings for multiple routes are similar to the batch process workflow shown above. Before starting the process make sure all the canal routes have the necessary data for production of drawings. Then:

1. Turn-on multi-select mode from `Edit` menu, and select all the routes whouse profile drawings are required inplan view. 
   
   Tip: To select all subroutes of a given canal, you can use `Edit > Select Routes > Select Sub-Routes`. This is helpfiul to generate all QCs of a TC route at the same time, using the same scaling and appearance.

2. Start the batch process from `Explore Solutions > Batch Process > Lsec Plot to AutoCAD`. 

3. When prompted provide the scaling desired, and watch it all happen in AutoCAD.

### Cross Section Drawings

Cross-section views can be generated to AutoCAD in one of three ways. The first method allows to generate cross-sections at preset intervals. An other way is to select and plot desired stations only. The third method allows users to save specific locations whose cross-sections are required, and generate only those specific sections. 

The command to execute this task is accessible from `Explore Solutions > Batch Process > XSections Plot to AUtoCAD`.

![fig073](Images/Image%20073.png)

> Note. In all cases, the cross-section view is generated FUS with respect to the current route. This is in line with the convention adopted for profile data extraction.

#### 1. Cross-Sections at increments

To use the first method, start by switching off the XSEC toggle button at the top of the detail view area. Then start the command. You will be prompted with available options for incremental cross-section generation.

![fig074](Images/Image%20074.png)

Choose the desired option. Then an iteration for each incremental station is carried out. This attempts to generate the cross-section data at each incremental station. In this example, for instance, 7 cross-sections are found for the shown canal, i.e., at 100, 200, ..., 700m station values, and 4 columns is input which means the plot will be 2x4 array of drawings.

![fig078](Images/Image%20078.png)

Input the desired number of columns to be used for generating the cross-section drawings. The dialog shows how many drawings are selected. 

![fig075](Images/Image%20075.png)

Choose the desired scaling and presentation options in the dialog below. 

> Note: It is essential for cross-section drawings to have equal horizontal and vertical scaling. To ensure this, choose 'Plot Extents', and set scaling to desired value.

You can also include grids in the plots.

![img8](Images/Image%208.png)

The plotting progresses.

![fig076](Images/Image%20076.png)

The resulting AutoCAD drawing looks similar to below, as specified a 2 x 4 array drawing.

![img077](Images/Image%20077.png)

#### 2. Cross-Sections for custom list

You can also generate cross-sections at select stations. To do this:

start by switching off the XSEC toggle button at the top of the detail view area. Then start the command. You will be prompted with available options for incremental cross-section generation.

![fig86](Images/Image%20086.png)

Choose `Custom Value` option. This will start an other dialog with the list of all stations  where data is available for cross-section drawing.

![fig087](Images/Image%20087.png)

Choose by clicking or draging. Use CTRL + Click to select/deselect individual stations.

The plots are generated for each of the selected station as explained for the previous method.

> Note: Stations are rounded upon rendering. For instance station value 24.987 is drawn to AutoCAD with annotation 0+24.90.

#### 3. Cross-sections at saved locations

This method requires an existing set of saved stations where cross-section drawings are required. Refer to documentation on Longitdinal Design of Routes, to learn how to create and save station data for cross-section generation.

To generate drawings for saved stations:

Toggle-on the XSEC button. Any saved stations will be listed, and also marked on the profile view.

![fig88](Images/Image%20089.png)

Click on any one station marker on the profile view, to change it to active (continuous line.)

> Note: Making one of the station markers active is important. Else, cross-sections could not be created, and process will not succeed with the following message.
> 
> ![figerr](Images/Image%20091.png)

Start the command from` Workflow > Batch Process > XSection Plot to AutoCAD`. You will be promoted to confirm your desired row size for plot generation.

![fig](Images/Image%20090.png)

Provide the desired array size for creating the drawings, and Click Ok. 

Follow the proceedure for method one above to complete from this step onwards.

> Note: While in plan view, the batch process for XSection drawing generation will only create drawings for those cross-sections whose stations are included in the START and END stations of the plan view.

### Generating drawings for Canal Structures

Special structures, such as Head Regulators, Cross-Regulators and Inclined drops are designed outside of CanalNETWORK using iCAD's *CanalStructuresJET*module. A complete set of tools is available with in iCAD environment the drawinsg for these structures. 

Refere to pertaining documentation on Design of Canal Structures using FLoating Nodes, for details. Note, the drawings can be overlayed on a generated plan view to create woring drawings, such as the one shown below for canal intersection location.

![image107](images/Image%20107.png)

### Plan View

> Note: Starting from Release 1.5.3, users can access this tool right with in CanalNETWORK interface from `Workflow > Plot to AutoCAD` . The procedure is the same. 
> 
> A complete documentation will be included soon.

> ![fig92](Images/Image%20092.png)
> 
> Flexible tools are included allowing to:
> 
> - generate complete plan view, including curve, station, control and cross-section markers for selected segments, or entire route length, or user specified range.
> 
> - as well as capability to generate plan views for adjacently running canal routes (MCs and TCs for instance.)
> 
> - generate North-Free layout maps to fit selected area in AutoCAD environment, suited for the newly introduced standard of presentation.
> 
> - generate and save cross-sections for multiple stations while in plan view, using `Ctrl+G ` key combination.

Similar to Flow Sections generation method described above, a plan view is is generated using CanalStructures module in iCAD.

1. Start iCAD, if not already open, and define a session using the module over the canal route object in AutoCAD, whose plan view is desired.
   
   This will create a tentative route with two controls, one at the begining and one at the end.  

2. Populate the longitudinal profile with design data from canal network, by using `Workflow > Reload Alignment` then choose `Network Nodes`.  Choose the network host object in AutoCAD. 
   
   ![[  ]](Images/Image%20003.png) 
   
   This will read the existing design data in the host, corresponding to the route in question, and populate the graphic area with controls, drops and other details as needed.
   
   ![[  ] ](Images/Image%20004.png)
   
   *Note: There is no need to try and alter design data in iCAD environment, as the end result with not be compatible with CanalNETWORK design and can not be saved. Simply proceed to plan view generation as described below.*

3. Start a cross-section view from `Workflow > Cross-Section View.` and pick any location. This will create a cross-section view at the selected station. To create the necessary details for plan view generation to desired range of stations:
   
   ![[  ]](Images/Image%20005.png) *Screenshot showing a cross-section view at a tentative station along a canal route.*
   
   a) Use` Workflow > Go to Station` or `Ctrl + G`, and input the starting station for plan view. This will create a cross-section at the newly specified station.
   
   ![[  ]](Images/Image%20006.png) 
   
   b) Invoke liveiew from `Workflow > Cross-Section Liveiew`. This will automatically generate cross-sections at each incremental station downstream of the starting station provided above, until `Ctrl + Q` is pressed or the end of the canal station is reached.
   
   c) follow the station informaion on the descriptive text to see if the desired range is reached to stop the process, as described in (b) above.
   
   This will create and store the necessary data that will help generate the plann view.
   
   *Note: It is best to run Liveiw for the entire reach of the canal route at once, and store the data, instead of running the command for individual ranges of interest separately. Hence it is often recommended to input 0.0 for (a), and allow the lieveiw process to complete the process automatically at the end of the canal route.*

4. Start the plan view generation from Workflow > Plan View. A dialog will apear requesting specifics for the desired plan view.
   
   ![[  ] ](Images/Image%20007.png)
   
   <u>Contour Intervals</u>: the inverval value to be used to generate contour lines with the plan view. a value of <0.5 indicates, no contour is needed. Default is set to 0.
   
   <u>Length of Control Markers</u>: The length of control markers on the plan view. This will also determine the length of station/curve markers. 
   
   Note: Providing 0 value supresses all markers. Providing too large a value could result in curve markers crossing each other, giving poor presentation quality. Recommended values are:
   
   - Large canals 20-40units
   
   - small canals 5-10 units
   
   <u>Lateral Exageration Scale</u>: Often canal layouts appear as narrow and to conjusted, making it difficult to view details and poor presentation. To aid this, an exageration scale can be set between 1 to 10. Usually, 3 to 5 gives good drawings. 
   
   Note: When exageration scale is applied, the distance normal to the route center line is multiplied by the specified scale factor. True ground distance is obtained by dividing the measuered distance in AutoCAD environment to the product of  this scale value and that of the plot scale.
   
   Note: too large exageration values may distort true appearance of the layout components on edge, and RoW markers, as well as on contour lines - especially on curve locations. 
   
   Note: On posed plan view generation (generating plans of adjacent routes) the exageration scale is set to 1.0.
   
   <u>Station Range</u>: The range of values to generate plan view for. These are automatically rounded to the nearest available value on the station date list.
   
   <u>Show Route Geometry</u>: control the visibility of route center line, and all curve and control markers.
   
   <u>Fit BBox</u>: Set to None, the plan view is generated in natural North UP orientation. When set to *Pick AutoCAD*, the user is prompted to pick a bounding object  in AutoCAD. The drawing creation attempts to automatically determine the best orientation and scaling for the drawing to fit in to the selected area.
   
   Tip: Upon creating the drawing to AutoCAD the exageration scale is exported along with the north symbol. Use the `Aligned Annotation` addon tool to generate this info.

5. Upon hitting Apply, the plan view will be generated per specifications. The following two screenshots show drawing created using different options for Fit BBox.
   
   ![t](Images/Image%20008.png)
   
   *Fig: Plan view with out a BBox specified, showing view oriented on North upwards..*
   
   ![f](Images/Image%20009.png)
   
   *Fig: Plan view generated with a bounding box specified in AutoCAD for plotting, showing rotation and scaling to fit.*

6. To generate the drawings to AutoCAD, use the standard tool from `Workflow > Render To AutoCAD` or `Ctrl + P`,  The first step would be to copy the axes information to the region of plot in AutoCAD, hence choose *Copy BBox*. 
   
   ![[  ]](Images/Image%20010.png) 
   
   Then selct Plot to BBox (AutoCAD) option, and upon prompt in AutoCAD, pick the object that defines the drawing area. 
   
   ![[  ]](Images/Image%20011.png) 
   
   On On the `uiPlotOption`s dialog box, choose:
   
   a) ALL: if the plan view is generated using a fit area (as shown in the second figure above)
   
   b) specify a plot scale, otherwise.
   
   ![[  ] ](Images/Image%20012.png)
   
   *Choose Plot scaling depending on the type of plan view drawing desired*
   
   ![[  ]](Images/Image%20013.png) *Axis reference information created to AutoCAD environment*
   
   Once the axis information is created in AutoCAD, along with a referenced starting object, use `Workflow > Render to AutoCAD`, select all objects, and click `Apply`. Upon prompt, choose the referenced object, and follow the dialogs to complete generating all groups of objects to AutoCAD.
   
   ![[  ] ](Images/Image%20014.png)
   
   *Use Select All button to choose all groups of objects.*
   
   ![[  ] ](Images/Image%20015.png)
   
   *Fig AutoCAD drawing, after few edits on line colors, and text annotation creation.*
