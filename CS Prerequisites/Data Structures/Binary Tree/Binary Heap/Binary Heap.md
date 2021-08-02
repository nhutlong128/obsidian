### Metadata

-  Type: #permanent #binarytree 
    Date written: #2021-06-21
    Source:  https://www.geeksforgeeks.org/heap-data-structure/
    Status: #wip 
    Keywords:  #datastructures #binaryheap
	Related: #binarytree
	
### Notes
- [[Binary Heap]] is a [[Complete Binary Tree]] with Heap properties.
- In [[Min Heap]], the key of parent node will always smaller than keys of its children nodes => The root key is minimum.![[Pasted image 20210621173007.png]]
- [[Max Heap]] is very similar to [[Min Heap]], the key of parent node will bigger than keys of its children nodes => The root key is maximum.![[Pasted image 20210621175107.png]]
- The main operation of [[Binary Heap]] is [[Heapify]]
- [[Binary Heap Construction]] costs [[O(nlog(n))]]
- [[Binary Heap Insert]] costs [[O(log(n))]]
- [[Binary Heap Decrease Node Key]] costs [[O(log(n))]]
- [[Binary Heap Head Pop]] costs [[O(log(n))]]
- [[Binary Heap Remove]] costs [[O(2log(n))]]