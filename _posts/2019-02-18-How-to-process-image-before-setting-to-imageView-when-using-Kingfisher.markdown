---
layout: post
title:  "When using Kingfisher, how to process image before set image?"
date: 2019-02-18
categories: iOS, Kingfisher, Swift
---
* When using Kingfisher, how to process image before set image?
	* You can supply processor in options
	* The final image is cached and returned
	* You can create your own processors
* When using imageProcessor in Kingfisher, which image will be cached?
	* Default the final image will be cached.
	* But you can add .cacheOrigin to cache origin image.
* When using imageProcessor in Kingfisher, what should you do if you want to cache origin image?
	* Add .cacheOrigin option
* How to enumerate from 10 to 0, 0 included or not included?
	* Not include the end
		* For x in stride(from: 1 to: 10, by: 1)
			* 0...9
	* Maybe include the end
		* For x in stride(from:1 through: 10, by: 1)
			* 0...10
