# Design Production

There are different products that you can generate from a succesfully compelted design for a canal route. These are:

### Table Data

### Bill-of-Quantity

BoQ

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
