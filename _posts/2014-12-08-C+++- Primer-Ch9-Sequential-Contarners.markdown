---
layout: post
category: "C++"
title:  "C++ Primer -- Ch 9. Sequential Containers"
tags: [C++]
---

Critical Notes of **C++ PRIMER**, Chapter 9.  

+ each of 3 containers is a class template  
+ 3 sequential containers and adaptors  
	![images1](/assets/2014-12-08-C+++- Primer-ch9/types_adaptors.png)  

# 9.1 Defining
## 9.1.1 create and initialise
+ Constructor  
	![images2](/assets/2014-12-08-C+++- Primer-ch9/constructors.png)  

+ Copy one container to another: the **container type** and **element type** must be the same
	![images3](/assets/2014-12-08-C+++- Primer-ch9/copy_containor.png)  
	
+ Copy containors with different types: use iterator:  
	![images4](/assets/2014-12-08-C+++- Primer-ch9/copy_iterator.png)  
	
## 9.1.2 about elements
+ support assignment  
+ can be copied  
+ references can not be elements  
+ vector can be element itself (with space between two \"\<\" or \"\<\"). Eg.  
	![images5](/assets/2014-12-08-C+++- Primer-ch9/containor_of_containor.png)  
+ IO library types can not be element (not support copy and assignment)  
+ Suppose ` Foo ` is a class that does not define a default constructor but a constructor that takes an int argument  
	![images6](/assets/2014-12-08-C+++- Primer-ch9/initialise.png)  

# 9.2 Iterators  
+ ![images7](/assets/2014-12-08-C+++- Primer-ch9/iterators.png)   
+ only for **vector** and **dequeue**  
	+ ![images8](/assets/2014-12-08-C+++- Primer-ch9/iterators_2.png)  
	+ **correct** code  
		![images9](/assets/2014-12-08-C+++- Primer-ch9/correct.png)  
	+ **wrong** code ( list does **not** support <=, <, >=, >; it only supports pre/postfix increment/decrement and equality/inequality)  
+ iterator range
	+ [first, last) 
	+ They refer to elements of, or one-past-the-end of, the same container  
	+ If the iterators are not equal, then it must be possible to reach last by repeatedly incrementing first.   
		In other words, last must not precede first in the container  

# 9.3 Sequence Container Operations  
## 9.3.1 Container Typedefs  
+ ![images10](/assets/2014-12-08-C+++- Primer-ch9/typedef.png)  

## 9.3.2 begin & end
+ ![images11](/assets/2014-12-08-C+++- Primer-ch9/begin_end.png)  

## 9.3.3 adding elements
+ ![images12](/assets/2014-12-08-C+++- Primer-ch9/add.png)  

+ ![images13](/assets/2014-12-08-C+++- Primer-ch9/add_2.png)  

## 9.3.4 Relational Operators  
+ **==**:  same size +  all the elements are equal  
+ ** < , > **: If the containers have different sizes but every element of the shorter one is equal to the corresponding element of the longer one, then the shorter one is considered to be less than the other.  
+ If neither container is an initial subsequence of the other, then the comparison depends on comparing the first unequal elements  

## 9.3.6 Accessing Elements  
+ ![images14](/assets/2014-12-08-C+++- Primer-ch9/access.png)  

## 9.3.7 Eerasing Elements
+ ![images15](/assets/2014-12-08-C+++- Primer-ch9/erase.png)  

+ use " ` find ` "  
	![images16](/assets/2014-12-08-C+++- Primer-ch9/find_1.png) ![images17](/assets/2014-12-08-C+++- Primer-ch9/find_2.png)  

## 9.3.8 assignment and swap
+ ![images18](/assets/2014-12-08-C+++- Primer-ch9/assign.png)  

# 9.4 how a vector grows  
+ vector : elements are stored contiguously. Eeach element is adjacent to the previous element.  
+ list : linked list  
+ For most applications the best container to use is a **vector**  

## 9.4.1 **capacity** and **reserve**  
+ ![images19](/assets/2014-12-08-C+++- Primer-ch9/capacity.png)  
+ **reserve**: set the capacity of a vector
+ **resize** : delete elements or insert elememt at the end of a container to make decrease/increase the size. May of may not change the capacity  

# 9.5 choose a container  
+ features:
	+ **LIST**  
		+ noncontiguous memory  
		+ efficient to insert or erase an element at any point( does not move any other elements )  
		+ Random access, is **not** supported  
	+ **VECTOR**  
		+ contiguous memory: have to move some elements to insert/remove any element except at the back of a vector  
	+ **DEQUEUE**  
		+ adding or removing elements at both the head and the tail is a fast operation ( better than vector when insert/remove on the head)  
		+ add/remove in the middle is slow ( similar to vector )
		+ support fast random access of any element ( similar to list )  
	+ generally, VECTOR is the right one  
+ some rules:  
	![images20](/assets/2014-12-08-C+++- Primer-ch9/select.png)  

# 9.7 adaptors
+ general types:  
	![images20](/assets/2014-12-08-C+++- Primer-ch9/common.png)  
+ include associated head files: 
	![images21](/assets/2014-12-08-C+++- Primer-ch9/head.png)  

## 9.7.1 Adaptor  
+ ![images22](/assets/2014-12-08-C+++- Primer-ch9/stack.png)  

## 9.7.2 Queue & Priority Queue
+ ![images22](/assets/2014-12-08-C+++- Primer-ch9/queue.png)  

# practise question:  
+ 9.9, 9.12, 9.13, 9.26, 9.43  

  












# code address
<https://github.com/ttxgz/activity_quiz/>