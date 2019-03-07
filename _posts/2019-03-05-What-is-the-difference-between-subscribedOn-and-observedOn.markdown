---
layout: post
title:  "What is the difference between subscribeOn and observeOn"
date: 2019-03-06
categories: iOS, Swift, RxSwift
---
* What is the difference between subscribeOn and observeOn?
	* subscribedOn makes the subscribeBlock run on certain scheduler
		* In which events are generated
	* observeOn makes the observeBlock run on certain scheduler
		* In which user reacts to the elements generated
* How to use dispatchQueue in Swift? How to get certain priority queue?
	* DispatchQueue.main.sync/Async()
	* DispatchQueue.global(qos: DispatchQos.QoSClass)
* What is the level of QoSClass?
	* userInteractive
	* userInitiated
	* Default
	* Utility
	* Background
	* unspecified
* How to transform range to array?
	* Array(0..<10)
