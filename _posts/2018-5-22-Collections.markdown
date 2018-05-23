---
layout: post
title:  "Collection in 2018-05-22"
date:   2018-05-22 09:25:40 +0800
categories: Collection
---
* ### How to input special symbol in Xcode/Macos
  * Press Command + Control + Space to call out symbol keyboard
  * Choose from the symobls
* ### What does init(coder:) do
  * It is actually part of Protocol NSCoding
  * NSCoding has two methods
    * encdoe(coder:)
      * Save what you config in xib or storyboard to disk
    * init(coder:)
      * Generate Instance of your view from disk
  * If you don't use xib or storyboard
    * Just input fatalerror(error)
