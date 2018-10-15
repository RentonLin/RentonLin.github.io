---
layout: post
title:  "How to write UnitTests in Xcode"
date: 2018/10/15
categories: iOS, Xcode
---
* How to write UnitTests
	* New target
	* Add test classes to target
	* Be careful of the FIRST principles
		* Fast
		* Independent
		* Repeatable
		* Self validating
		* Timely
	* Write tests for asynchronous operations
	* Faking objects
* How to run UnitTests
	* Command + U to run all tests
	* Click icon beside test file to run all tests in the file
	* Click icon beside test function to run the test
* How to test OC class in UnitTests?
	* Import OC class to the test target
	* Import head file in bridging file
		* Module name can get from framework's modulemap file
	* Write test code
* How to test OC framework in UnitTests?
	* If using cocoapods, the UnitTests target also need pod installed
	* New a bridge file, and set bridging file to the file you created
		* Add import <#ModuleName/header.h>
	* Write test code
