# CanalDRAIN Docs

## General Assumptions and Conventions

Once network is resolved and sized, the design of individual routes shall be executed from the most downstream to upstream. This would be incotrast to the design of routes in supply canal network, where task progresses from upstream parent canal to downstream branch canals.

## UI for DrainNETWORK

No FSL-OGL criteria in design criteria, hence no annotators and related features.

## Design Criteria for DrainNETWORK



## Routes

Namin styles MD, SD, TD, FD 

Default design criteria for drain canals

dashed line style if invert diff between end and bed is le o, contrast to supply network

## Node Invert:

Nodes represent segments downstream

always attempted to locate nodes meet CTL==OGL. (to avoid unnecessary cut)

minFSL-OGL set to -99

stBranchRaise='Free'

mFSD=-99 Full supply depth

DHD= -1*DHD*

DBL Design

- drop adjust funcitons

- DBL create, and draw

- fitForNoDrop

reverse geometry analysis in comparison to supply canal drop positioning.

Node inverts for branch inlets are positioned to a maximum of:

- OGL-CTL of Branch at control

- CBL at collector canal.





## DBL Design and recomended practice

MD->SD...

Invert changes at controls in recieving canals impact hydraulics at juction with feeder canals, particularly the inlet invert. DBL drawing for branch drains may show oddly positioned bed levels, because existing data relects previous invert locations. 

![fig1](Images/Image%201.png)

This can be easily corrected by clicking on the node, and using `Ctrl+R` or redraw. To reduce/avoid this step deesign/explore from downstream to upstream.

![fig2](Images/Image%202.png)

, especially near segments close to the recieving canal. Accordingly prev
