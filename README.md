# TIL (Today I Learnt)

Inspired by @jbranchaud's [repo](https://github.com/jbranchaud/til) and @thoughtbot's [repo](https://github.com/thoughtbot/til)

This project is a collection of small things I learn about different languages, frameworks and technologies.
It consists of short markdown documents summarising concepts or tips I'd like to share.
The goal is to write something new everyday or as often as possible.

Currently: 106 TILs

---

# Categories

* [Arduino](#arduino)
* [Command line](#command-line)
* [Computer Science Jargon](#computer-science-jargon)
* [CSS](#css)
* [Data Structures and Algorithms](#data-structures-and-algorithms)
* [Electronics](#electronics)
* [Front-End](#front-end)
* [Git](#git)
* [HTML5](#html5)
* [Java](#java)
* [JavaScript](#javascript)
  * [Design patterns](#design-patterns)
  * [Node](#node)
  * [React](#react)
* [Machine Learning](#machine-learning)
* [Processing](#processing)
* [Random](#random)
* [Raspberry Pi](#raspberryPi)


# Arduino

* [Setup the correct baud rate in the Serial monitor](arduino/baudRateSerialMonitor.md)
* [Play .wav files on Arduino without an SD card](arduino/wavFilesWithoutSdCard.md)
* [How to read resistors](arduino/resistors.md)
* [Using a mini breadboard](arduino/usingMiniBreadboard.md)
* [Some prototyping vocabulary](arduino/prototypingVocabulary.md)
* [Difference Voltage and Current](arduino/voltageCurrent.md)
* [Ohms](arduino/ohms.md)

# Command Line

* [How to kill all instances of Node.js servers](commandLine/killNodeServers.md)
* [CLI tools](commandLine/cliTools.md)

# Computer Science Jargon
* [Pure functions](csJargon/pureFunctions.md)
* [Tight coupling vs loose coupling](csJargon/tightCouplingLooseCoupling.md)
* [Higher-order functions](csJargon/higherOrderFunctions.md)
* [Programming paradigms](csJargon/programmingParadigms.md)
* [Basic CS terms](csJargon/BasicCsTerms.md)
* [Interpreter vs compiler](csJargon/interpreterCompiler.md)
* [Expressions](csJargon/expressions.md)
* [Compound assignment](csJargon/compoundAssignment.md)
* [Scope](csJargon/scope.md)
* [Closure](csJargon/closure.md)
* [REPL](csJargon/repl.md)
* [Polymorphism](csJargon/polymorphism.md)
* [Graph traversals](csJargon/graphTraversals.md)
* [Composition & Inheritance](csJargon/compositionInheritance.md)
* [Predicate function](csJargon/predicateFunction.md)
* [Type introspection](csJargon/typeIntrospection.md)
* [Abstract syntax tree](csJargon/ast.md)
* [Dynamic programming](csJargon/dynamicProgramming.md)
* [First-class citizen](csJargon/firstClassCitizen.md)

# CSS
* [Mix Blend Mode](css/mixBlendMode.md)
* [CSS Reset](css/cssReset.md)
* [Feature queries](css/featureQueries.md)
* [Inherited & Non-inherited Properties](css/inheritedAndNonInheritedProperties.md)
* [CSS Specificity](css/specificity.md)
* [:empty](css/empty.md)
* [widows](css/widows.md)

# Data Structures and Algorithms
* [Binary search](dataStructuresAlgorithms/binarySearch.md)
* [Linear search](dataStructuresAlgorithms/linearSearch.md)
* [Insertion sort](dataStructuresAlgorithms/insertionSort.md)
* [Big O notation](dataStructuresAlgorithms/bigONotation.md)
* [Difference stack and queue](dataStructuresAlgorithms/stackQueue.md)
* [Singly-Linked list](dataStructuresAlgorithms/singlyLinkedList.md)
* [Doubly-linked list](dataStructuresAlgorithms/doublyLinkedList.md)
* [Memoization](dataStructuresAlgorithms/memoization.md)
* [Depth-First Search](dataStructuresAlgorithms/dfs.md)
* [Breadth-first search](dataStructureAlgorithms/bfs.md)
* [Hash tables](dataStructureAlgorithms/hashTables.md)
* [Different types of tree traversals](dataStructureAlgorithms/treeTraversals.md)
* [Quick sort](dataStructureAlgorithms/quickSort.md)
* [Merge sort](dataStructureAlgorithms/mergeSort.md)

# Electronics
* [Current](electronics/current.md)

# Front-End
* [Graceful degradation vs Progressive Enhancement](frontEnd/gracefulDegradationVsProgressiveEnhancement.md)
* [Flash of Unstyled Content (FOUC)](frontEnd/FOUC.md)
* [Console.time()](frontEnd/consoleTime.md)
* [Performance tips](frontEnd/performanceTips.md)
* [Critical Rendering Path](frontEnd/CriticalRenderingPath.md)
* [Cross-Site Scripting](frontEnd/CrossSiteScripting.md)
* [Cross-Site Request Forgery](frontEnd/CrossSiteRequestForgery.md)
* [Secure web app with HTTP headers](frontEnd/secureWebAppHTTPHeaders.md)

# Git

* [Git pull rebase](git/rebase.md)
* [How to fix most recent commit](git/amend.md)
* [How to untrack node_modules folder when already commited to Github](git/untrack_node_modules.md)
* [How to find which commit introduced a bug](git/git_bisect.md)

# HTML5

* [Web Workers](html/webWorkers.md)
* [What is a polyfill](html/polyfill.md)
* [Preload](html/preload.md)
* [Accessibility labels](html/accessibilityLabels.md)

# Java

* [void](java/void.md)

# JavaScript

* [JavaScript security with Obfuscators](javascript/obfuscators.md)
* [Array destructuring](javascriot/destructuring.md)
* [Different types of functions](javascript/typesFunctions.md)
* [Event Delegation](javascript/eventDelegation.md)
* [AMD - Asynchronous Module Definition](javascript/amd.md)
* [Hoisting](javascript/hoisting.md)
* [Coercion](javascript/coercion.md)
* [var vs. let](javascript/varVsLet.md)
* [IIFE](javascript/iife.md)
* [Transpiling](javascript/transpiling.md)
* [Universal rendering](javascript/universalRendering.md)
* [this](javascript/this.md)
* [Difference null / undefined / undeclared](javascript/differenceNullUndefinedUndeclared.md)
* [JavaScript Event Loop](javascript/eventLoop.md)
* [Objects](javascript/objects.md)
* [Tree Shaking](javascript/treeShaking.md)
* [Implicit shadowing](javascript/implicitShadowing.md)
* [Class - Prototypal inheritance](javascript/class.md)
* [Delegation](javascript/delegation.md)
* [The JavaScript engine](javascript/engine.md)
* [The Web Storage API](javascript/webStorageApi.md)

### Node

* [Npm link](javascript/node/npmLink.md)
* [Install npm packages offline](javascript/node/installNpmPackagesOffline.md)

### React

* [Mixins](javascript/react/mixins.md)

### Design patterns

* [Constructor Pattern](javascript/design_patterns/constructorPattern.md)
* [Module pattern](javascript/design_patterns/modulePattern.md)


# Machine Learning

* [Glossary](machine_learning/glossary.md)
* [Bayes rule](machine_learning/bayesRule.md)
* [Naive Bayes](machine_learning/naiveBayes.md)
* [SVM](machine_learning/svm.md)
* [Decision tree](machine_learning/decisionTree.md)
* [Classification and Regression](machine_learning/classificationRegression.md)
* [Supervised vs Unsupervised](machine_learning/supervisedVsUnsupervised.md)

# Processing

* [Formula to map out image pixels from two dimensional array to one dimensional array with the raw depth data of the Kinect](processing/rawDepthPixels.md)
* [Using the map function](processing/mapFunction.md)
* [Vectors and forces](processing/vectorsAndForces.md)
* [Save animations as video](processing/saveVideo.md)

# Random
* [Save a video with transparent background to use it in AR in Unity](random/videoTransparentBackground.md)
* [What happens when you enter a URL in the browser and press 'enter'](random/urlBrowser.md)
* [How does DNS work](random/dns.md)

# RaspberryPi

* [Basic setup](raspberryPi/basicSetup.md)
* [SSH](raspberryPi/ssh.md)

---

# License

 © 2016 - Charlie Gerard

 This repository is licensed under the MIT license. See LICENSE for details.
