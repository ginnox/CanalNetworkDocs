# Layout plans and Network Resolution

Refer to the standard workflow for using CanalNETWORK software. One of the input data is a layout map in AutoCAD. This section discusses the task of importing such a layout map from an AutoCAD environment, and processing the connectivity data for the network of canals. Most of the task is handled automatically, while it needs some assistance from the user to resolve some issues that may linger.



## AutoCAD canal layout maps

The AutoCAD layout maps must fulfil certain conventions to be used in the CanalNETWORK software environment. The following are essentially assumed to be true in the AutoCAD source drawing:

1. All routes are drawn using Polyline command. Any object drawn with the Line command can not be processed, and will be excluded. It causes error on subsequent tasks.

2. All canal routes are drawn from upstream to downstream directions. 

3. All canal routes start and end with a stratight segment of at least 20m. 

4. All canal routes are drawn to scale of 1:1, and to world coordinate system (WCS).



Best practices for layout drawings include, but are not limited to:

1. Organization by layer: it is very helpful to collect canal routes of similar generation or level to one layer. Users have, while working on a number of projects, observed that this will greately enhance key batch tasks later. For instance, collect all TC (teritiary canals) to a separate layer, say *TC Canals*. Similarly, collect all quaternary level canals to a separate layer called, say, *QC Canals*. And so on.
   
   

2. Intersection of canals: The points where any two canals intersect will form a junction node. Nodes constitute a baseic data block for network analysis. Therefore, all canals must be drawn with care - especially near the begining and the end. The following are key recommendations:
   
   * where to canals offtake from a single parent canal, make sure they intersect the parent canal at the same point.
   
   * Where two canals offtake from a single parent canal, make sure they do not intersect themselves any where other than the point where they intersect the parent canal. This may be the case where the starting segments of the branch canals are either parallel, or the cross the parent canal at slighly different locaitons. If necessary edit the first or second vertext of one of the canal routes to avoid parallel.
   
   * If possible avoid curves on intersection points of parent and branch canals.
   
   * end of canals not close to other canals with in extension distance

3. All routes must end at sufficient distance from other canal routes. (Sufficiently farther than the extension length and node merge distance parameter values in `Network Preferences`, which are often set at 2m and 5m respectively.) 



> Note: The amount of time spent to resolve a network analysis, depends little on the size of the irrigation area or the number of canals. Rather it greately depends on how strictly the above guideline is adhered to in preapring the layout map.



For this reason, it is highly recommended that the engineer responsible for preparing layout maps must be aware of these guiding rules and assumptions.





## Network resolution: Definition

Network resolution is a term used to represent the task of analysing the connectivity between each canal route in the canal network system, and ensuring that each canal in the network has ONLY one parent canal.



Where this basic criteria is not met across the system of canals, the network is NOT resolved, and progress to the subsequent steps (for instance Network establishing in the standard workflow) is bound to abort with an error of some sort.



After a succesful network resolution task, the user can do the following:

1. Automatically generating ordered and sequentila naming for all routes in the network.
   
   Some canals may need to be manually named depending on specific needs of the project. These canals can be assigned NAME EXCEPTIONS. A common example is a TC branching from another TC. This route will be automatically named a QC, but the user can assign in a TC level as an exception.
   
   

2. Plot these namings to AutoCAD environment with desired text specification (height, font,...)

3. Use the resolved network structure to group canal routes by generation and instance them in AutoCAD, for batch processing at a later stage.



Lets now see how layout maps prepared in AutoCAD are imported to CanalNETWORK environment and analyzed for connectivity.

## Importing layout map to CanalNETWOK environment

The first step is to import the drawing to the CanalNETWORK environment. To do that, follow below steps.

### Import single routes



### Import instances



### Import by layer



## Node Identification

There are two types of nodes.

1. Canal junciton nodes: are created where a branch canal meets a parent canal. These are represented as circles.

2. End of Canal Nodes: are created where a canal route terminates with out connection to a branch canal. Such nodes are represented as squares.



[  ] figure: Node types and appearance.

Note: The size of the nodes as they apear on the plan view can be customized in Node graphic.





The second step is identifying nodes. To start the automatic process:



> Note: It is recommended to change the view to layout view. The other parts of the interface are not of much use at this stage.





## Identifying Connectivity Issues and Resolving them

The user may expect two types of isses with the connectivity established from above step.

1. Multiple BoC

2. Unresolved EoC nodes





Multiple BoC issues automatically

Click on table, 

Back in CanalNETWORK, use Ctrl+G (Go to ) key combination. This will zoom in to the are where the issue is noted, and selects the specific node with the issue.

- detach one the canal with the issue



Re run the test, to verify all issues are succesfully resolved, or new issues are not created in the process.



## Resolving EoC Nodes with Branches

Manual



AutoMatic








