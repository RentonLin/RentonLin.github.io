---
layout: post
title:  "How can you copy an array with Int?"
date: 2019-01-23
categories: iOS
---
* How to get diff of current git folder with Kaleidoscope?
	* Set Kaleidoscope as merge and diff tool
	* gdt
* How to remove duplicated elements in array?
	* Make element conform to Equatable protocol
  * Use reduce
* How can you copy an array with Int?
	* Var newArr: [Int] = oldArr
	* Value type array are automatically copied
* How can you get a deep copy of an array with objects?
	* Enum each objects and get a copy of object
	* If you only var newArr = oldArr, you will get a new arrary filled with old elements
