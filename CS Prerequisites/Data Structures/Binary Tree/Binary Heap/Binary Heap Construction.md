1. Starts from the last node (tail) and iterate to the next node until the root node:
- Check if the current node is leaf => ignore
- If the current node is not leaf => Do the [[Heapify]] at the current node
- Iterate to next node

2. The reason why [[Binary Heap Construction]] costs [[O(nlog(n))]] is:
- We have to go to each node => [[O(n)]]
- In each node, we have to do [[Heapify]] => [[O(log(n))]]