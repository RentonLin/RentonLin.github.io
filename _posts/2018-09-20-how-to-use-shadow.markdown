---
layout: post
title:  "How to use shadow in iOS"
date:   2018/09/20
categories: iOS, Cocoa
---
* What is the properties about shadow
  * They are properties of CALayer
  * shadowColor
    * CGColor
  * shadowOpacity
    * [0, 1], 0 -> transparent, 1 -> opaque
    * 0 by default -> your shadow is not shown by default
  * shadowOffset
    * Offset: CGSize
    * When set to (0, 0), it is four boarder shadow
    * When set to (width, height), shadow.x += width, shdow.y += height
  * shadowRadius
    * Blend
  * shadowPath
    * Shadow will draw in this path if not nil, using properties from shadowOpacity, shadowOffset, shadowRadius, shadowColor
* How can you implement common shadow
  * Set the four properties
  ```
  let workView = UIView(frame: CGRect(x: 100, y: 100, width: 100, height: 100))
          workView.backgroundColor = UIColor.red
          workView.layer.shadowColor = UIColor.green.cgColor
          workView.layer.shadowOpacity = 1
          workView.layer.shadowOffset = CGSize(width: 10, height: 10)
          workView.layer.shadowRadius = 5
  ```
* How can you implement custom shadow
  * Set the four properties
  * New a path, and set to shadowPath
  let bezierPath = UIBezierPath()
  ```
          bezierPath.move(to: CGPoint(x: 0, y: 0))
          bezierPath.addLine(to: CGPoint(x: 0, y: 200))
          bezierPath.addLine(to: CGPoint(x: 100, y: 200))
          bezierPath.addLine(to: CGPoint(x: 100, y: 0))
          bezierPath.close()
          
          workView.layer.shadowPath = bezierPath.cgPath
  ```
* How can you implement shadow on round corner view
  * When clipsToBounds is set true, the layer.maskToBounds is also set to true
    * Set layer.maskToBounds back to fasle will show the shadow
  * New a new transparent view and place the origin view into it as a subview
    * Set shadow to the new view
    * Not recommended
* What if you have three views and you want to add the same shadow to them?
  * Put them into the same tranparent view
  * Set shadow to the parent view
