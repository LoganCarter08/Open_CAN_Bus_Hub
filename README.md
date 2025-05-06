# Open CAN Bus Hub
An open source alternative to a CAN bus hub primarily used in aftermarket automotive industry. 

## Overview
This project is intended to reduce the cost of a simple part needed for many project cars. If you are building a car and need to add aftermarket equipment via CAN bus you will likely need a hub of some sort to distribute the network to each of your devices. 

The existing products like [AEM](https://www.aemelectronics.com/products/ev_conversions/wiring_shop/wiring_harnesses/parts/30-2225?srsltid=AfmBOopf-43udBTczr3DMtdVAqn7zBDi4FWJSfJJbkCLwWn_8UP-PhpX) and [Haltech](https://www.haltech.com/product/ht-159000-elite-can-hub-4-port-dtm-4/?srsltid=AfmBOop2I1wcCl7ELiAaJ4Hz_9G2S5Ku90I_iyAMGlEmO2NZ8aU0mGMG) are very expensive, are limited to three devices after connecting the ECU, and require external resistor termination. This project addresses these issues. 

This project will walk you through building your own CAN bus hub to meet your needs. 

## Design Notes 
* The industry standard for automotive CAN bus has become DTM plugs, so utilizing these was a priority
* Minimizing the number of wires to keep complexity and risk of issues was the primary priority. Later versions may attempt to eliminate the need for any wires regardless of number of rows. 
* Handling high(ish) current was something we regarded as important as users may be powering many devices from one hub. See the important section for more info on power capabilities. 

## IMPORTANT
* Do not exceed 10 amps total on the hub. This means all of your plugs combined should not exceed 10 amps. It would be ideal to put a fuse prior to the hub to ensure this is not exceeded. Read the PCB readme for more information on amperage. 
* Do not exceed 7 amps total on each of the plugs. The DTM pins are only capable of 7 amps and so is the PCB. Read the PCB readme for more information on amperage. 

## Tools Needed 
1. Soldering iron 
2. 3D printer (read FAQ if you do not have one)
3. Allen keys 
4. Needle nose pliars 
5. Wire strippers (only needed if doing more than one row)

## Parts Needed
1. Solder 
2. 3D printer filament (ASA is recommended for automotive)
3. 2mm diameter by 4mm long socket cap bolts 
4. 3mm diameter by 12mm long flat head cap bolts
5. 2mm diameter by 4mm long threaded inserts 
6. 3mm diameter by 4mm long threaded inserts 
7. 120ohm resistor (if adding a termination resistor)
8. PCB (view readme in the PCB folder for more information)
9. Wire (if using more than 1 row)

## Assembly
TODO 

## FAQ
**Q. What pin orientation is used?**

A. The intended orientation is what Link ECU uses, but should also work with Haltech and others. You may notice that in both versions pins 1 and 2 power and ground and pins 3 and 4 are CAN low and CAN high. Power and ground pins can be interchanged and so can the CAN low and high as long as every device that is plugged into this hub follows this standard. If this isn't clear just think of the markings on the PCB as CAN 1 and CAN 2. They don't actually care if they are high or low. They are just marked to make it easier for assembly. Same with power and ground. These are sized the same internally, so you could use the power pin as the ground and vice versa if you need to for your application. 

Link's orientation: 

![Link ECU CAN pinout](/Images/link_ecu_can_bus_pinout.png)

Haltech's orientation (wire side): 

![Haltech ECU CAN pinout](/Images/haltech_ecu_can_bus_pinout.png)


**Q. I only need x number of PCBs and it is more expensive to order small amounts.** 

A. If you are in the US feel free to contact me. I might have some available and if not I may do a bulk order, depending on interest, to lower the cost per individuals. I can do the same with the pins and resistors too. Shipping outside of the US will likely be more expensive than you ordering them from a manufacturer directly. 


**Q. Can I sell these?**

A. I put this project under an MIT license. You are free to sell them if you would like. I would just ask that you reference back to this project so it can help people who are looking for a DIY solution. 


**Q. What if I don't have a 3D printer?** 

A. Depending on your budget or needs you can either find a 3D printing service to print it for you, look for local hobbiest with printers, check your local library for printer usage, or you can contact me if you are in the US.


**Q. Do I need to know CAD?**

A. CAD skills are really helpful here. The design is partially parametric, but it is missing brackets for mounting. These will likely need to change per user, so they are not included in the model. I will likely upload some STEP files with some sizes with random mount designs just to give people options. Visit the readme in the Model folder for more information. 


**Q. Do I need to know PCB design?**

A. Not unless you need to make changes to the design or want to contribute to the project. 