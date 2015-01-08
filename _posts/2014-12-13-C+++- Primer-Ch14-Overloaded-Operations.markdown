---
layout: post
category: "C++"
title:  "C++ Primer -- Ch.14  Overloaded Operations and Conversions"
tags: [C++]
---

Critical Notes of **C++ PRIMER**, Chapter 14.  

# 14.1 definition  
+ ![images1](/assets/2014-12-15-C++-ch14/can_overloaded.png)  
+ ![images2](/assets/2014-12-15-C++-ch14/can_not_overloaded.png) 
+ has the same number of parameters (including the implicit this pointer for member functions)    
+ at least one operand of class or enumeration ( an operator for the built-in types may not be overloaded )  
+ Precedence and Associativity Are Fixed  
+ Overloaded functions that are members of a class:   
	+ have **one less** parameter than the number of operands  
	+ have an implicit **this** parameter that is bound to the **first** operand.  
+ usually, arithmetic and relational operators -> nonmember functions ; assignment operators -> members:
	+ ![images3](/assets/2014-12-15-C++-ch14/member.png)  
+ using it:  
	+ ![images4](/assets/2014-12-15-C++-ch14/using_1.png) or + ![images5](/assets/2014-12-15-C++-ch14/using_2.png)  
	+ ![images6](/assets/2014-12-15-C++-ch14/using_3.png)  

# 14.2  Input and Output Operators  
## 14.2.1  Overloading the Output Operator <<  
+ ![images7](/assets/2014-12-15-C++-ch14/stream.png)  
+ IO Operators Must Be Nonmember Functions 
	+ Or else the left-hand operand would have to be an object of our class type:  
	+ ![images8](/assets/2014-12-15-C++-ch14/error.png)  
	+ wrong because it is the opposite of the normal way we use output operators  

## 14.2.2. Overloading the Input Operator >>  
+ must deal with the possibility of errors and end-of-file  
+ usual way for wrong input: create a new, unnamed Obj using the default constructor  
	+ ![images9](/assets/2014-12-15-C++-ch14/err_input.png)  

# 14.3. Arithmetic and Relational Operators  
## 14.3.1. Equality Operators  
+ ![images10](/assets/2014-12-15-C++-ch14/equal.png)  

# 14.4. Assignment Operators  
+ ![images10](/assets/2014-12-15-C++-ch14/assign.png)  
+ Should Return a Reference to *this  

 
