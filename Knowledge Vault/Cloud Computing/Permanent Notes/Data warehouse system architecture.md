- The core infrastructure component of an [[Redshift Data warehouse]] is a [[Redshift cluster]]
- [[Redshift Leader Node]] manages communications with client programs and all communication with [[Redshift Compute Node]]
- [[Redshift Leader Node]] parse user command to execution plan and pass it to [[Redshift Compute Node]]
- Each [[Redshift Compute Node]] has its own dedicated CPU, memory, and attached disk storage
- A [[Redshift Compute Node]] is partitioned into [[Redshift Node Slices]] . Each slice is allocated a portion of the node's memory and disk space.
- [[Redshift User Data]] is stored on [[Redshift Compute Node]]
![[Pasted image 20210717143350.png]]