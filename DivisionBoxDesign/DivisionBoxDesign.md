# Design of Division Boxes

CanalNETWORK software can handle the design and estimation of canal junction structures. By default, every canal junction is designed as a turnout structure. If any junction is required to be designed as, and function as, a division box structures, the user must indicate this by checking the *Div. Box* check box on the Node Edit panel.

![[  ]](Images/Image%20001.png) 

*Division Box check box in Node Edit Panel.*

> Note: A confirmation is required to proceed. The message box informs the user of eminent changes to the data of the node in question.

This guide describes the method and procedure used in the design and documentation of division box structures in CanalNETWORK product.

## Design Approach to Division box

The design approach implemented in CanalNETWORK product is taken from a guideline from ECDSWCo. (See Reference at the end). The division box design method adopting broadcrested weir as flow divisor is implemented in CanalNETWOEK product.

The governing flow equation is:

Q= 1.7 B H^(1.5)

Where:

- Q is the discharge flowing over the crest

- H is the head of flow overt the crest

- B is the overflow length

The soution to this equaiton is determined based on the Modular Limit criteria. This means that, the flow over the weir is independent of variations in tail water level. For this to occur, the tail water energy level must not rise above a certain percentage of the upstream energy head over the weir crest.

The steps implemented in the solving algorithm are:

1. Assume a headloss value, z

2. Determine H1, the the upstream energy head over the weir crest
   
   Determine H2, the taile water energy level
   
   Determine B, the required overflow wisth from the Broad crested weir equation.
   
   B= Q/1.7/H1^(1/5)

3. If z>=H1/3 and H2/H1<0.66, modularity condition is satisfied
   
   Else, repeat from step 1.

If the modularity condition can not be met after adequate number of iterations, the algorithm aborts and:

![[  ]](Images/Image%20002.png) 

*Error message reporting failure to succesfully solve for modularity condition.*

a. An error message, such as below, is reported

b. The check mark assignment is reversed, and the junction is retained as a turnout structure.

An error message can also arise if the incoming and outgoing discharge to the division box do not match.

![[ ]](Images/Image%20007.png) 

*Error message for unbalaned discharge condition.*

Upon succesful solution to the above iterative process, the algorith assigns dimensions to the corresponding banching canal as  follows:

* Overflow Width, B= max (0.3, H1, Lc/5), where Lc= 2*H1

* Crest Height, ds= Crest Level - Parent Invert

* CBL branch= CBL parent + Y - z - y, where Y and y are the flow depths in the parent and branch canals respectively.

* L branch= 5*(H1-H2) 

The actual dimension tables and designed invert levels for the parent and branch canals can be found from `Explore Solutions > Data Tables > Explore Division Boxes`.  A table similar to below content is displayed.

![[  ]](Images/Image%20005.png)

![[dsfs]](Images/Image%20006.png)

*Typical report generated for the design of a division box.*

## Generating Design Report

The results of the above algorithm for a certain division box can be generated from the `R` (Redesign) button located right next to the *Div. Box* check mark in the Node Edit panel area.

Click on this button, a report of similar to the one shown below is generated.

![[  ]](Images/Image%20003.png) 

*Report generator setting dialog.*

![[  ] ](Images/Image%20004.png)

*Sample report for a division box design*

### BoQ generation

BoQ is estimated using the dimensions generated in the preceeding table, and the standard drawings below.

![gdfgd](Images/Image%20008.png)

![fdsa](Images/Image%20009.png)

A sample BoQ for a division box looks similar to below output.

![dasas](Images/Image%20010.png)

*Sample output of BoQ listing for a division box.*

END.



Regerences: A guideline for Design of Division Box Structures, Feb 2015, IDFP Design Team, Water Works Design and SUpervision Enterprise, Addis Ababa.


