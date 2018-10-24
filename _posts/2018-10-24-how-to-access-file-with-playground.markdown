---
layout: post
title:  "how-to-access-file-with-playground"
date: 2018/10/24
categories: iOS, Playground
---
* How to transform string to bool?
	* (Str as NSString).boolValue
* How to get a mapped list from list in Python?
	* [e.xx(), for e in list]
* How can playground read and update data files from Swift playground?
	* Import playgroundSupport
	* Create folder with ~/Documents/Shared Playground Data
	* Access file in this folder with XCPlaygroundSharedDataDirectoryURL.appendingPathComponent("xx.xx")
* How to enumarator files in a folder?
	* Get FileManager.default()
	* fileManager.enumarator(atPath:isDirectory:true)
	* For url in enumarator {
	* #procress
	* }
* How to get type of an any?
	* Type(of: xx)
* How to solve stuck in Swift playground if you do heavy work?
	* Playground is by default iOS
		* Remove UIKit
		* Change to MacOS project may help
* How to launch app with specfic language?
	* Add arguments in scheme
	* -AppleLanguage "en"
