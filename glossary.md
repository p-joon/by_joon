# Glossary
##### __[Asset Package](#)__
An asset pakcage is a self contained collection of scirpts, or artwork, or even full game source code, that you can add to a project, when starting from scratch.  


##### __[Components](#)__
additional empty game objects(scripts) that add additional functionality to a game object to make them work.  

##### __[Deferred Execution](https://blogs.msdn.microsoft.com/charlie/2007/12/10/linq-and-deferred-execution/)__  
- __[Draw Calls](#)__: a draw call represents a single draw from a texture to the display. Ideally, you want to have the least amount of draw calls possible.
- __[Game Object](#)__: a game object represents any entity inside of your scene (ex. the main camera). A game object not only allows us to visualize what's in the object itself, but it also includes the code we need to make it work.  

##### __[Heap Memory (Java)](https://www.journaldev.com/4098/java-heap-space-vs-stack-memory)__
Java Heap Space is used by java runtime to allocate memory to Objects and JRE classes. Unlike in a Java stack where memory allocation is done when your program is compiled, in a heap it is allocated as your program is run. Acccessing variables placed here is a bit slower compared to a stack's direct and fast access.  

Heap is linkened to a global memory pool. A method or function will use the heap for memory allocation if you need the data or variables to live longer than the method or function in question. The objects you find here are accessible to all the functions.

Garbage Collection runs on the heap memory to free the memory used by objects that doesn't have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.  

##### __[Old Generation](https://stackoverflow.com/questions/2129044/java-heap-terminology-young-old-and-permanent-generations)__
The Old Generation is used to store long surviving objects. Typically, a threshold is set for young generation object and when that age is met, the object gets moved to the old generation. Eventually the old generation neeeds to be collected. This event is called a _major garbage collection_.  
- Tenured Space: The pool containing objects that have existed for some time in the survivor space (objects which survived after garbage collection from Survivor Space).  

##### __[Parallax Scrolling](#)__
when the background moves slower than the foreground to give the sense of dpeth without actually using real 3D space.  

##### __[Permanent Generation/Metaspace](https://stackoverflow.com/questions/2129044/java-heap-terminology-young-old-and-permanent-generations)__  
The pool containing all the reflective data of the virtual machine itself, such as class and method objects. What with Java VMs that use class data sharing, this generation is divided into read-only and read-write areas.  
- __Java 8 Update: PermGen__ is replaced with __Metaspace__ which is very similar. Main difference is that Metaspace re-sizes dynamically i.e., it can expand at runtime. Metaspace has unlimited default maximum size. On the contrary, PermGen from Java 7 and earlier has the default size of 64MB (on 32-bit JVM) and 82MB (on 64-bit JVM).
- Whenever there is a need to resize PermGen/Metaspace, JVM will do it as it does with the standard heap. Resizing those spaces requires a full Garbage Collection, which is always an expensive operation. It can be usually observed during a startup when a lot of classes are being loaded. Especially if the application has dependencies on many external libraries. If there are a lot of full GCs during the startup, it’s usually because of that. If that case, increasing the initial size can boost the startup performance.

##### __[Scene](#)__
A scene represetns the curent state of your game. You can have multiple scenes that represent individual levels of a game. You can use scenes for a splash screen, or for game over screens, or you can put all of your game content into a single screen, and use coding to hide and show the elements that you need, based on the state of the game.
##### __[Sprite](#)__
A sprite represents any image that would be rendered in a scene.

##### __[Sprite Renderer](#)__
The Sprite Renderer allows you to display a texture which would represent the sprite in the scene.  

##### __[Stack Space (Java)](https://dzone.com/articles/stack-vs-heap-understanding-java-memory-allocation)__
Java Stack Space is used for execution of a thread. They contain method specific values that are short-lived and references to other objects in the heap that are getting referred from the method.  

Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and references to other objects in the method.  

As soon as the method ends, the block becomes unused and becomes available for the next method.  

##### __[String Constant Pool](https://www.journaldev.com/797/what-is-java-string-pool)__
While the String object is immutable, its reference variable is not. As applications grow, it's very common for string literals to occupy a large area of memory, which can even cause redundancy. In order to make Java more efficient, the JVM sets aside a special area of memory called "string constant pool".
##### __[Young Generation](https://stackoverflow.com/questions/2129044/java-heap-terminology-young-old-and-permanent-generations)__  
It is place where all new objects are allocated and aged. When the young generation fills up, this causes a minor garbage collection. It is divided into two spaces:  
- Eden Space: When object created using `new` keword memory allocated on this space.  
- Survivor Space: This is the pool which contains objects which have survived after java garbage collection from Eden space.  
