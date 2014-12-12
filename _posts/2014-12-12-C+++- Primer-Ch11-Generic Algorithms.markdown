---
layout: post
category: "C++"
title:  "C++ Primer -- Ch.11 Generic Algorithms"
tags: [C++]
---

Critical Notes of **C++ PRIMER**, Chapter 11.  

+ Iterators Bind Algorithms to Containers  
+ Algorithms Never Execute Container Operations  

# 11.2 A First Look  
## 11.2.1 Read-Only Algorithms  
+ `accumulate()`  
	+ ![images1](/assets/2014-12-12-C++-Primer-ch11/accumulate_1.png)  
	+ ![images2](/assets/2014-12-12-C++-Primer-ch11/accumulate_2.png)  
+ `find_first_of()`  
	+ ![images3](/assets/2014-12-12-C++-Primer-ch11/find.png)  
## 11.2.2  Algorithms that Write Container Elements  
+ `fill()`  
	+ ![images4](/assets/2014-12-12-C++-Primer-ch11/fill.png)  
+ Algorithms **Do Not** Check Write Operations  
	+ ![images5](/assets/2014-12-12-C++-Primer-ch11/fill_2.png)  
+ `back_inserter`  
	+ ![images6](/assets/2014-12-12-C++-Primer-ch11/back_inserter.png)  
+ `sort`, `stable_sort`, `count_if`  
	+ ![images7](/assets/2014-12-12-C++-Primer-ch11/code.png)  

# 11.3 Revisiting Iterators  
+ **insert iterators:**  insert elements to the container  
+ **iostream iterators:** bound to input or output streams  
+ **reverse iterators:** move backward, retuned by the rbegin and rend functions  
  
## 11.3.1. Insert Iterators  
+ back_inserter: uses push_back  
+ front_inserter: uses push_front  
+ inserter: uses insert. takes a second argument( an iterator ) indicating the position ahead of which insertion should begin  
	+ ![image8](/assets/2014-12-12-C++-Primer-ch11/insert_2.png)  

## 11.3.2. iostream Iterators  
+ ![image9](/assets/2014-12-12-C++-Primer-ch11/io_iter_1.png)  
+ ![image10](/assets/2014-12-12-C++-Primer-ch11/io_iter_2.png)  

# **TBD**
