# Surface modelling and Profile Extraction

Calculation and presentation of ground surface data is a key process in the design of irrigation infrastructure. iCAD product incorporates dedicated module to manage this task, and deliver results in a convenient and easy to use environment.  The module and its extended applications (for instance in CanalNETWORK product) leverage computational algorithms from within Matlab, to generate representations of surface models, and determine elevation values at specific query points. The technical details are described below.

## Surface Interpolant

Surface fitting and interpolation, as applied in the context of topographic data processing in iCAD and CanalNETWORK products, specifically refers to the use of scattered data of the form x, y, z triplet to determine a representative surface model of the form z= F(x,y) and using this surface model to generate elevation (z) values at arbitrary x, y locations. This means, data from typical surveying work or other sources that is available in x, y, z format can be used to reach at the desired surface model, and undertake subsequent tasks.

To estimate the surface model for a given set of x,y,z data, iCAD builds on scattered interpolation algorithm in matlab. This algorithm performs Delauney triangulation over the data set, with the aim of creating a surface fit made up of small triangles. A Delaunay Triangulation maximizes  the smallest occuring triangle over all triangulations og the point set. In other words, any other triangulation will have a smaller angle at vertices.

![d](Images/2.png)

It is important to note that the method:

- assumes a perfect plane inside each triangle, and 

- the elevation at any point inside or on the edge of each triangle is calaculated using linear interpolation

## Query on Topograhic Data

Once the surface interpolant is determined, elevation at querry points of x, y is detemined from the same, using the following relation ship.

z= F(x, y)

where

F= f(x,y,z) is the surface interpolant.

The surface data extraction algorithm in iCAD and CanalNETWORK software products is applied at least in the following functions:

- Point  Query: This function is used to interactively querry elevation data from x,y input obtained from the AutoCAD environment. The function reads the x, y (or E, N) data from user selection in AutoCAD, and displays the elevation value calculated from z= F(x,y)

- Profile Extraction: The fundamental input to profile extraction is an alignment path object defined in AutoCAD environment. This object provides the  x, y data at fixed intervals along the path object. The same function is applied on x,y data set to return corresponding elevation values. 
  
  ![[  ] ](Images/Fig1.jpg)
  
  *Fig: Alignmnet route, vertices and querry points*
  
  When extracting strip elevation data for an alignment object, normal lines are generated at fixed intervals. In addition to x,y data at center line - i.e., on the alignment route - other x,y data are created at offset locations specified by the user along these normal lines. The offset locations are applied on both sides of the alignmnet. The resulting x,y data set forms a strip area along the alignment route. The elevation data at this data set is calculated from z= f(x,y).
  
  ![[  ]](Images/Fig3.jpg) 
  
  *Schematic showing Alignment route, normals and querry points*

Note: The intervals for extracting profile data are specified by the user. The algorithm includes vertex points along the alignmnet route object, but the user has the option to exclude these points during the extraction process.

- Profile Reload tools: Sometimes engineers want to modify alignment routes to meet some design requirements. This is naturally handled with in the AutoCAD environment. In such cases, both iCAD and CanalNETWORK products offer a function that allows reloading profile data for an alignmnet object whose vertices are modified. Reload functions essentially repeat the profile extraction steps described above using  settings used to create the original profile data.

## Extrapolation

The implementation of the surface interpolant function in above described querry methods of either iCAD or CanalNETWORK product, allows extrapolation to determine elevation data ouside the area covered by input x,y data set. This meanse, the implementation can estimate elevation values for points outside the boundary area defined by the inpit data set. 

![[  ]](Images/Fig2.jpg) 

*Schematic showing point data set, boundary area defined by the data set, and querry points for extrapolaiton.*

It is important to note that:

- The returned values are derived from linear extrapolation

- the reliability of the values returned decreases significantly as the querry points move away from the boundary area, original data set. 

Hence, the extrapolation capability is to be considered as only a complimentary feature to obtain a crude estimate of terrain variation beyond the boundary area. There is no guarantee that designs based on extrapolated data will be of acceptable quality and accuracy.

## Curve Handling During profile extraction

Curves, if found in the AutoCAD alignment object, will be considered while extracting prorfile data. The requirements for succesful data extraction are:

- the begining and ending segments of the alignment route must be straight segments of at least 20meters.

- Curve radius of 20m or larger



The schematic below shows detailed curve information extracted.

![curve](Images/Image%20curve2.png)



For straight segments, the incremental distance specified will be used. Where curve arcs are encountered an incremental distance of 5meters (or close) is used to extract profile data at finer resolutions. This will allow adequate representation of key points along the alignment in creating plan views and accurate bill-of-quantity estimates at a latter stage.



> Note: Curves must be at least 20m radius, and have a curve length of at least 25 meters to be considered for detailed extraction. This is hard-codded in the software, considering the constructable range of curve sizes.



Short curves will still be approximated by about 5m increments, but the curve information will not be captured. Only curves whose information is succesfully extracted are shown in profile views.



After extracting profile information in iCAD, the data table will display information related to curves, if available.

![im](Images/Image%204.png)



* Curves (233/187) show that 187 of 233 arcs are extracted for curve information.

* del L= -0.20480m indicates the station variation to be expected as a result of the arcs that do not meet the curve size specification, and hence are approximated using ~5m small segments of straight lines.

> Note: the curve information in above dialog is available only after extraction of profile data. It is not shown when viewing existing data.



A typical profile data is represented as follows:

![im](Images/Image%20006.png)



Cross-section views from `Workflow>Show Section` show a transverse variation of ground level at the station of choice.

![im](Images/Image%20007.png)





END.
