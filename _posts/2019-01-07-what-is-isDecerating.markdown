---
layout: post
title:  "Will isDecerating be true when you call selectItemAt:postion:animated: of UIScrollView?"
date: 2019-01-07
categories: iOS, UIScrollView
---
* What is sectionInsect in UICollectionView?
	* Top is the first cell's top from bottom of headerView. Be careful, top is not calculated from the top of headerView to previous section.
* Will isDecerating be true when you call selectItemAt:postion:animated: of UIScrollView?
	* isDecerating is true when scrollView is moving after user lifts finger
	* So this is not called, when you set UIScrollView's offset with animation.
* How to implement cell's size changing animation.
	* Implement new size in collectionView:collectionViewLayout:sizeForItem:
	* Call collectionView.collectionViewLayout.invalidateLayout()

