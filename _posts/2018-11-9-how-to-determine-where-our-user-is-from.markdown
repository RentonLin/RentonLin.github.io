---
layout: post
title:  "How to determine where our user is from"
date: 2018/11/9
categories: Ads, iOS
---
* How to determine where our user is from? Organic or not? From which ads platform? Form which campaign?
	* Enable IDFA Track
	* Install AppsFlyerSDK
	* Set appsflyer delegate
	* In the delegate method, you can get the values about current user
	* Available keys and values are here
		* https://support.appsflyer.com/hc/en-us/articles/207032096-Deferred-Deep-Linking-Getting-the-Conversion-Data#ResponseKeys
