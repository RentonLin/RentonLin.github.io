---
layout: post
title:  "How to use decimal in Swift, how to display monthly price of a SKProduct with period of one year"
date:   2018-07-09 22:53:00 +0800
categories: jekyll update
---
* What is decimal
  ```
    Decimal is a structure representing a base-10 number
  ```
* What is the differences between decimal and float/double
  ```
    Float and double are NOT accurate, especially when representing price.
    They are structure representing a base-2 number.
    When deal with currency, better use decimal than float/double
  ```
* How to use decimal
  * Create a Decimal
  * Apply +/-/\*/\ to decimals
  * Use numberFormmater to change decimal to string
* How to get monthly price from a SKProduct subscription with period of one year
  ```
    //Get price of product, which is the value in the currency of the related store of your iTunes Store id
    let price: Decimal = product.price
    let monthlyPrice = price / 12
    //Transform it into string using the local of product
    let numberFormmater = NumberFormatter()
    numberFormmater.local = product.local
    numberFormmater.numberStyle = .currency
    let result = numberFormmater.stringFromNumber(monthlyPrice as NSNumber)
  ```
* How to enumrate dictionary, and what is the element
  ```
    dic.map({(key, value) -> Any
      #do with key and value
      })
    for (key, value) in dic
    Every element is a tuple with key and associate value
  ```
* What are the common ways to get sorted array
  * The element conform to Comparable protocol
  ```
    arr.sorted()
    arr.sorted(by: </>)
  ```
  * The element does not conform to Comparable protocol
  ```
    arr.sorted(by: { v1, v2 -> Bool
      #compare two element and return true if v1 should be in front of v2
      })
  ```
