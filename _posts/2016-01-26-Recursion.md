---
layout: post
title: Recursion
---

Although the topic of Recursion might be a little intimidating at first, a recursive function is simply a function that calls itself from inside its function body.  

Lets consider the following problem with powerOfTwo, a function that determines if a number passed to it is a power of 2 and if it is, returns true:

			function powerOfTwo(num)
			    if (num <= 0) {
			        return false
			    } else if (num === 1) {
			        return true
			    } else if (num > 1){
			        if (num % 2 == 0) {
			            if (num / 2 === 2) {
			                return true
			            } else {
			            	#else call powerOfTwo on the num divided by two
			           		powerOfTwo(num/2)
			        	}
			        } else {
			           return false
			        }
			    }
			};

In our algorithm for solving this problem 
      


