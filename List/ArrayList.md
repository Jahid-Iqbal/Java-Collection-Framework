# ArrayList

  >ArrayList is an implemented class of List Interface which is present in `java.util` package. ArrayList is created based on growable Array means the size of ArrayList need not to be defined.

  ```java
public class ArrayList<E> extends AbstractList<E>
        implements List<E>, RandomAccess, Cloneable, java.io.Serializable
  ```
**Constructors:** Initially ArrayList defines a List of capacity 10 by default. Capacity means 10 indexes are available to store values. But at that time size is 0. Size counts the number of stored values on that list.
```java
ArrayList arrayList= new ArrayList();	//No-Arg constructor Initial capacity is 10 but size is 0.
```
Capacity of ArrayList can be defined externally using constructor `ArrayList(int initialCapacity)`.
```java
ArrayList arrayList= new ArrayList(3); 
```
Using the constructor `ArrayList(Collection c)` the value of onr List can be copied to another.
```java
ArrayList arrayList= new ArrayList();

arrayList.add(10);
arrayList.add(20);
arrayList.add(30);
arrayList.add(40);

ArrayList arrayList2= new ArrayList(arrayList);

System.out.println(arrayList);	//[10, 20, 3040]
System.out.println(arrayList2);	//[10, 20, 3040]
```


**Properties:**  

* **Index Based DS:** ArrayList are index based DS. Means each element is inserted in immediate next index of the current index. This is not possible to leave an index empty and then insert an element in next index.

```java
arrayList.add(10);	//Index 0
arrayList.add(20);	//Index 1
arrayList.add(30);	//Index 2
arrayList.add(40);	//Index 3
arrayList.add(8,50);//Index 8. Runtime errorException in thread "main" java.lanIndexOutOfBoundsException: Index: 8, Size: 4
```
* **Resizable:** Unlike traditional arrays in Java, an ArrayList can dynamically resize itself to accommodate more elements. It automatically handles the memory allocation and resizing, allowing you to add or remove elements without worrying about the underlying array's size.
* **Ordered:** ArrayList maintains the order of elements in which they are inserted. The position of an element in the ArrayList can be determined by its index, which starts from 0 for the first element and goes up to size() - 1 for the last element.
* **Duplicates and Nulls:** ArrayList allows duplicate elements, meaning you can store multiple occurrences of the same value. It also permits storing null values.

```java
ArrayList arrayList= new ArrayList();	

arrayList.add(10);	
arrayList.add(10);	
arrayList.add(30);	
arrayList.add(null);	
arrayList.add(null);

System.out.println(arrayList);	//[10, 10, 30null, null]
```
* **Data Retrieving Order:** ArrayList follows the insertion order.
* **Generics:** ArrayList is a generic class, which means it can store elements of any type. When creating an ArrayList, you can specify the type of elements it will hold, such as ArrayList<Integer> for integers or ArrayList<String> for strings. This provides compile-time type safety and eliminates the need for explicit type casting.

```java
	ArrayList noType= new ArrayList();	//Type isnot mentioned. So values of any type can bestored
	noType.add(10);
	noType.add("Hello");
	
	ArrayList<Integer> typedList= newArrayList<Integer>();	//Type is defined
	typedList.add(10);
	typedList.add("Hello");	//Compile Error: The method ad(Integer) in the type ArrayList<Integer> is notapplicable for the arguments (String)
```
* **Methods:** ArrayList provides various methods to manipulate and access its elements. Some commonly used methods include add(), remove(), get(), set(), size(), contains(), indexOf(), and isEmpty(). These methods allow you to add elements, remove elements, retrieve elements, check if an element is present, find the index of an element, and perform other operations.
* **Performance:** ArrayList offers efficient performance for most operations. Random access and retrieval by index are fast, as they have constant time complexity O(1). However, inserting or removing elements at arbitrary positions may require shifting other elements, resulting in a time complexity of O(n), where n is the number of elements in the ArrayList.


  It's important to note that ArrayList is not synchronized means multiple thread can access at a time, which means it is not thread-safe. If you need to use an ArrayList in a multithreaded environment, you should consider using `java.util.concurrent.CopyOnWriteArrayList` or synchronize the access to the ArrayList manually.