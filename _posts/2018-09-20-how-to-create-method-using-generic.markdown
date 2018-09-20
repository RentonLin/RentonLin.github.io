---
layout: post
title:  "how-to-create-method-using-generic"
date:   2018/09/20
categories: iOS, Swift, Collection
---
* How to create a method that takes a generic type value as input, and  returns a generic type.
  * Func foo<T>(dump: T.type) -> T
  * How to use it
    * foo<Int>(dump: Int.type)
* What is frame of layer?
  * Like view and its superview
  * A layer's frame is its frame in it's superLayer's coordinate
* What does the mask property of mask mean?
  * The mask is also a layer
  * Default is nil, and all contents will be drawn
  * When it is not nil, the layer's contents will only be drawn where the mask's alpha is not zero
  * In this way you can clip layer by a sublayer(although there will not be a layer there)
* How to check a value got from json is null
  * Value is NSNull
* How to change array to set in Swift
  * Set<array>
* What is the new templates in Xcode playground
  * You can now create a viewController in the playground
* Can you test view in playground
  * Yes, use the new templates, and show the linked view
* How to implement shadow in iOS
* How to make rotate to a view
  * View.layer.transform = CATransform3DRotate(originTranform, CGFloat.pi / 4.0, 0, 0, 1)
