# Farm Blocks and Network Sizing

One of the key strengths of CanalNETWORK software is high level of task automation avaiable for time consuming and error prone tasks. Once a network of canals is succesully imported and resolved, subsequent tasks are easy to manage, giving users a quick turnarround time for their projects. Farmblock analysis functionality is one of such many features.

Farmblock tools assist to identify and calculate irrigation areas for the lowest level(s) of canals in a given netowrk, and cummulate the values towards the primary level canals. This process facilitates two important stages of the design:

1. Accurately determine the net irrigable area of the network, or its sub-networks, or any other level of canal.

2. Size each segment of canal in the entire network with our requiring further input from the user (using duty assigned in the design criteria).

Sizing of canal segments, refers to the determination of amount of discharge passing through each segment of each route of the network canals.

These, otherwise time consuming tasks can be completed in a matter of a few seconds in CanalNETWORK software, with quality and speed.

## Working with Farm Blocks

First, let's see ways to create farm block information. There are two methods:

1. Read drawing objects representing farm blocks in AutoCAD. This is the most accurate method, and also can be very time consuming.

2. Automatically estimate the area each canal may be serving. This is a quick process, and also the least accurate. Note that this is only an esimtate.

The two methods are described below.

### Farmblocks from AutoCAD

To read farmblock area data from AutoCAD, first create the farm blocks using polyines. There are a few ways to draw farm blocks.

* Field canal irrigating to both sides: Draw ensclosing polyline objects around the area served by the field canal. 
  
  ![s](Images/Image%20001.png)

* Field canal irrigating only either to the left or to the right: creat a polygon area covering the area served by the canal, and add a zero area extension at a location convenient to cross with the feeded canal.
  
  To add a zero area extenaion, click on the boundary and hover over the vertex you want to edit and choose `Add Vertex` menu item.
  
  ![s](Images/Image%20003.png)
  
  Pick a location over the other side of the canal.
  
  ![s](Images/Image%20004.png)
  
  Finally modify the resulting geometry by moving the next vertes to over lap with the previous vertex.
  
  ![s](Images/Image%20005.png)
  
  ![s](Images/Image%20006.png)
  
  The final geometry is shown above. This ensures the the area crosses the desired canal route, with out any change on the area of the block area delineated (hence the term zero-area extension.)

> Note: Each farmblock area should cross ONLY one serving canal. The converse is also true, i.e., each canal should only be crossed by one farmblock boundary. Otherwsie, the first canal that is found to cross with a given farmblock is assigned the area of the farmblock. 

Once these are ready:

1. Collect all farm blocks to fascilitate easy import. This can be done in either of two ways. Either instantiate all the farm blocks in to one or few host objects, or construct/ move all farm block boundaries to a separate layer.

2. To import from a host instance object go to `Workflow > Farm Blocks > (Re)Import Farm Blocks...` menu command. To import from layer go to `Workflow > Farm Blocks> (Re)Import Farm Blocks By Layer...` Both methods are valid.
   
   ![s](Images/Image%20007.png)
   
   This will start the *Choose* dialog. 
   
   ![s](Images/Image%20008.png)
   
   If importing for the first time, or desire to overwrite all existing associated data, choose `Reset All`. If you want to append the current collection to the existing data, choose `Update Only`.  For the case under consideration, Reset All would be the right choice, so hit the corresponding button.
   
   ![s](Images/Image%20009.png)
   
   Confirm the action in the dialog.
   
   ![s](Images/Image%20010.png)
   
   The *Done* dialog completes import process. The farmblocks imported are shown in the layout view area overlapping the network elements.

At this stage you can view the quantities of areas associated to each serving canal route, by using `View > Route Text > Select & Show Text...` and picking `A` field in the dialog.

![s](Images/Image%20014.png)

You can also generate a table from `View > Workflow > Farm Blocks > Edit Blocks...` , and selecting `Current` when prompted.

![s](Images/Image%20017.png)

![s](Images/Image%20015.png)

![s](Images/Image%20016.png)

One can modify the block data for any one route at any time, in one of two ways:

(a) by simply ReImporting the farm block object corresponding to the route. In this case you should choose `Update Only` button when prompted.

(b) by starting the Edit Block menu command, choosing `Reset` and editing the areas manually. Some times, geometrically editing farm blocks may not be a choice for the engieer. Rather editing a table may be required. This may be the case for canals in existing projects whose area is already prescribed. In this case:

1. Start Edit Blocks menu command as above

2. Choose `Reset`. This will erase any cummulative area information in the network and reset data to the original data during import.

3. simply start editing in the table, and hit `Apply`.
   
   ![s](Images/Image%20019.png)

You can see that, the area corresponding to the parent canal is 0.00. This is because it does not serve a particular farm block. The area it serves shall be determined from cummlative of the areas that the sub-canals serve individually. To do this, 

1. First select the primary most canal for the network, to indicate the final direction of cummulation.

2. Then go to `Workflow > Farm Blocks > Edit Block Areas...` and choose `Cummulate` button.

3. The table data is updated to show the cummulated area each route is serving, as shown below. Hit `Apply` to continue to the next step.
   
   ![s](Images/Image%20018.png)

> Note: Area served is shown as a label in the layout view area ONLY for canals associated with Farm Blocks. Other canal routes will show Canal capacities as available.

> Note: If farm block data is updated, DO NOT forget to cummulate areas again to reflect the changes in the table, and `Apply` the new figures to the data base.

### Automatically created farm parcels

Where fast estimates are required, the auto estimator tool can be used. The tool is available from `Workflow > Farm Blocks > Auto Estimate...` as shown below.

![fig50](Images/Image%20032.png)

Note: This should be applied on a fully resolved network, else errors will be encountered in the process.

To use the tool:

1. Start it as described above.
   
   Upon initiating the warning dialog appears, reiterating the results - if any is found - are approximate.
   
   ![fig51](Images/Image%20022.png)
   
   Accept the subsequent confirm action messages. 
   
   ![fig52](Images/Image%20023.png)

2. Next, you are prompted to provide a bugger distance. This value is used to determine the distance beween adjacent farm blocks. Note the value is a negative value, indicating that the areas determined will be shrinked away from boundary lines determined by the algorithm.
   
   ![fig54](Images/Image%20024.png)

3. The final result is presented as shown below, giving the sum total of farm parcel areas found for the network. You can see that the blocks are only calculated for the last generation canals.
   
   ![fig55](Images/Image%20025.png)
   
   The process ends with the below dialog.
   
   ![fig57](Images/Image%20026.png)

The above process, has already assigned each route in the network with the corresponding estimated areas of the farm parcel area. This can be viewed from `Workflow > Farm Blocks > Edit Block Area` command. The procedure is same as that for the manual process described further above.

The table will display a result similar to below snapshot.

![fig65](Images/Image%20028.png)

You can select/deselect parcels by left-clicking on them, and choose to delete them.

> Note: Delete job can not be undone. You will have to regenerate the blocks again.

 You can also view the size of selected parcels by rightclicking on them and choosing `Properties`.

![fig62](Images/Image%20027.png)

### Editing Automatically created farm blocks

Farm blocks automatically created can be edited and updated by using the context menu accessed by right-clicking on any block.

To select blocks for processing, click on the desired blocks. The blocks will be selected or deselected accordingly. Use `Select All` option to select all blocks.

![ima32](Images/Image%20034.png)

To view area and associated property, use the `Properties` context menu.

![ImagAr](Images/Image%20035.png)

To Delete blocks, use `Delete Block(s)` context menu. This is helpful, when canals that do not supply water to fields are assigned a block.

You can also draw the farm blocks to AutoCAD. This allows to easily edit the vertices of each farm block and update from it. To achieve this a farm block host object is required. The object must be referenced to the comman area reference axis, and tagged appropriately.

To Link a Host Object: go to `WorkFlow > Farm Blocks > Host Object` . 

![imagHost](Images/Image%20036.png)

This will display the dialog showig the contents of the selected host object if any are found. Click on the `Link` button to accept.

![imagdlg](Images/Image%20037.png)

Note: The menu item now shows the changes made.

![imagnew](Images/Image%20038.png)

To draw blocks to AutoCAD, select the desired blocks and choose the `Draw to CAD` context menu. This will create the drawings to AutoCAD. You can edit the vetrices of any of the blocks.

![imag29](Images/Image%20041.png)

To update from the drawings, select the desired blocks to update, and choose `Update from CAD` context menu. A dialog will show 

![imag40](Images/Image%20042.png)

Such work saved in AutoCAD can be reloaded to the CanalNETWORK environment using `Workflow>FarmBlocks> AutoEstimate...` tool, if the FarmBlock Host object is available and linked.

Tips:

- It is highly recommended to create and use a separate layer to contain the host object and the blocks of farm parcels. With the number of objects increasing in the AutoCAD environment, it may be hard to keep track of changes, and accidentally delete uninteded objects that may cause problems at later stage.

- Using `Edit > Highlight Selection in AutoCAD` helps to know which block is for which route while working in AutoCAD.
  
  You can not import farm blocks using manual steps, while a FarmBlock host object is linked to the current workspace. The following message will appear if attempted.
  
  ![figinfo](Images/Image%20043.png)

### Important Notes about Farm blocks

Farm blocks are expected to meet few requirements to be succesfully imported, and linked to, network of canals.

* All farm blocks must be made of polyline objects

* All farm blocks are expected to cross ONLY one canal route. This will not cause an error. However, In case of multiple intersections are found, the block area is associated with the route whose intersection is found first.

* It is highly recommended that they contain no Curved segments. FarmBlocks are imported as segments of straight lines, and hence all curve information will not be considered. This does not cause an error. However, it may lead to unwanted confusion regarding intersecting routes. Consider the below example.

![Image40](Images/Image%20040.png)

Here, the Farm-block corresponding to SC_1 has a curve tracing the curve of the main canal (as shown in the highlighted area.) Upon import to network, the curve information is not considered, and the Farm block will have the geometry shown below.

![Image413](Images/Image%2041.png)

As a result of removing the curve, the farm block now happens to cross not only the intended SC_1 route, but also MC. This may result in linking of farm block to MC, instead of SC_1. 

## Working with large networks

Working with large netwroks can pose some challenges when dealing with farm blocks creation. This can be easily solved using the sub-network view feature. This feature limits the displayed network to all branches of a given route. There are two ways to start this function.

1. Go to `View > Sub-Network` menu. The first time, the list contains only one item, Click on the `Re-create Sub Networks` item.  This will analyze and group your network in hirarchies. 
   
   ![fig65](Images/Image%20029.png)
   
   To view this, restart the command again. You will now see a list of items, and sub items.
   
   ![fig68](Images/Image%20030.png)
   
   Click on any one item, only the corresponding routes will be displayed.
   
   ![fig69](Images/Image%20031.png)

2. The other method is to use `View > Go to Route...` menu or `Ctrl+G` for short. Select the desired route on plan view, and start the command. 
   
   ![fig70](Images/Image%20033.png)
   
   Accept OK on the dialog, and this will retain only relevant canal routes in the view.

You can work on any sub-network, as you would on the entire network. The changes will only affect the network in view.

# Sizing Networks

Sizing networks is a quick process, that fully relies on the farm block data prepared using the above steps. It determines the amount of water discharge that must be transported in each segment of the each route of the canal network. To start the fully automatic process:

1. Make sure there are no selection(s) in the plan view, by right clicking on the layout view area and selecting `Clear Selection`.

2. Start the menu command from `Workflow > Network Rating/Capacity`.  
   
   ![s](Images/Image%20020.png)
   
   ![s](Images/Image%2021.png)

3. Choose `Resize All` This will do the calculation for the entire network, and display the resulting information in the layout view area. If no information is shown, toggle the text comonent from `View > Route Text > Toggle Text On/Off` .

![s](Images/Image%2022.png)

> Note that text label for canal capacities follow the notation  X+YYY, where X denotes capacity in cubic meters per second, and YYY denotes capcity in litres per second.

END.
