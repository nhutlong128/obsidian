- [[Redshift AUTO distribution]] assigns an optimal distribution style based on the size of the table data
- [[Redshift EVEN distribution]] is appropriate when a table doesn't participate in joins. It's also appropriate when there isn't a clear choice between KEY distribution and ALL distribution.
- [[Redshift KEY distribition]] The rows are distributed according to the values in one column.
- [[Redshift ALL distribution]] A copy of the entire table is distributed to every node.