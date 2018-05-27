---
layout: post
title:  "Hot to get model from indexPath in a Rx way"
date:   2018-05-21 23:22:40 +0800
categories: Collection
---
* Two ways to get model from indexPath of TableView & CollectionView
  * Use indexPath and dataSource to get model
    * ```
    Observable.just(indexPath).withLatestFrom(#ObservableThatBindToYourTableView) { indexPath, datas in
      return datas[indexPath.secion][indexPath.row]
    }
    ```
  * Use model<T>(at: indexPath)
    * ```
    do {
      let element: Type = try tableView.model(at: indexPath)
    } catch {
      //work with error when cast failed
    }
    ```
    * Warning: You must specify the type of your variable.
    * Edited: 2018-05-27
    * Your can first transform the data to Any and then downcast to the type of your Model or Protocol
    ```
      let e: Any = try tableView.model(at: indexPath)
      if let t = e as? Type {
        t.foo()
      }
    ```
