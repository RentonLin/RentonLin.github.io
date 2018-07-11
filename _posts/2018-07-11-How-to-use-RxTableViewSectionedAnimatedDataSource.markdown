---
layout: post
title:  "How to use RxTableViewSectionedAnimatedDataSource"
date:   2018-07-11 23:59:00 +0800
categories: RxSwift RxDatasource
---
* How to implement UITableView with sections and headerView footView with RxSwift
  * Use RxTableViewSectionedReloadDataSource
  * ```
  //Create a data type which is the element for a cell
  struct CustomElementType {
    var text: String
  }
  ```

  * ```
  //Create a type conform SectionModelType which is the element for a section
  //Here we use header to represent headerView
  //You can also add a property like footer to represent footerView
  struct CustomSectionDataType: SectionModelType {
    var header: String
    var items: [Item]
    typealias Item = CustomElementType
    init(original: CustomSectionDataType, items: [Item]) {
      self = original
      self.items = items
    }
  }
  ```

  * ```
  //New datasource with section model type
  //Config each cell with each element
  let dataSource = RxTableViewSectionedReloadDataSource<CustomSectionDataType>(configureCell: { datasource, tableView, element(<--CustomElementType) -> UItableViewCell in
    //create and return your cell here
    })
    ```

  * ```
  //Config titleView for section
  //Get title from SectionModel
  dataSource.titleForHeaderInSection = { (ds, section) in
    let sectionModel = ds.sectionModels[section]
    return sectionModel.header
  }
  ```

  * ```
  //new section models
  let sectionDatas = [CustomSectionDataType(header:"section0", items:[Item]),
  CustomSectionDataType(header:"section1", items:[Item]]
  ```

  * ```
  //Bind data to UITableView
  Observable.just(sectionDatas).bind{to: tableView.rx.items(dataSource: dataSource)}.dispose(by: #yourDisposeBag)
  ```
  * ```
  //If you have different types of element in cells, you may wrap your final model in CustomElementType
  struct CustomElementType {
    var text: String
    var exactModel: Any
  }
  //when config cell, downcast exactModel to your model type, and fill cell
  ```
* How to implement UITableView with animation while insert or delete with RxSwift
  * Use RxTableViewSectionedAnimatedDataSource
  * How does this work?
    * RxTableViewSectionedAnimatedDataSource is built on top of RxTableViewSectionedReloadDataSource
    * RxTableViewSectionedAnimatedDataSource keep latest value, when get a new value, it compare two value, and then make tableView animation like insert or delete
    * CustomSectionDataType conform to AnimatableSectionModelType, where you need to provide a unique id for each sectionModel, which helps datasource to find which sectionModel is new and which sectionModel is deleted
    * Element conforms to IdentifiableType and Equatable, where you need to provide unique id for datasource to find which rows are deleted and which rows are added
  * How to use
  ```
  //make element in each cell conform IdentifiableType, Equatable
  struct CustomElementType: IdentifiableType, Equatable {
    var id: String
    var text: String
    typealias Identity = String(<--can be Int)
    var identity: Identity {
      return text
    }

    func ==(lhs: CustomElementType, rhs: CustomElementType) -> Bool {
      return lhs.id == rhs.id
    }
  }
  ```
  ```
  //See AnimatableSectionModelType
  struct CustomSectionDataType: AnimatableSectionModelType {
    var uniqueId: String
    var header: String
    var items: [Item]
    typealias Item = CustomElementType
    init(original: CustomSectionDataType, items: [Item]) {
      self = original
      self.items = items
    }
    typealias Identity = String(<--can be Int)
    var identity: String {
      return uniqueId //Use this
    }
  }
  //create models and bind to RxTableViewSectionedAnimatedDataSource, that is almost same with reloadDataSource
  ```
  ```
  //Do not rebind observable to UITableView, which will result in fatalerror in Debug, and reloadData(with no animation) in Release
  Observable.just(models0).bind(to: tableView.rx.items(dataSource: dataSource))
  Observable.just(models1).bind(to: tableView.rx.items(dataSource: dataSource)//<--This will cause fatalerror in Debug
  ```

  ```
  //Even if you dispose previous bind, and bind a new observable, there will be no animation
  //No animation:
  let modelsObservable1 = PublishSubject<[CustomSectionDataType]>()
  modelsObservable1.asObservable().bind(to: tableView.rx.items(xxxx)).disposed(by: disposeBag)
  disposeBag = DisposeBag()
  let modelsObservable2 = PublishSubject<[CustomSectionDataType]>()
  modelsObservable2.asObservable().bind(to: tableView.rx.items(xxxx)).disposed(by: disposeBag)
  ```
  ```
  //This is the prefered way
  let modelsObservable = PublishSubject<[CustomSectionDataType]>()
  modelsObservable.asObservable().bind(to: tableView.rx.items(xxxx)).disposed(by: disposeBag)
  modelsObservable.onNext(v1)
  modelsObservable.onNext(v2)
  ```
  ```
  //IdentifiableType can be the same, but it will raise fatalerror in Debug, and just reload (with no animation) in Release
  ```
