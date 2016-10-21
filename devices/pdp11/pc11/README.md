---
layout: page
title: PC11 High-Speed Paper Tape Reader/Punch
permalink: /devices/pdp11/pc11/
---

PC11 High-Speed Paper Tape Reader/Punch
---------------------------------------

PDPjs implements the PC11 component in [pc11.js](/modules/pdp11/lib/pc11.js). 

A variety of [Paper Tape Images](/apps/pdp11/tapes/) have been archived, and they are typically collected in a
configuration file such as [demo.xml](demo.xml):

	<?xml version="1.0" encoding="UTF-8"?>
	<device id="pc11" type="pc11" baudReceive="9600" autoMount='{path:"/apps/pdp11/tapes/DEC-11-L2PC-PO.json"}' pos="left" width="35%" padLeft="8px" padBottom="8px">
		<name>Paper Tape Controls</name>
		<control type="container">
			<control type="list" binding="listTapes">
				<tape id="tape00" name="Bootstrap Loader (16Kb)" path="/apps/pdp11/boot/bootstrap/BOOTSTRAP-16KB.json"/>
				<tape id="tape01" name="Absolute Loader" path="/apps/pdp11/tapes/absloader/DEC-11-L2PC-PO.json"/>
				<tape id="tape02" name="BASIC (Single User)" path="/apps/pdp11/tapes/basic/DEC-11-AJPB-PB.json"/>
			</control>
			<control type="button" binding="attachTape">Attach</control>
			<control type="button" binding="loadTape">Load</control>
			<control type="description" binding="descTape" padRight="8px"/>
			<control type="file" binding="mountTape"/>
			<control type="progress" binding="readProgress" pos="default" width="250px" padTop="8px">Tape Progress</control>
		</control>
	</device>
		
The above configuration is used by PDPjs machines such as:

- [PDP-11/20 with 16Kb and Bootstrap Loader](/devices/pdp11/machine/1120/bootstrap/) ([Debugger](/devices/pdp11/machine/1120/bootstrap/debugger/))
- [PDP-11/20 with 16Kb and DEC BASIC](/devices/pdp11/machine/1120/basic/) ([Debugger](/devices/pdp11/machine/1120/basic/debugger/))