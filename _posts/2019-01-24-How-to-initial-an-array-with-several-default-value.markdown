---
layout: post
title:  "How to initial an array with default value of n zero"
date: 2019-01-24
categories: iOS
---
* How to initial an array with default value of n zero?
	* Init(repeating: #Value, count: #n)
* How to get bitmap data of UIImage? How to get color of specific pixel?
	* Let width = image.size.width
	* Let height = image.size.height
	* Let provider = image.cgImage!.dataProvider
	* Let providerData = provider!.data
	* Let data = CFDataGetBytePtr(providerData)
	* Let numberOfComponents = 4
	* Let offset = (width * y + x) * numberOfComponents
	* Let a = data![offset]
	* Let r = data![offset + 1]
	* Let g = data![offset + 2]
	* Let b = data![offset + 3]
* How to change 0xff to 0xff00?
	* First, from 0xff -> 0xff0, value is multiplied by 0x10 or 16
	* So, from 0xff -> 0xff00, value is multiplied by 0x100
* How to loop from high value down to small value? How to custom loop start value and end value and step?
	* For i in stride(#startValue, through: #endValue, by: #offset)
* 1s = ?ms
	* 1000
* How to change a color image to gray image?
	* Use cifilter
