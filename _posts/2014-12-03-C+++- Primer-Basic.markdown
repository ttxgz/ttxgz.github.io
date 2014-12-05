---
layout: post
category: "Android"
title:  "C++ Primer -- Basic"
tags: [android]
---

I am reading _*the C++ Primer*_, and will mark down notes about critical things that easily confuse us.

# 1. Getting Started.
## 1.2 A First Look at Input/Output
### 1.2.1 Standard Input and Output Objects

+ The library defines four IO object: **cin, cout, clog, cerr**
+ std:endl \-\- manipulator, write a newline to the **output + flush** the buffer
+ 如果不加，则发生错误时可能会导致错误推断崩溃位置  

## 1.3 About Comment  
- Comment pairs ( /\* \.\.\. \*/ ) do not nest. The following is **wrong**:    
```
	/* ..... /* .... */    ... */
```
	
## 1.4 control structures
### 1.4.4 Reading an Unknow number of input  

``	int cnt(0);  ``  
``	cout << "Test 6:  Read an unkonw number of string: please input some words" << endl;  ``   
``	while(cin >> s1)// will only break when enter ctrl+z>  ``  
``	{  ``  
``		cout << s1 << endl; ``  
``		cnt++;  ``  
``	}  ``  
``	cout << "You have input " << cnt << " words" << endl;  ``   

# 2. Variables and Basic Types
## 2.1 Primitive Buit-in Type
![images1](/assets/2014-12-03-C+++- Primer-Basic/built_in_type.png)
+ float: 32bit  
+ double: 64 bit  
+ long double: 3 or 4 x 32 bit  

## 2.8 class
+ class： the default member type is private  
+ struct:  the default member type is public  

## 2.9 head file  
### 2.9.1  
  head file should not contain definitions of variables or functions, except for the 3 following cases:  
   1. 在编译时就已经知道到值的classes  
   2. 在编译时就已经知道到值的 const  
   3. inline 函数  
   
### 2.9.2  
+ header guard  

# 3. Library Types  
## 3.2 Library string Type  
### 3.2.1 definition and initialing of string  
![images2](/assets/2014-12-03-C+++- Primer-Basic/string.png)  

### 3.2.3 Operations of string  
![images3](/assets/2014-12-03-C+++- Primer-Basic/string_op.png) 

## 3.3 VECTOR  
+ code address: <https://github.com/ttxgz/cpp_practise/tree/vector_iterator>)  

### 3.3.1 initialization  
+ A vector is a class template
+ grow --> let it grow rather than initial with a set number when initialising

###3.3.2 Operations on Vector  
![images4](/assets/2014-12-03-C+++- Primer-Basic/vector_op.png)  

+ a correct code:  
![images5](/assets/2014-12-03-C+++- Primer-Basic/vector_1.png)   

+ subsribing **does not add** elements, a piece of **wrong** code is:  
![images6](/assets/2014-12-03-C+++- Primer-Basic/vector_2.png)  

+ subsripts can be used to fetch existing elements. The correct code should be:  
![images7](/assets/2014-12-03-C+++- Primer-Basic/vector_3.png)  

## 3.4 iterator  
### 3.4.1 definition and initialise  
+ every container type has its own defined iterator. For example:
	vector<int>::iterator iter;  
+ vector.begin() and vector.end():  
	- when the vector is empty, then vector.end() and vector.begin() are the same  
	- vector.end() always refers to an un-existing element that follows the last element  

### 3.4.2 Operations on iterator  
+ dereference operator: points to the element. Eg:  
`	*iter = 4;  `  
+ increment. Eg:  
`	iter++;  `  
+ ==, !=: If two iterator refers to a same element, then they equal.  

### 3.4.3 an example:  
![images8](/assets/2014-12-03-C+++- Primer-Basic/vector_4.png)  

### 3.4.4 const_iterator VS const iterator  
+ const_iterator: can not change the value it refers to, but can change the iterator itself.  
+ const iterator (seldom use): can change the value it refers to, but can cot change the iterator itself. Eg:   
![images9](/assets/2014-12-03-C+++- Primer-Basic/vector_5.png)  
![images10](/assets/2014-12-03-C+++- Primer-Basic/vector_6.png)  

# 4. ARRAYS & POINTERS  
## 4.1 ARRAYS  
### 4.1.1 initialise  
![images11](/assets/2014-12-03-C+++- Primer-Basic/array_init.png)  
+ arrays VS vectors:  the **length** of arrays are **fixed** when defined. No push_back(), no size().

## 4.2 POINTERS  
+ void pointer: can point to anything   
![images12](/assets/2014-12-03-C+++- Primer-Basic/void_pointer.png)  

### 4.2.5 const pointer  
+ C-style character string: character string with 'null' at the end  
![images13](/assets/2014-12-03-C+++- Primer-Basic/c_string.png)  

+ operations on it:  
![images14](/assets/2014-12-03-C+++- Primer-Basic/c_string_op.png)   

+ **Dos and Don'ts**  
	+ Never Forget the **null-terminator**  
	+ Ensure **enough size** of a destination string  
	+ Use **strn** functions (Eg. strncat/strncpy is better than strcat/strcpy)  
	+ it is better to use string rather than use c-style character string ( char[] )  
	
### 4.3.1 Dynamically Allocating Arrays  
+ allocate with initial value:  
![images15](/assets/2014-12-03-C+++- Primer-Basic/alloc.png)  

+ to delete:  
`delete pi;`  
`delete ps;`  

+ to allocate array:  
` int *pia = new int[10]; // array of 10 uninitialized ints `  

+ to delete allocated array:  
` delete [] pia; `  


# 6. Statements  
+ Code Address: <https://github.com/ttxgz/cpp_practise/tree/exception_try_c>  

## 6.13 try blocks and exception handling  
### 6.13.1 A throw expression  
`	if(tmp > 10)  `  
`	{  `	
`		cout << " I will throw a runtime_error exception now!" << endl;  ``  
`		throw runtime_error("This number is larger than 10!"); //After throwing the err, will be caught immediately, so will not execute the push_back!`  
`	}`  
`	if(tmp < 5)`  
`	{`  
`		cout << " I will throw an int exception now!" << endl;`  
`		throw 20;//After throwing the err, will be caught immediately, so will not execute the push_back!`  
`	} `  


### 6.13.2 A try block  
`	try `  
`	{`  
`		int tmp;`  
`		cin >> tmp;`  
`		if(tmp > 10)`  
`		{`  
`			cout << " I will throw a runtime_error exception now!" << endl;`  
`			throw runtime_error("This number is larger than 10!"); //After throwing the err, will be caught immediately, so will not execute the push_back!`  
`		}`  
`		if(tmp < 5)`  
`		{`  
`			cout << " I will throw an int exception now!" << endl;`  
`			throw 20;//After throwing the err, will be caught immediately, so will not execute the push_back!`  
`		}`  
`		numbers.push_back(tmp);`  
`		cnt ++;`  
`	}catch(runtime_error err)`  
`	{`  
`		cout << "Catch a runtime_error exception, err.what() is: " << err.what() << endl;`  
`		cout << endl;`  `  
`	}catch(int e)`  `  
`	{`  
`		cout << "Catch an int exception, the err value is: " << e << endl;`  
`		cout << endl;`  
`	}catch(...)`  
`	{`  
`		cout << "Catch an unknown exception! " << endl;//Catche any exception rather than the runtime_error and the int error `  
`	}   `  

### 6.13.3 Standard Exceptions  
[images16](/assets/2014-12-03-C+++- Primer-Basic/standard_exceptions.png)  

# 7. Functions   
### 7.2.3 Vector as parameter   
It is better to use iterator than the vector for the efficiency of copying. Eg:   
![images16](/assets/2014-12-03-C+++- Primer-Basic/iterator.png)     

# code address
<https://github.com/ttxgz/activity_quiz/>