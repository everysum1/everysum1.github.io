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
			               	powerOfTwo(num/2)
			            }
			        } else {
			           return false
			        }
			    }
			};

In our algorithm for solving this problem is simple.  We want to find if an integer given as an argument is a power of two, that is if 2 ^ nth power = argument.  We know that many numbers are divisible by two, but not this does not mean they are a power of two.  How can we know for sure we have a power of two? We must keep dividing by two until it equals two in order to know for sure.

So we have our base cases where we will return out of this infinite loop of calling the function within the function: Any argument that equals zero or less will automatically return false, and 1 will automatically return true.  Now we get to the recursive part of the function...

First we check if the argument passed in is evenly divisible by two, thereby eliminating all odd numbers from our list of possible power of twos.  Next we check if the number divided by 2 will equal 2.  If we have no such luck, we'll have to keep checking to see if we keep on dividing by two eventually we'll get 2 .  That sounds like a lot of work, and soooo repetitive! Why not let recursion do all the work?!

So we call the function on the argument number divided by two.  This will pass the number divided by two as the new argument to run on the second call of the function.  This loop will continue until we break out true at one of our base case scenarios (likely num / 2 === 2) or false in the case of an odd number or an integer less than 1.  And that's recursion in a nutshell!
      


