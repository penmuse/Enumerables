##Background
I work at Andela, a firm that specializes in training African talents into world-class developers regardless of prior computer knowledge or programming experience. I happened to be placed in the ruby stack where I will be expected to `possess the skill of a junior full­stack web developer that is comfortable using Ruby on Rails to build real world applications.`

This is not a story of a professional life but it would be great for my readers to get a hint of the motivation for this post. Back to the point of departure, on my induction into the ruby tabernacle, I was delegated to build programs that would generally 'blow' a beginner's mind away. I was expected to implement a binary search algorithm, a Linked list data structure, binary search trees and write my own Enumerable module - Yes! You heard me correctly, Enumerable module.

It does not really get more challenging than this. I carried out these tasks and inevitably learnt a whole lot of tricks and stuffs. However, a concept seemed to astound me the most while writing these scripts. It is this concept that led to this post. What was this revelation? It is simply the fact that we take so many ruby built in methods for granted. A type of these so-called taken for granted methods are the ones housed in the Enumerable module......
Having to write some of these methods myself proved trickier than I envisaged. You will see what I am talking about later on when you try to write some of them yourselves.
##Enumerables
Enumerables are methods that are provided by the ```Enumerable``` module which serves to iterate through a Ruby array or Hash (sometimes behind the scenes and palpably some other times). They are wildly used in the ruby community because they obviate the need to write unnecessary algorithms in your code. As an indispensible module, they have been mixed-in to the Array and Hash classes by default.
Below is the most fundamental enumerable method and how you could write it youself supposing ruby was not charitable enough to provide it for us.
####my_each
The `each` method provides the fundamental platform from which all other enumerable methods implement their iterative processes. It effectively eliminates the need for ```for loops```. Let's get to work:
Given an array,

`arr = ["a", "b", "c", "d", "e"]`

How would you loop through every item in ```arr``` if ruby had not provided the each method? Let's say how would we go about getting this output on our screen

`aa--bb--cc--dd--ee`

 Before jumping off, please bear in mind that you cannot use the built in `each` method or a `for loop`. Please get to work! Continue reading only after giving up or successfully completing the task.
 
 
 We would first write a module that will be mixed into the array class like:
 
```ruby
module Enumerable
	def my_each
	 	i = 0
	 	while i <= self.length - 1
	 		yield self[i]
	 		i += 1
	 	end
	 end
end
class Array
    include Enumerable
end
```
 The `yield` key\_word is just to make available our items to a block (we do remember that the each method takes a block. Don't we?).
 We could then write the logic with our own each method like this:
 
```ruby
arr.my_each do |letter|
	if arr.index(letter) == arr.length - 1
		print letter * 2
	else
		print letter * 2, "--"
	end
end
```

Quite straight forward, wasn't it. The iteration process here is quite evident. We shall consider a pair of methods in which the underlying iteration may not seem so evident. Before we do that however, we must understand the logic here is important as it co

 
 	
 	