---
layout: post
title:  "Daily collection 2018/05/19"
date:   2018-05-19 00:42:40 +0800
categories: jekyll update
---
1. How to use timer with RxSwift
* Problems with NSTimer
  * NSTimer will retain target which often cause retain cycle.
* How to use timer with RxSwift
```
        let o = Observable<Int>.timer(#dueTime, period: #lap?, scheduler: scheduler).subscribe()

        //DueTime is the the first time you will timer to fire
        //Lap is the inter-period between after fires, if nil is provided, the timer will only fire once. In this way you can create repeat timer and unrepeat timers
        //Scheduler: Scheduler where you will your timer to fire

        //Warning:The following timer will never fire unless you subscribe it.
        let o = Observable<Int>.timer(#dueTime, period: #lap?, scheduler: scheduler)

        //How to stop a timer? Just dipose the subscription
        let disposebal = Observable<Int>.timer(#dueTime, period: #lap?, scheduler: scheduler).sbuscribe()
        disposebal.dispose()
```
2. When will subscription release in RxSwift?
* Disposebal.dispose(by: disposeBag)
  * Subscription blocks(nextBlock, errorBlock) and the values retained by them will be released when disposeBag is released
  * Normally we create a disposeBag as a property of current object, when current object deinit, its disposeBag will also deinit, which cause all subscription blocks and value they retained to reduce reference count.
  * So if you retain Self in the blocks, onNext block for example, subscription and self retain each other, which will cause memory leak.
* Observer.onError(error), onComplete()
  * If the observer calles its onError() or onComplete(), the subscription will also release
  * A common scene for this is the UI actions, when UI element deinit, their observables, button.rx.tap or collectionView.rx.modelSelected will  also dispose
* Edited: 2018-05-27
  * Another way to control dispose of your Subscription
    * Using takeUntil
    ```
      //before you subscribe your observable, use takeUntil operator to make your observable dispose at a specific time
      let o.takeUntil(self.rx.willDealloc).subscribe{#subscribeCode}
    ```
3. How to use ssh key to communicate with remote repository
  * Create ssh keys pair
    * ssh-keygen
    * Default private key and public key is stored in ~/.ssh/
  * Add to ssh agent
    * ssh-add ~/.ssh/private_key_file
  * Add ssh public key to repository holder
    * Github account preference
  * Test
    * ssh -T git@address_to_repository
