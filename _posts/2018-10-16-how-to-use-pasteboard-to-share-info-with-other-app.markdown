---
layout: post
title:  "How to use pasteboard to share info between apps"
date: 2018/10/16
categories: iOS
---
* How to install Hackintonish
	* Download system install pkg
	* Create install disk through Ubeast
	* Configure bios setting for PC
	* Insert disk to usb 2.0 port
	* Boot from usb
	* Install
	* Boot from usb
	* Install on disk
	* Boot from usb
	* Install on disk
	* Finish configure MultiBeast
		* Be careful with graphics and usb configuration
	* Reboot into mac OS
* How to encode url and decode url
	* Encode
		* Str.addingPercentEncoding(withAllowedCharset: .urlQueryAllowed)
	* Decode
		* Str.removingPercentEncoding
* How to copy text to clipboard, and get text from clipboard
	* UIPasteboard.general.string = "xx"
	* You can use setValue:ForType:to share info with other app
		* Other app can use value(forPasteboardType:) to get the value
	* You can use setData:ForType: to share UIIMage or NSData with other app
* What type of data if supported to save in the clipboard?
	* String
	* NSData
	* Image(through data)
	* Array
	* Dic
