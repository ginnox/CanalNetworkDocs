# Using Auto Route Design

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

## Manual design of individual segments

First, lets see the canal section design tool. This tool is availiable for a single segment in the profile view, and accesible from the `Indicator Button` in the `Assembly Pannel` pannel. 

To start it, select a desired segment from the profile view. The `Indicato Button` will be active. Click on it. The *Canal Section Design* interface will pop up.

[  ] figure.

Note: this interface starts with the hydraulic design parameters for the selected segement, and no data entry is required. 

The main purpose of this interface, among others, may be to anlyze the variation of the flow section as the slope varies. As the slope is varied, by dragging the vertical bar the flow section and corresponding flow velocity and sheat stress developed are computed and displayed. The colored scales on the gauge bars provide feedback on appropriateness of the slope.

The Solver function offers a key tool to determine the best fitting slope that respects the constraints for limiting velocity and shear stress set in the design criteria.

## Auto Designing a single segment

## Auto Designing a single route

# Design aids available for completing design of routes

Annotation minFSLoGL

Annotate frop

Math tool on ivert edit box

## AutoDesigning a selection of routes
