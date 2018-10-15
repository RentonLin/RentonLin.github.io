---
layout: post
title:  "How to use TTS service"
date: 2018/10/12
categories: iOS
---
* How to use AVSpeechSynthesizer To speak a sentence?
	* First, new an AVSpeechUtterance with text
	* Adjust voice, rate, pre pro latency of utterance
	* New a new AVSpeechSynthesizer or reuse one
	* Use synthesizer.speak(utterance)
* How to use Objective-C Framework in Swift?
	* Drag framework to project
	* If there is no bridge file
		* New an Objective-C file and add a new bridging file(Xcode will ask you to create a bridging file)
		* Import <Module/MoudleName.h>
	* Now the framework can be used
* How to use TTS Cloud service of Google?
	* Enable Google Cloud
	* New a project
	* Enable TTS API
	* Create a  service  account key
		* No role is needed for the service account
	* Download a json version of the key
	* Set environment variable to use the JSON file(which is your credential)
	* Install and init Cloud SDK
	* Use curl to use TTS api to transform text to mp3 and save to local
		* This is a json file
	* Save value for key "audioContent", and save to a text file
	* Base64 decode this file to mp3
	* Play the mp3
	* So if you want to use this service, you must have a server do the previous steps, and then you can download the mp3 file to local and play it
