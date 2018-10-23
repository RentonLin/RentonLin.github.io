---
layout: post
title:  "How to do localization in iOS"
date: 2018/10/23
categories: iOS
---
* How to do localization
	* Strings
		* New localizable.strings
		* Add localization
		* Use NSLocalizedString(#key, #comment)
		* Use NSLocalizedStringForTable to specify a strings file to read strings
	* Image
		* Add localization
		* Set image for different languages
	* Xib, storyboard
		* Add localization
		* Adjust text and layout
* What will you get if you run 1.0 / 0.0?
	* Get infinite
	* When you transform infinite to Int, it will crash
* What is differences of Int in iPhone5 and iPhone 5s?
	* Int is Int32 in iPhone5
	* Int is Int64 in iPhone5s
* What will happen if you pass Int64 to Int?
	* In x64 devices, it's ok, they are the same
	* In armv7 devices, it will crash
* How to copy a folder in Linux
	* Copy -r #SourceFolder #TargetFolder
