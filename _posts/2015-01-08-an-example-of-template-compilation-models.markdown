---
layout: post
category: "C++"
title:  "an example of template compilation models"
tags: [C++]
---

Let's use an case to study and verify the C++ template compilation models

# 1. Basic theory  

Let's review some basic knowledge first.  

+ compiler does not generate code immediately when it sees a template definition   
+ The compiler produces type-specific instances of the template only when it sees a use of the template( a function template is called / an object of a class template is defined)  
+ Non-template function/class:  
	+ compiler only needs to see the declaration of function/class when the function is called or the class is instantiated  
	+ so normally functions/class interfaces(class functions) are declared in header files, and defined in cpp files  
+ template function/class:  
	+ To generate an instantiation, the compiler needs the source code that defines the template  
	+ the compiler needs the template function/class definition (usually in cpp files) when it sees a called or an intance definition of the function/class.  
+ conclusion or template function/class -- we have 3 ways to define:  
	+ define template function/class interfaces in header files, not in cpp files  
	+ **Inclusion Compilation Model**: define template function/class interfaces in cpp files, then include the cpp files in header files  
	+ **Separate Compilation Model**: use ` export `  

# 2. an example of 3 ways  

Let's use a template to write a simple stack.  

+ 1st method: define in the header file.  
	+ tstack.h:  
	![images5](/assets/2015-01-08-an-example-of-template-compilation-models/head2.png)  
  
+ 2nd method: **Inclusion Compilation Model**  
	+ tstack.h:  
	![images1](/assets/2015-01-08-an-example-of-template-compilation-models/head1.png)  
	+ tstack.cpp:  
	![images2](/assets/2015-01-08-an-example-of-template-compilation-models/cpp.png)  
	+ main.cpp
	![images4](/assets/2015-01-08-an-example-of-template-compilation-models/main.png)  
	+ Makefile:  
	![images3](/assets/2015-01-08-an-example-of-template-compilation-models/makefile.png)  
	+ 2 critical points are highlighted in the above
		+ the head file includes the source file, but the source file does not include the head file, because it will be compiled to be an object file before linked(thanks to the Makefile)
		+ in the Makefile, should not make the source file into an object, because it should would be read and compiled to a specific template object when the class is instantiated 
+ 3rd method: **Separate Compilation Model**  
	+ theoretically we can use export in the source file to tell the compiler to remember a given template definition
	+ but I never succeed using this method. Perhaps because of the compiler version or parameter I use. If you have a practise, please do teach me :)

# 3. code address  

<https://github.com/ttxgz/cpp_practise/tree/template>