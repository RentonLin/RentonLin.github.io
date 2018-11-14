---
layout: post
title:  "How to add an imageView to collectionView as background"
date: 2018/11/14
categories: iOS, UICollectionView, CALayer
---
* What are the three ways to track where is the user from?
	* Idfa and cookie
	* Google play url
	* Common info
		* Device id
		* Mac address
		* IP address
		* Device name
		* Wifi mac address
		* Region
		* Local
* How to add a view to collectionView's background and send to back?
	* The view should be userInteractive set to false
	* Add it as subview
	* Send back
	* Make layer's zposition to negative value
* How to set substring's attributes for an attributes string?
	* In SwifAttributed string, get range of substring, check if it is NSNotfound
	* If not, set(style: forRange:)
