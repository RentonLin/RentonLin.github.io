---
layout: post
title:  "How to distinguish client languages from http request"
date: 2018/11/5
categories: iOS, Backend
---
* How to map a dictionary to another dictionary?
	* You can write an extension, new a new dictionary
	* Get the transform block
	* And set key value to the new dictionary
* What is the protocol that make the class object able to change to string?
	* CustomStringConvertible
	* This is a protocol with one method: description
	* This is not only for debug print, is also used for change objects to strings, like to a url
* What is the debug version protocol that make the class object able to change to string?
	* CustomDebugStringConvertible
	* Swift works for any type, but it is discouraged to use this directly
* How should you return contents of different languages according to client requests?
	* Respect accept-language in http header
* How should throw exceptions and how should you write method that can throw?
	* Throw error
* What is the differences between normal refresh and hard refresh on frontend?
	* All the js files are refreshed in hard refresh
