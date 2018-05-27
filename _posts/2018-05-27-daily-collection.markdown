---
layout: post
title:  "Collection in 2018-05-27"
date:   2018-05-27 20:47:57 +0800
categories: Collection
---
* ### How to change key binding when using a normal keyboard in MacOS
  * Preference -> Keyboard -> Modifier keys
  * Exchange Command and option
  * Of course you can also change other keys like Control, Caps Lock, Fn  here
* ### How to detect link or number in UITextView
  * property: UIDataDectorTypes
  * Change this property to what you like: .link, .address, .calendarEvent, .shipmentTrackingNumber, .FlightNumber, .lookupSuggestion, .all
* ### How to handle click of the dectected types in UITextView
  * Implete method in UITextViewDelegate
  * iOS10 and later
  * TextView(:shouldInteractWithURL:inRange:interaction:)
    * return false and handle by yourself
    * or just return true
  * There are 3 kinds of interaction:
    * .default
    * .present
    * .preview
* ### How to change double to string with formate
  * let s = String(formate:"%.2f", 0.019)
* ### How to draw a rect with round corner in context
  * Normal way
    * context.beginPath
    * move
    * drawToPoint
  * Easy way
    * Using UIBezierPath
    * In this way, drawing rect with round corner is just like new a view and set its layer's cornerRadius
    ```
    //Don't forget set path fillColor and strokeColor before stroke or fill
    let path = UIBezierPath(rounderRect:cornerRadius:)
    path.stroke()
    path.fill()
    ```
* ### How to capture several variables in closure in Swift
  * [weak v1, weak v2]
* ### Hot to make image in button fill button even if image is smaller than button's size
  ```
  btn.contentVerticalAlignment = .fill
  btn.contentHorizontaolAlignment = .fill
  ```
* ### How to bind credit card to Japanese Apple ID
  * Get a credit card with JCB, CMB JCB card in my case
  * Make sure it is ready for purchasing as Apple will try to make a bill of $0.01 when binding
  * On Mac OS, enable VPN of Japanese VPS
  * Enable global proxy
  * Open iTunes and login your Japanese App Store account
  * In account detail, edit payment method and input your JCB card info
  * Your card will have a $0.01 bill and then all is done
