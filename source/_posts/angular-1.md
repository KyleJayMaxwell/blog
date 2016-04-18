---
title: Angular Two-Way Bindings
tags:
  - Angular
  - Tutorial
categories:
  - Tech
date: 2016-04-17 09:00:00
---


## Angular Tutorial #1

[Github Repo](https://github.com/KyleJayMaxwell/angular-levelUpTuts-1)

### Understanding Data bindings
##### -Classic Templates

In most classic template systems, they merge both the template and model together into the view, which is what the client sees. There are a few problems with method.
  1. Once the template and model both merge, any changes made to the model after will **NOT** go through the the view. 
  2. Anything that the user changes will not effect the view either. Making more work for the developer, who has to write code that syncs the view with the model and vice versa.

Visual example of the classic data binding system:
One Way Binding:
![Picture of One-Way Data Binding](https://docs.angularjs.org/img/One_Way_Data_Binding.png "Classic Data Binding Diagram")

##### Angular Template
In angular things work a bit differently. The template is made of uncompiled HTML, markups and directives, which is then compiled in the browser. The compilation step then makes a live view, this especially means that any changes in either the view or model will mirror each other. In essence the view is now what the **SUDO** or **Single-Source-Of-Truth**, basically meaning that the view is now a instant reflection of your model. While the view is just a mirror of the model the controller is separate from the view and won't register it. The reason for this is because of testing, we can now test the controller without the view or any browser dependencies/DOM.
Visual example of the Angular data binding system.

Angular Two Way Binding:
![picture of two way data binding](https://docs.angularjs.org/img/Two_Way_Data_Binding.png "Angular Binding Diagram")

##### Example
In my project that I made we are using a built in directive of angular, ng-model where we assign it a variable name. Like this,  
`<input type="text" ng-model="yourName" placeholder="Enter Your Name Here.">`  
I am creating the directive ng-model to basically store some data from this input, with the variable name of "yourName". Now without anymore work, angular will now be saving what we type when we type it, to your variable name. Angular is then looking for `variable name` wrapped in double brackets, to fill from the model. So in this case, `<h2>{{yourName}}</h2>` whatever we type in the input field will also be added to the header too. The great thing is it will automatically do this without us having to save, so we can just type. In my example too, I used it to change the background color also. `<body style="background:{{yourName}}">` if we type a color name or hex code it will change the color of the background also. Showing the power of angular.