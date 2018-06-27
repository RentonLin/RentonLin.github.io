---
layout: post
title:  "How to use CGGradientLayer"
date:   2018-06-27 11:59:00 +0800
categories: Collection, Swift
---
* ### How to use CGGradientLayer
  * ```
  let layer = CGGraidentLayer()
  layer.frame = CGRect.zero
  layer.colors = [color1.cgcolor, color2.cgcolor, color3.cgcolor]
  veiw.layer.addSublayer(layer)
  ```
  * Where is (0, 0) and (1, 1)
    (0,0) is the left bottom corner and (1, 1) is the right top corner
  * What is the default start point and end point
    (0.5, 0) -> (0.5, 1)
    That is middle bottom to middle top
* ### How to change distance between characters
  * Use attributedString
  * kerning can affect this value
  * Kerning is 0 by default, but it doesn't mean the distance between is 0, it means determine the distance by the font
* ### How to delete app / test 3d touch on simulator
  * Touch slightly to enable edit mode on desktop
  * Touch and press down to test 3d Touch
* ### How to copy text from simulator
  * Long click until the copy menu appears
  * Command + C
