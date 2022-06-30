# SettingPreferences

Preferences are used to customize different aspects of software functionality, as well as appearance of design elements. They allow for flexibility in design process and presenttion of results.

Preferences is accessed from the menu WorkSpace > Edit Preferences... as shown below.

![fig1](Images/Image%20001.png)

The variable editor interface displays avaialble preferences and their settings. Each setting and their use is presented in the table below.

![fig2](Images/Image%20002.png)

## Network_Pref Templates

| Variable Name                    | Remarks                                                                                                                                                                                                                                                                                                                                                     | Sample Values |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| Parent Canal Invert(m)           | The invert (canal bed) level of the first generation canal in the network.                                                                                                                                                                                                                                                                                  | 1002.874      |
| Farm Duty(l/sec/ha)              | Old functionality, Suppressed until more use case is identified:<br/>Temporarily assigned to control canal bed design algorithm behaviour:<br/><0.001 forces down-grade slope while locating contol nodes. (no adverse slopes)                                                                                                                              | 0             |
| Node Invert Levels(m)            | Invert levels of all nodes (controls) in entire network set with respect to OGL at location.<br/>Allowable Input:  -5.0 < value < 5.0.                                                                                                                                                                                                                      | -0.5          |
| Max.Tolerance to compare FSL(m)  | \|Tolerance value for comparing FSL values during flow check tasks.<br/>0.0001< value < 0.5                                                                                                                                                                                                                                                                 | 0.005         |
| Max. Distance b/n Merge Nodes(m) | \|Distance between neighbouring / successive nodes (controls) to consider them as merged nodes.<br/>1.0< value<5.0                                                                                                                                                                                                                                          | 5             |
| Control Branch Invert(-)         | Invert level position for branch canal (merged node):<br/>1: Lock with parent invert level. Invert level to branch canal is fixed at the same level as the parent canal invert. <br/>0: Free. In this case the invert level to the branching canal is fixed using provided head loss values only. \|                                                        | 1             |
| Associated Canal on Import(-)    | Suppressed: This function is no more used in the updated release.<br> \|                                                                                                                                                                                                                                                                                    | 0             |
| Route Extension Length(m)        | \| Identifying intersection points between canal routes from AutoCAD object data may at times require extending tips. This parameter sets the allowable extension length for canals, when needed. <br> 0.5< value < 5.0<br/>Note: This does not impact the actual length of the canal routes. It is used only for computational needs.                      | 2             |
| Extrapolate Profile Data(-)      | \| Determines behaviour for transverse profile calculation. For smaller offset distances used in profile extraction:<br>0: allows no extrapolation<br/>1: allows extrapolation of available transverse profile data to include default offset ranges of -15, -12,..., 12, 15                                                                                | 1             |
| Round Dims for Construction (-)  | \| During canal section design, often constructable dimensions are required. This option determines results of bottom width design: <br>0: do not round values, use as is<br/>x: round to specified value<br/>0 < value < 0.25<br/>Note: It is important to set practical values, thus limit inputs to one of the following values. 0.05, 0.10, 0.20, 0.25. | 0             |

## NodeGraphic_Template

The values for this group of variables determine the visual behaviour for design elements in layout, profile and cross-section views of the interface.

| Variable Name                    | Remarks                                                                                                                                                     | Sample Value |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| Display Height of Node bar(m)    | Height of vertical lines representing nodes or control structures in profile view. 1 <= value <=7.5                                                         | 2.5          |
| In-Route Node Marker symbol(-)   | Marker symbol to represent in-route node locations on layout view. O= circle, S=square                                                                      | o            |
| Max. Marker Size for Nodes(Pnts) | Maximum size of markers for in route nodes. 5Points= small, 10Points= medium, 15Points= Large.                                                              | 15           |
| Min. Marker Size for Nodes(Pnts) | Minimum size of markers for in route nodes. 5Points= small, 10Points= medium, 15Points= Large.                                                              | 10           |
| End-of-Canal Marker symbol(-)    | Marker symbol to represent end-of-canal markers on layout view. O= circle, s= square                                                                        | s            |
| Marker Size for EOC(pts)         | Marker size for End-of-Canal markers:5Points= small, 10Points= medium, 15Points= Large.                                                                     | 10           |
| Available Head Margin(%)         | Margin of available head for flow check task. Nodes will be marked red, if the available flow head is less than required by the given percentage. 0<value<2 | 1            |
| Text Font Height (-)             | Size of font height to display text in graphic areas. 8Points=Small, 10Points=medium, 12Points=Large                                                        | 10           |
| Color template(-)                | Color template to use when creating graphic contents in all views.Note: The colors are also used when generating drawings to AutoCAD environment.           | Default      |

## control_BoQSettings

These variables provide key parameters for generating a representative BoQ listing for the project.

| Variable Name                  | Remarks                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Sample Value |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| B/H ratio (wall)               | Ratio of height to width to determine the thickness of vertical wall of the drop at foundation level:<br/>0<=value<=10<br/>Note: a value of 0 meanse assume a vertical wall face.                                                                                                                                                                                                                                                                                       | 0.65         |
| Excavation cut slope           | Slope of vertical excavation from surface to foundation level.<br/>0.25<value<10                                                                                                                                                                                                                                                                                                                                                                                        | 0.25         |
| Working space(m)               | desired space to maintain for working space, arround structures, canal linings.<br/>0<value<2                                                                                                                                                                                                                                                                                                                                                                           | 0.3          |
| Compacted fill Ht(m)           | Height of compacted back filll material required on excavated bottom, and below the foundation block.<br/>0<value<0.5                                                                                                                                                                                                                                                                                                                                                   | 0.1          |
| Consider Clearing Depth(m):    | Decide whether to consider clearing depth when calculating cut and fill volumes for earth work of canal segments.<br/>1: Consider clearing depth<br/>0: Do not consider clearing depth.<br/>Note: If Yes is choosen, the cut volume due to clearing depth is reduced on BoQ reported cut volume. Similarly the fill volume due to clearing depth is added to BoQ reported fill volume. If No is choosen, the effects of clearing depth on calculated volume is ingored. | 0            |
| Consider Structure Reaches(m): | Decide whether to consider the length of structures (drops, turnouts, controls, etc) and reduce cut volumes for the same in the volume reported for canal segments.<br/>Yes: excludes cut and fill volumes for structures when reporting BoQ for earth works in canal segments.<br/>No: considerst the structures as point data, and BoQ reports for canal segments may include cut and fill volumes for structures. In this case double accounting is possible.        | No           |
| BoQ List of Items(-)           | Decides how BoQ table is repoted. Detailed: a standard BoQ item is created for each component of each item. Summarized: the standard BoQ item list is created for similar items together.                                                                                                                                                                                                                                                                               | Detailed     |

See notes on Drop Design to see how these are used for specific conditions.



A detailed presentation of each parameter and results is discussed in documentation on Design Prododuction. Please refer to it.

## drop_designSettings

These parameters decide the specific considerations to be used when positioning and sizing drop structures for the entire project. See notes on Drop Design for details.
