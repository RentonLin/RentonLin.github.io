---
layout: post
title:  "How to send next in observer of Observer<Void>"
date:   2018-06-17 15:13:00 +0800
categories: Collection, RxSwift
---
* ### We can use () to represent Void
Use void when represent observer when you just need tell observer that certain things happens but no detail should be provided
```
let o = PublishSubject<Void>()
o.onNext(())
o.subscribe()
```
