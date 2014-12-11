---
layout: post
category: "C++"
title:  "C++ Primer -- Ch 10. Associated Containers"
tags: [C++]
---

Critical Notes of **C++ PRIMER**, Chapter 10.  
  
+ ![images1](/assets/2014-12-08-C+++- Primer-ch10/general.png)  

# 10.1 the `pair` Type  
+ ![images2](/assets/2014-12-08-C+++- Primer-ch10/pair.png)  
+ ![images3](/assets/2014-12-08-C+++- Primer-ch10/initial.png)  
+ public member names: `first`, `second`  
	![images4](/assets/2014-12-08-C+++- Primer-ch10/pair_1.png)  
+ `make_pair()`: generate a new pair  
	![images5](/assets/2014-12-08-C+++- Primer-ch10/pair_2.png)  

# 10.3 map  
## 10.3.1 define a map  
+ ![images6](/assets/2014-12-08-C+++- Primer-ch10/map.png)  

## 10.3.2 types defined by map  
+ ![images7](/assets/2014-12-08-C+++- Primer-ch10/map_type.png)  
+ a map iterator: a pair  
	+ ![images8](/assets/2014-12-08-C+++- Primer-ch10/map_2.png)  

## 10.3.3 adding an element to map  
+ insert
+ subscribing  

## 10.3.4 subscribing a map  
+ ![images9](/assets/2014-12-08-C+++- Primer-ch10/subscribe.png)  
	+ if the key "Anna" already exists, change the mapped value to "1"  
	+ if the key "Anna" does not exist, creat/insert a map with key value "Anna" and mapped value "1"  
+ return mapped value with a subscript:  
	+ ![images9](/assets/2014-12-08-C+++- Primer-ch10/return_value.png)  

## 10.3.5 `map::insert()`  
+ ![images10](/assets/2014-12-08-C+++- Primer-ch10/insert.png)  
+ ![images11](/assets/2014-12-08-C+++- Primer-ch10/insert_1.png) or ![images12](/assets/2014-12-08-C+++- Primer-ch10/insert_2.png) or ![images13](/assets/2014-12-08-C+++- Primer-ch10/insert_3.png)  
+ return value: pair< map<>::iterator, bool >  
	![images14](/assets/2014-12-08-C+++- Primer-ch10/return_pair.png)  
	![images15](/assets/2014-12-08-C+++- Primer-ch10/return_pair_2.png)  
	
## 10.3.6 find and retrieve  
+ **find** & **count**  
+ ![images16](/assets/2014-12-08-C+++- Primer-ch10/find.png)  
+ ![images17](/assets/2014-12-08-C+++- Primer-ch10/find_1.png)  
+ ![images18](/assets/2014-12-08-C+++- Primer-ch10/find_2.png)  

## 10.3.7 erase an element  
+ ![images19](/assets/2014-12-08-C+++- Primer-ch10/map_erase.png)  

# 10.4 SET  
+ a collection of keys  
+ the keys of a set:  must be **unique** and may **not be changed**  

## 10.4.1 define and use  
+ ![images20](/assets/2014-12-08-C+++- Primer-ch10/set.png)  
+ add elements:  
	![images21](/assets/2014-12-08-C+++- Primer-ch10/set_insert.png)  
	![images22](/assets/2014-12-08-C+++- Primer-ch10/set_insert_2.png)  
+ find elements:
	![images23](/assets/2014-12-08-C+++- Primer-ch10/set_find.png)  
	![images24](/assets/2014-12-08-C+++- Primer-ch10/set_find_2.png)  

# 10.5 Multimap & Multiset  
+ multiple instances of a key  

## 10.5.1 Add/Remove elements  
+ insert always adds an element  
+ remove with a key value: remove all the elements with this key value  
+ remove with an iterator: remove only the reference of the iterator  
## 10.5.2 find elements  
+ elements with same key value are adjacent  
+ `find` & `count`  
	![images25](/assets/2014-12-08-C+++- Primer-ch10/multy_find.png)  
+ `lower_bound` & `upper_bound`  
	![images26](/assets/2014-12-08-C+++- Primer-ch10/bound.png)  
	![images27](/assets/2014-12-08-C+++- Primer-ch10/bound_code.png)  
+ `equal_range`  
	![images28](/assets/2014-12-08-C+++- Primer-ch10/equal_range.png)  
	






# practise question:  
+ 10.18,19,10.28  