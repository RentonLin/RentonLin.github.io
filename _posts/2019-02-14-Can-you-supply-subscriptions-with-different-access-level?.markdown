---
layout: post
title:  "Can you supply subscriptions with different access level?"
date: 2019-02-14
categories: iOS, iAP, Swift
---
* Can you supply subscriptions with different access level?
	* Yes
	* A subscription group can contain several subscription levels
	* Each level can have several subscriptions
	* You can make different levels having different level of accessible contents
* When user switch between different level in a subscription group, what will happen?
	* If this is an upgrade , user need pay the high price - lower price and immedietely upgrades to high level
	* When downgrade, it will take effect on the next period
	* When in the same level, if this is in the same level, and the period is the same, the change takes effect immedietely, or next period if not.
* Can you make one of your subscription not available in some country?
	* No
	* You can make your app not available in some country
* What is escaping for closure in Swift?
	* When a closure it passed to a function, and can be called after function returned, the closure should be marked as @escaping.
	* For example, you pass a closure to a function of an object, and the object stores the closure as variable for future calling.
