---
layout: post
title:  "How to create an Alfred workflow"
date: 2018/10/12
categories: Alfred, iOS, Python
---
	* When test local notification triggered by calendar date, what should you be careful with
		* While adjust system time, do not cross the trigger time
		* It seems that every time you select a date, even you have not click pop button, the local notification will be rearranged
	* When you test iAP, what should you be careful with
		* The system time must be correct
	* How to draw a shape on a layer
		* New a CGShapeLayer
		* Create a CGPath
			* You can also create a CGPath with a UIBezierPath
		* Set shaperLayer.path = path
		* ```
			* Let layer = CGShapeLayer()
			* Layer.frame = CGRect(x:0, y:0, with: width, height: height)
			* let bezierPath = UIBezierPath(roundedRect: frame, byRoundingCorners: [UIRectCorner.bottomRight, UIRectCorner.topRight],  cornerRadii: CGSize(width: 50, height: 50))
			* Layer.path = bezierPath.cgPath
		* ```
	* How to clip a view as you wish
		* New a CGShapeLayer and set path to
		* Set layer.mask to shapeLayer
	* Python: How to make utf-8 code enable in your python file
		* Indicate encoding utf-8
		* # -*- coding: utf-8 -*-
	* Python: How to read string from file
		* F = Open(#path, #mode)
		* F.readlines()
	* Python: How to get lines from file and enumerate them
		* Lines = F.readlines()
		* For line in Lines:
	* Python: How to replace substring in string
		* Str.replace(#replacedString, #newString)
	* Python: How to concat string list
		* '\n'.join(stringList)
	* Python: How to take value from input
		* Import sys
		* Let param1 = sys.argv[1]
	* How to write a workflow in Alfred
		* Drag Trigger/Input
			* Trigger
				* Hotkey
				* Keyword
				* Snipper in other app and others
			* Input
				* When using hot key, clipboard/current selection text is supported
				* When using keyword, you can pass text after keyword
		* Action/Script
			* Action
				* Open file
				* Open app
				* And many others
			* Script
				* Using input to do actions and sys.stdout.write(output) to produce output to the next  step
		* Output
			* To clipboard
			* To file
			* Notification
