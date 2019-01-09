---
layout: post
title:  "Is indexPathsForVisibleItems sorted?"
date: 2019/01/03
categories: iOS, UIKit
---
* How to fix bug of calling selectItem:at:position:animation of UICollectionView sometimes does not trigger isSelected state changing?
	* It seem to be a bug of UICollectionView, sometime, the when call this method, the isSelected state of the target cell is not changed.
	* Call UICollectionView.reloadData() first
	* Then call selectItem:at:position:animation
* How to draw a bezierPath with some corners round clipped.
	* Using medthod init(roundedRect: byRounddingCorners:cornderRadii)
	* You can pass needed corner to UIRectCorner
* How to get differences of a file with a history version in git?
	* Gd #md5OfCommit #filepath
* Is the first indexPath always the first indexPath in indexPathsForVisibleItems?
	* No
	* So if you want to get the topMost cell that is visible now, you should sort this array first
