---
layout: post
title:  "How to edit files in MacOS"
date: 2018/10/25
categories: MacOS
---
* How to do localization of app name, privacy text?
	* Get string keys
	* Localize InfoPlist.String
	* Input key = "value";
* Where are the keys of the privacy keys?
	* https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html
* What are the two different ways to declare privacy descriptions?
	* Use keys in https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html
	* Or use Privacy-xxxxxx
* How to perform choose path action, and get a path?
	* New Panel
	* Config whether file, folder can be selected
	* Present
	* Check action, if action is ok, get url from property of panel
* How to write file in folder that user selected?
	* Use panel to select a folder
	* Set com.apple.security.files.user-selected.read-write to true
