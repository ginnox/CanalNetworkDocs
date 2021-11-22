# About Design Criteria

Establishing a set of design criteria is the basis of design work. These data are also the key input data for tackling the sizing and detailing of a network of canal system in CanalNETWORK.

Design criteria in CanalNETWORK, specifically refer to a list of parameters that defined and set to a specific value correponding to the design task required. This parameter list is constantly refered to by numerous design tasks, with out the need for the user to input data every now and then. 

> Note: As parameters in Design Criteria set are constantly refered to in the design process, it is IMPORTANT to spend adequate time to set values. This will save significant time later.

## Contents of Design Criteria Set

The following groups of criteria set are defined and available in the software:

1. CBL Design Settings: These parameters are used to dictate the placement (position) and size of drops when creating canal bed level design information.

2. Command Criteria: The parametrs in this group determine commanding variables related to the supply and distribution of water in the network.

3. Construction Variables: These parameters define the assembly information for canal sections to be used when creating cut and fill section geometries.

4. Hydraulic Design Variables: As in above, these parameters set design specifications for the geometrical shape and size of the flow section to be used for water conveyance.

These groups of parameters are carefully set for each level of canal that may exist in the project. In a typical project, for instance, MC, SC, TC, QC and FC may exist. For such a project, there are five levels (or generations) of canals, and each level is provided a separate set of values for the above group of parametrs.

## Detail Definition of Design Criteria Parameters

Before diving in to detail discussion of parametrs and their meaning, it is worth while to understand the concept of controls.

Controls are points along a canal route that may represent a phyisical structure (e.g., turnout, division box) or a theoretical control point which is known to result in a change of either hydraulic parameter, geometrical shape of canal section, or other. As such, controls define segments of a canal route. Each segment is therefore comprised of well known and fixed hydraulic and geometrical paramters.

In the sample network of canals shown below, the MC canal feeds four sub canals. Therefore, the branch locaitons represent a physical control point. As can be seen in the correponding profile view, these are represented by solid vertical bars. In plan view they are represented with small circles as Nodes. Such controls are automatically identified and positioned by the software.

![](DesignCriteria/Images%20for%20Design%20Criteria/Image%20001.png)

[  ] image  plan

The user can also introduce fictious controls for design purposes. This could be to change the hydraulic characterisics or the construciotn details of a canal reach. The 

[  ] image profile

Controls are built on a number of Node, and Segment Assembly parameters. These parameters represent hydraulic and geometric conditions UPSTREAM of the control. Changing a parameter on a control, therfore, affects ONLY the canal reach or segment located upstream of that control. 

In essence, therfore, design criteria values constitute the node and geometry parameters of controls in the entire network, depending on the location of the controls. The below sections present a detailed desctiption of each parameter in the design criteria set, and discuss how they impact design or hydraulic behaviour. 

### CBL Design Settings

These parameters are used to dictate the placement (position) and size of drops when creating canal bed level design information. 

> Note: CanalNETWORK software automatically designs canal bed level information, and ALWAYS uses the values for in this group of Design Criteria parameters.

#### Prefered/ Max Drop Height(m):

There are different ways to set value for this parameter

* Single value: (Fixed Drop Heigh design) specifies the maximum drop height allowed for the canal level. This value is also used as standard drop height to be applied at all the locaitons, except the last drop.

* two values: Not allowed

* Three values: (Variable Drop Height design) specifies setting for canal bed level design by inserting variable drop heights depending on two conditions: (a) terrain variation and, if specified corresponding FSL variation, (b) Provissions of 

[  ] *Fig showing Drops created using a set of three values. Whenever feasible with in presctibed prefered control spacing (150m in this case) the prefered heigh is applied. If not increment/ or decrement is applied. This results in a vaiable drop height design*

[  ] *Fig showing Drops created using a single value that specifies a standard drop heigh (in this case 1.50meters).*

Note: In each case, the last drop is automatically sized to meet the remaining head loss in the canl reach. The values above do not control the last drop in a reach.

#### Minimum Drop Height(m):

This value specifies the minimum allowed drop height in the canal segment. All drops inserted will observe this limit, except the last drop.

#### Min. Control Spacing (m):

This parameter specifies the minimum allowable spacing between drop structures. CBL generated attempts to ALWAYS maintain the provisions in this parameter when positioning drop structures.

There are two ways to set and use this parameter:

* Single value: specifies an absolute minimum that must be maintained between successive drops.

* two values: in addition to above, the second value specifies a prefered length between drops. This second value is used ONLY if variable drop height specification is used in *Prefered/ Max Drop Height* above.

#### Fit Height

This parameter dictates how canal bed levels are positioned with respect to prevailing OGL along the profile of the canal route. Values impact behaviour of design as follows:

* *fitHt <=0* : ensure the vertical distance between `OGL and upstream invert level` at each drop fulfils this value. This is widely used in the network.

* *fitHt>0*: ensure the vertical distance between` FSL and OGL `at each drop meets this value. This is often applied for feeder canals, who supply water to farm blocks, and must mainatin a certain head above ground level.

* *fitHt=-99:*  this value represents 'Not Applicable.' Canal segments with this value setting are designed for no drop.

> Note: If fitHt is set to -99 (not applicable), the control invert level is automatically calculated and set. Hence, the user can not manually raise or lower the invert levels. To allow this, the user must clear this value and set a proper value. 

#### FIt Type

The setting in this parameter is used to determine where in the reach drops must be located:

* *first:* inserts drops at the first location where the CBL/ or FSL (depending on fitHT setting above) meets the OGL. This setting tends to reduce fill volumes and increase cut volumes.

* *last:* inserts drops at the last location (same as above.) this setting tends to increase fill volumes and reduce cut volumes.

[  ] *Figure showing drop positioning along a canal reach using First and Last options.*

### Command Criteria

The parameters in this group of Design criteria set the governing hydraulic parameters for the canal network system, inview of desired operational conditions.

#### Canal Duty (l/sec/ha)

This value is derived from cropping pattern and climatic conditions of the irrigaiton area, The values are determined for the different canal levels depednig on expected operational losses. This value is used to size all the canal segments in the network according to the following relation ship:

Qi= dutyi x Ai

where Ai is the cummulated area that each segment serves downstream.

Note: Area served by each canal and its segment is automatically cummulated. However, the either draw farm blocks in AutoCAD and import them to the network workspace, or use AutoEstimate tool to define the area seved by each feeder (lowest level) canal. The software then handles the cummulating of areas upstream toward the first level canal.

#### Min FSL-OGL @ Controls(m)

This value controls the invert level of all the controls along a canal with reference to desired FSL level over prevailing OGL at the control. Two ways are available:

* *>-99* value ATTEMPTS to meet FSL-OGL at each control is greater than set value. The status is indicated in the detail view axis, as well as using `Explore Solutions > Annotators > Min FSL-OGL`.  Red color text indicates this setting is not met, and design review is mandatory.

* *=-99* means this value is not applicable for controls along the canal. The status is still shown as above, but color coding is not applied. 

[  ] *Figure showing FSL-OGL conditions at control for a criteria settinhg of 0.50m* 

#### FSL-OGL Control type

This must ALWASYS be set to US Control. It specifies that Min driving head calculations are made with reference to FSL upstream of the control.

#### Min FSL-OGL @Reach(m)

This value can be set to help design process by showing which parts of a canal reach meet this requirement, and which do not.

* *>0:* When invoked from, `Workflow > Design and Analysis > Show FSL-OGL for reach`, will show reaches of the canal route and available FSL-OGL equal to or above specified value. This is applicable to lowest level feeder canals expected to supply water to farm areas.

* *=-99* meanse this parameter is not applicable, and invoking above command shows  no information. This is typically the value for all canals, except feeder (lowest) level canals.

[  ] *Figure showing FSL-OGL values graphically, showing areas that meet or exceed the MIN FSL-OGL=0.50  Note: The figure is example only, and this criteria may not be required to be set for MC type canals.*

#### Min Drv. Head @Control(m)

This value dictates the head to be maintained at each junciton node (or control structure) when positioning bed levels for branch canals. This value is ALWAYS maintained between FSL of parent canal and FSL of branch canal. However, the final CBL for the branch canal also depends on the *Branch Invert Raise* parameter setting below,

[ ] *Figure showing bed level of Branch Canal (SC_2) with respect to parent canal (MC) based on Min Drv Head value of 0.30 (a) Branch Invert Raise= Free, (b) Branch Invert raise= Fixed)*

#### Branch Invert Raise (-):

This value dicates how invert level for branch canals is set with respect to CBL of parent canal at the control location:

* Fixed: forces to fix the CBL invert of branch canal to the same level as that of parent canal

* Free: positions CBL invert of branch canal regardless of parent CBL value at control, rather respects Min Drv Head values (above.)

### Construction Variables

This group of design criteria parameters dictates the assembly information for canal flow section (Lined or unlined), and their placement with respect to prevailing ground level variation in transverse direction (using cut and fill shape specificaiton). 

#### Canal Lining type, Ltyp(-)

Specifies if a canal segment is provided with lining, and the type of lining:

* *=-1:* The canal segment has no lining, canal section is applied to existing formation as is. Both the lining nor the foundation thickness values (below) are ignored.
  
  

* *=0:* The canal segment is lined with a thin lining provision. The canal lining thickness value (below) is taken in to account to form the geometry of the lining.
  
  

* *=1:* The canal is Lined with thick structure. Here both the lining and foundation thickness value(below) are taken in to account to form the shape of the lining.



[ 3 figures] *Figure showing Unlines, Lined (Thin) and Lined (Thick) flow sections.*

#### Lining Thickness, Thk(m)

This parameter sets the value representing the thickness of lining to be applied (See above for *Canal Lining Type*). A minimum value of 0.05m and a maxiumum value of 0.30 is allowed.



#### Foundation Thickness, THK(m)

This sets the value for the thickness of the canal lining at the bottom (See above for *Canal Lining Type*). A minimum value of 0.3 and a maximum value of 0.6 are allowed.



#### Earth cut shape, Smc(-)

This parameter specifies how the formation level varies in the transverse direction in cut conditions. The values are supplied in triplets, and upto three triplets are allowed. Each triplet has the specification [w, m, h].

* w, m, h: Single triplet specifing - consequetively - a working space width (for thick lined canals) or berm width (for unlined and thin lined canals), a cut slope (mH:1V), and the height through which this cut slope is applied.

* h is set to Inf (Infinity) for the last entry in single, double or triple entry method.



[ ] *Figure showing a canal section in cut using single and double entry methods*



> Note: The triplets in both Eatch and FIll shape specification must be of the same size. This means even if double triplet is needed ONLY for the cut shape, the fill shape must also be double triplet. In this case simply repeat the first triplet, then set w to slightly greater than the smallest allowable value (0.05m, say 0.051).



#### Earth fill shape, Smf(-)

This parameter serves the same function as *Earth Cut Shape* parameter above, but in Fill condition.

* w, m, h: single triplet specifiying - consequetively - top berm width (for unlined and thin lined canals) or formation width beyond canal lining for (thick lined canals), fill slope (mH:1V), and height through which the fill slope is applied. 

* h is set to inf (Infinity) for the last entry.



[ ] *Figure showing a canal section in cut using single and double entry methods.*



### Hydraulic Design

This is the last group of parameters in the Design Criteria set. It detemines how canal flow sections are sized and positioned for the diffenernt segments in all of the canal network. For a given canal level, the following parametrs and their uses apply:





#### Min. Design Discharge(m3/sec)






#### Design B to D ratio(-)




Limiting Velocity(m/sec)




Max. All. Shear Stress (Kg/m2)




Mannings Roughness, N(-)




Freeboard, FB(m)




Canal Side Slope, m(-)




Bed Slope, So(m/m)




