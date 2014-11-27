---
layout: post
category: "Android"
title:  "A Simple Android APP"
tags: [android]
---

Today we write and test an app on android with Samsung Galaxy S4 , to learn how to config simple layout and use buttons. The App case comes from *Android Programming*.

#Main Files Analysis

##activity_quiz.xml

This file, automatically generated, describes the basic layout of the activity. See the description of the following:

![image1](/assets/layout.png)

The above analysis describes how to add simple element. The resource ID is used to be associate with the variables in the JAVA src. The quote of strings is shown in strings.xml. The source code in string.xml is: 

TBD (to fix the jekyll error)

So, when the text on the Button with "text @string/false_button" is "FALSE"

##QuizActivity.java

This file control all the events of the app. The analysis of the file is as the following:

![image2](/assets/java.png)

Android is event-driven, for example, activities may be triggered by clicking on a button. Android SDK provides different types of listener interfaces. Here we use View.OnClickListener to monitor a "single click" of a button.

Toast is a class to show short pop-up message. Here we use Toast.makeText(Context, int, int) to show the onclick message. 

#Running Result

![images1](/assets/1.png) ![images1](/assets/2.png) ![images1](/assets/3.png)

#Comment

##1. Anonymous Inner Class
The input parameter of setOnClickListener() is a newly created anonymous inner class " View.OnClickListener". It is better to consider the advantages and the disadvantages of it.

##2. the input parameter "Context"
Here we use " QuizActivity.this", but not “this”. Because "this" is the "View.OnClickListener".

#code address
https://github.com/ttxgz/activity_quiz/