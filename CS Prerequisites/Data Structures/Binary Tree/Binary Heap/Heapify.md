For [[Min Heap]], at i_th node:
- Find the minimum min node of [i_th node, the left child node, the right child node]
- If the minimum min node is not i_th node => Swap the key of minimum min node <=> i_th node
- Keep doing [[Heapify]] at the  i_th node to the root node.

[[Half Heapify]]