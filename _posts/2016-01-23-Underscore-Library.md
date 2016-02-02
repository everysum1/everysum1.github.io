---
layout: post
title: Underscore Library
---

The Underscore Library has a lot of shorthand methods available for commonly used functions in Javascript so you don't have to write them out every time.


We will start with some of the basics that are used to build other more complex methods in the library.  Each is the cornerstone of the Underscore Library, performing the work of applying a specified function on each of the values in a collection.  Note that each does NOT return anything, its results are purely side effects. Each runs the quintessential loop through an object and is similar to the built in native Javascript method called .forEach but that only works on arrays.  The _.each method of the _ library works on both arrays and objects.  Remember that we must use different loops for iterating over objects and arrays.  We also have to check that the object being passed in to our _.each function is an array before we iterate over it as such.  

Its important to note that in the world of Javascript, arrays are objects but objects are not necessarily arrays.  Being an Object-Oriented language, nearly everything is an Object.  Yes, you read that right.  There are array objects, function objects, even string objects if you want to get technical about it.  Most of the time you don't really think about it, but keep it in mind when you're working through this method:  

		function each(collection, callback) {
			if (Array.isArray(collection)) {
				for (var i = 0; i < collection.length; i++) {
					callback(collection[i], i, collection)
				}
			} else if (collection.constructor === Object) {
				for (key in collection) {
					callback(collection[key], key, collection)
				}
			}
		}

So we used Array.isArray to check if the collection being passed in is an array object and not just a regular object object.  If it is, we use a for loop to iterate over it and apply the callback function that was passed in as an argument earlier.  We also have access to the index or key of the property as well as the whole collection, which can come in handy if we want to perform the work of a function on each of the values in a collection, but then we need to use the value of each property's index rather the value that place holds in the collection.  

Looping over an object similarly, we use a for in loop.  Almost identically as in arrays, we also have access to the key and collection as well as the value. 