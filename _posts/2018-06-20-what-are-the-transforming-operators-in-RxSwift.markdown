---
layout: post
title:  "What are the transforming operators in RxSwift"
date:   2018-06-20 22:02 +0800
categories: Collection, RxSwift
---
* ### What are the transforming operators in RxSwift
  * #### Map
    * Transform element to other, just like map in Swift
  * #### FlatMap
    * Generate a new type of Observable to each element, and merge all the new Observables and subscribe to it
    * Be careful, any observable sending error will make the terminate the observable
  * #### FlatMapLatest
    * Generate a new type of Observable to each element, and only subscribe to the newest Observable
    * You can use this to deal with error events and filter them
  * #### Materialize
    * Observe to events of an observable
  * #### Dematerialize
    * Get element from event, used with Materialize
* How to use [SwiftRichString](https://github.com/malcommac/SwiftRichString) to generate attributes string
  * Create a style object and call setStyle on string
  ```
  let style = Style {
    $0.color = UIColor.white
    $0.alignment = .center
    ....
  }
  let hello = "Hello".set(style: Style)
  let world = "world".set(style: Style)
  print(hello + world)
  ```
  * You don't need to remember all those keys.font congratulations
