##Background
I work at Andela, a firm that specializes in training African talents into world-class developers regardless of prior computer knowledge or programming experience. After getting into Andela to be trained, I happened to be placed in the ruby stack where I will be expected to `possess the skill of a junior full­stack web developer that is comfortable using Ruby on Rails to
build real world applications.`

This is not a story of my professional life but I just thought it would be great for my readers to have a little backgound of what led to this post. Back to the point of departure, on my induction into the ruby tabernacle, I was delegated to build programs that would generally 'blow' a beginner's mind away. I was expected to implement a binary search algorithm, a Linked list data structure, binary search trees and write my own Enumerable module - Yes! You heard me correctly, Enumerable module.

It does not really get more challenging than this. I carried out these tasks and learnt a whole lot of tricks and things. However, a concept seemed to astound me the most while writing these scripts. It is this concept that led to this post. What was this revelation? It is simply the fact that we take so many ruby built in methods for granted. A type of these so-called taken for granted methods are the ones housed in the Enumerable module......
Having to write some of these methods myself proved trickier than I envisaged. You will see what I am talking about later on when you try to write some of them yourselves.
##Enumerables
Enumerables are methods that are provided by the ```Enumerable``` module which serves to iterate through a Ruby array or Hash (sometimes behind the scenes and palpably some other times). They are wildly used in the ruby community because they obviate the need to write unnecessary algorithms in your code. As a module, they have been mixed-in to the Array and Hash classes.
Below is a collection of enumerable methods and how you could write them youself supposing ruby was not charitable enough to provide them for us.
####my_each
The `each` method provides the fundamental platform from which all other enumerable methods implement their iterative processes. It effectively eliminates the need for ```for loops```. Let's get to work:
Given an array,

`arr = ["a", "b", "c", "d", "e"]`

How would you loop through every item in ```arr``` if ruby had not provided the each method? Let's say how would we go about getting this output on our screen

`aa--bb--cc--dd--ee`

 Before jumping off, please bear in mind that you cannot use the built in `each` method or a `for loop`. Please get to work! Continue reading only after giving up.
 
`def my_each
 	i = 0
 	while i <= arr.length - 1
 		yield self[i]
 		i += 1
 	end
 end`
 	