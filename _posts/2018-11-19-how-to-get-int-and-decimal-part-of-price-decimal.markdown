---
layout: post
title:  "How to get int part and float part of a price decimal"
date: 2018/11/19
categories: iOS
---
* How to get int part and float part of a price decimal?
	* Int part: Floor((decimal as NSDecimal).doubleValue)
	* Decimal part: (decimall * Decimal(100)).IntValue - (Int part) * 100
* How to implement price with int on left and decimal part on right top?
	* Get different parts of the decimal
	* Use formater to change integer to price and delete .00 at the end
	* Place "." before decimal part * 100
	* Use two labels to represent them
	* Adjust constraints
		* Make a container view
		* Add the two views as subviews
		* Make left.left.equalToSuperview
		* Make right.right.equalToSuperview
		* Make left.right.equalTo(right.left)
		* Make container.centerX.equalToSuperView
		* Make conatiner.left.greaterOrEqualTo(superView)
		* Make right part's compressionResistancePriority to low
			* Make right part adjust fontSizeWithWidth
			* In this way when the int part is too big ,the right part will be compressed to small fonts
	*  LeftEdge     left.right    RightEdge
	*  LeftEdgeleftxxxxxxxxx.rightRightEdge
