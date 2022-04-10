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

ThA number of table data can be generated from

### Bill-of-Quantity

Bill of Quantity document is one of the key outputs of a design task. In CanalNETWORK product, this is a fully automated process. The output can be created in many different ways.

> Note: Often, the volume of cut and fill involved for a canal route is a design decision tool. To explore these values, the best way is to use the annotation tools from `Explore Solutions > Annotators`. See relevant section in this guide.

#### Preparing for BoQ extraction

Before BoQ can be extracted accurately, all elements of the canal route - i.e., profile data and structures data must be updated. To ensure all data for the elements correspond to the most recent design changes, fully exploring solutions is a mandatory step, especially before BoQ extraction. This ensures that every element of the canal route are upto date.

 This can be easily achieved by invoking the batch process from `Explore Solutions > Batch Processes > Batch Explore SubRoutes`.

![fig6](file://C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design Production\Images\Image%20017.png)

This will invoke the following dialog, indicating which level is selected currently (in this case TC) and to confirm which levels of canals to automatically explore and update.

Once can choose a single level, or multiple levels. In either case, a confirmation is requested that lists the name and number of canals that will be processed.

![fig7](file://C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design Production\Images\Image%20018.png)

![fig8](file://C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design Production\Images\Image%20019.png)

Confirm `Go` and all relevant canal routes are auotmatically updated for the latest design data. The following dialog confirms the actions taken.

![fig8](file://C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design Production\Images\Image%20026.png)

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
   
   ![figz](images/Image%20049.png)
   
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
   
   ![figzx](images/Image%20069.png)
   
   The above snapshot shows a summarized listing. Notice the description column for Canal, and Drops, explicitly listing summary for a number of segments and structures respectively.

2. Clearing Depth:
   
   0 [Default]: This is the default setting, that assumes no clearing activity, and sets the clearing depth for the quantity listing to zero. Excavation and fill works on canal segements are calculated to existing ground level (OGL) formation.
   
   d>0: Using this option does two things:
   
   (a) Change listing for Clearing to the specified depth
   
   (b) Account for specified depth of clearing, when calculating cut and fill areas at each station.
   
   ![figxsec](images/Image%20070.png)
   
   ![figxm](images/Image%20072.png)
   
   This schematic shows how clearing depth is considered for improving the accuracy of earth work estimates. Note also that, the clearing depth is exagerated for demonstration purposes. The shaded region represents area deductions and contributions to cut and fill data, respectively, extracted in Profile Data listing. 
   
   Note: After changing this setting, update the profile data for the route using `Explore solutions > Table Data > Profile Data`. Else, the changes are not captured in BoQ listing.
   
   Below example shows the difference in quantity for d=0, and d=20cm. Notice the highlighed difference in listed clearing depth, and corresponding volumes for Excavation, Cartaway, and Fill works.
   
   ![fig2](images/Image%20071.png)

3. Structure Reaches
   
   No [Default]: this is the default setting, and reports cut and fill volume listing with out considering those due to the structures. Note, earth works are also reported for structures separately. Therefore, this may slightly increase the quantity listed for canal earth works.
   
   Yes: This option, considers structures location in calculating earth cut and fill volumes. In this method, the begining and ending of each structure including working space at both ends is used to exclude station items from calculation. For this method, if the strucures are explored, the designed lengths are used to determine the begining and end of each structure. If not, however, a default value is used as follows:
   
   Turn Outs: 
   
   - length before station= 1.2 + sqrt(Q)  Working Space
   
   - length after station= 3.0 + Working Space.
   
   Drops Structures:
   
   - Length before station= 1.25*Drop Height
   
   - Length after station= 2.25*Drop Height

4. 
   
   As may be expected, cut and fill volumes to canal segments reduce with this option enables.
   
   
   
   > Note: Only turnouts and drops are included in the recent version. Future versions will be updated to account division boxes as well.

### Longitudinal Profile Design

### Flow Sections

### Cross Section Drawings

### Plan View

Similar to Flow Sections generation method described above, a plan view is is generated using CanalStructures module in iCAD.

1. Start iCAD, if not already open, and define a session using the module over the canal route object in AutoCAD, whose plan view is desired.
   
   This will create a tentative route with two controls, one at the begining and one at the end.  

2. Populate the longitudinal profile with design data from canal network, by using `Workflow > Reload Alignment` then choose `Network Nodes`.  Choose the network host object in AutoCAD. 
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20003.png) 
   
   This will read the existing design data in the host, corresponding to the route in question, and populate the graphic area with controls, drops and other details as needed.
   
   ![[  ] ](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20004.png)
   
   *Note: There is no need to try and alter design data in iCAD environment, as the end result with not be compatible with CanalNETWORK design and can not be saved. Simply proceed to plan view generation as described below.*

3. Start a cross-section view from `Workflow > Cross-Section View.` and pick any location. This will create a cross-section view at the selected station. To create the necessary details for plan view generation to desired range of stations:
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20005.png) *Screenshot showing a cross-section view at a tentative station along a canal route.*
   
   a) Use` Workflow > Go to Station` or `Ctrl + G`, and input the starting station for plan view. This will create a cross-section at the newly specified station.
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20006.png) 
   
   b) Invoke liveiew from `Workflow > Cross-Section Liveiew`. This will automatically generate cross-sections at each incremental station downstream of the starting station provided above, until `Ctrl + Q` is pressed or the end of the canal station is reached.
   
   c) follow the station informaion on the descriptive text to see if the desired range is reached to stop the process, as described in (b) above.
   
   This will create and store the necessary data that will help generate the plann view.
   
   *Note: It is best to run Liveiw for the entire reach of the canal route at once, and store the data, instead of running the command for individual ranges of interest separately. Hence it is often recommended to input 0.0 for (a), and allow the lieveiw process to complete the process automatically at the end of the canal route.*

4. Start the plan view generation from Workflow > Plan View. A dialog will apear requesting specifics for the desired plan view.
   
   ![[  ] ](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20007.png)
   
   Contour Intervals: 
   
   Length of Control Markers:
   
   Lateral Exageration Scale:
   
   Station Range:
   
   Show Route Geometry:
   
   Fit BBox:

5. Upon hitting Apply, the plan view will be generated per specifications. The following two screenshots show drawing created using different options for Fit BBox.
   
   ![t](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20008.png)
   
   *Fig: Plan view with out a BBox specified, showing view oriented on North upwards..*
   
   ![f](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20009.png)
   
   *Fig: Plan view generated with a bounding box specified in AutoCAD for plotting, showing rotation and scaling to fit.*

6. To generate the drawings to AutoCAD, use the standard tool from `Workflow > Render To AutoCAD` or `Ctrl + P`,  The first step would be to copy the axes information to the region of plot in AutoCAD, hence choose *Copy BBox*. 
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20010.png) 
   
   Then selct Plot to BBox (AutoCAD) option, and upon prompt in AutoCAD, pick the object that defines the drawing area. 
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20011.png) 
   
   On On the `uiPlotOption`s dialog box, choose:
   
   a) ALL: if the plan view is generated using a fit area (as shown in the second figure above)
   
   b) specify a plot scale, otherwise.
   
   ![[  ] ](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20012.png)
   
   *Choose Plot scaling depending on the type of plan view drawing desired*
   
   ![[  ]](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20013.png) *Axis reference information created to AutoCAD environment*
   
   Once the axis information is created in AutoCAD, along with a referenced starting object, use `Workflow > Render to AutoCAD`, select all objects, and click `Apply`. Upon prompt, choose the referenced object, and follow the dialogs to complete generating all groups of objects to AutoCAD.
   
   ![[  ] ](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20014.png)
   
   *Use Select All button to choose all groups of objects.*
   
   ![[  ] ](C:\Users\Dell\Documents\GitHub\CanalNetworkDocs\Design%20Production\Images\Image%20015.png)
   
   *Fig AutoCAD drawing, after few edits on line colors, and text annotation creation.*

## Table Data

There are different types of data that a user can generate as tables, concerning the design work on a given canal. These are all available from `Explore Solutons > Data Tables menu`.

### Profile Data

### Flow Seciton Data

### Schedule Data

For Drops, Turnouts, DIvision Boxes, and 

### Setout Data

After generating a plan view, a corresponding setting out data is generated and displayed in the table view editor.

BoQ
