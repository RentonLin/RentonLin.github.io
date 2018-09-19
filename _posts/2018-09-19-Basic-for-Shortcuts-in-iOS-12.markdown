---
layout: post
title:  "Basic for Shortcuts in iOS 12 (NSUserActivity)"
date:   2018/09/19
categories: iOS12
---
* What is Shortcuts in iOS 12?
  * It is an assistant that can help user find and finish what he wants to do quickly, whether by displaying elements in lock screen, Siri or Shortcuts app
* What is Shortcuts constructed by?
  * UserActivity that can be donated to show on lock screen, spotlight search, notification center, and user can tap to enter app, also can be trigger by Siri.
	* Intent that can be interacted with user by tap or Siri. Now you can even finish a task without open your app!
	* Shortcuts App(formally named Workflow): An app that can help user finish a group of tasks by click, and can be easily customized.
* What can we do with shortcuts with UserActivity?
  * Donate shortcuts
    * New a UserActivity, and set need properties
	  * Call becomeActive on the object and store it
		* iOS will learn automatically by current time, date, location and suggest this action for user later
	* Remove shortcuts
		* NInteraction.removeAll/removeWithId/removeWithIds
	* Respond to click of shortcuts
		* Add type for NSUserActivity in Info.plist
		* Implement in appdelegate
    ```
    func application(_ application: UIApplication, continue userActivity: NSUserActivity, restorationHandler: @escaping ([Any]?) -> Void) -> Bool
    ```
		* Make a class that conform UIUserActivityRestoring protocol
		  * Commonly it is your home viewController or app delegate
			* You can use navigator or router to route to specific viewControllers with info from userActivity's userInfo which was donated by you
	* Suggest shortcuts to user, and user can find in setting
		* Use INVoiceShortcutCenter.shared.setShortcutSuggestions([INShortcut]) to suggest intents for user
		* Suggest user to immediately add voice phrase to a certain shortcut
		* Use INUIAddVoiceShortcutButton to show add to Siri button
		* Use system Controller INUIAddVoiceShortcutViewController to make user input voice phrase for certain shortcuts
	* Update added voice shortcut with new voice phrase
		* Use INUIEditVoiceShortcutViewController  to make user update voice phrase for certain shortcuts
	* How to debug a shortcut
		* Setting -> Developer -> Shortcut testing
    * Show recently added shortcut
* Problems
	* When get useractivity from INVoiceShortcut.INShortcut.userActivity, the persistentIdentifier is nil.
	* In this way, I can only distinct shortcuts by some values in the userInfo
