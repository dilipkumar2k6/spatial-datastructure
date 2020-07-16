# Summary
- Search trees such as BSTs, AVL trees, splay trees, 2-3 Trees, B-trees, and tries are designed for searching on a one-dimensional key. 
- A typical example is an integer key, whose one-dimensional range can be visualized as a number line. 
- These various tree structures can be viewed as dividing this one-dimensional number line into pieces.
- Some databases require support for multiple keys. 
- In other words, records can be searched for using any one of several key fields, such as name or ID number. 
- Typically, each such key has its own one-dimensional index, and any given search query searches one of these independent indices as appropriate.
# Multi Dimensional keys
## Problem
- A multidimensional search key presents a rather different concept.
-  Imagine that we have a database of city records, where each city has a name and an xy coordinate. 
- A BST or splay tree provides good performance for searches on city name, which is a one-dimensional key. 
- Separate BSTs could be used to index the x and y coordinates.
- This would allow us to insert and delete cities, and locate them by name or by one coordinate. 
- However, search on one of the two coordinates is not a natural way to view search in a two-dimensional space.
## Concatenated key approach
- Another option is to combine the xy coordinates into a single key, say by concatenating the two coordinates, and index cities by the resulting key in a BST.
- That would allow search by coordinate, but would not allow for an efficient two-dimensional range query such as searching for all cities within a given distance of a specified point. 
- The problem is that the BST only works well for one-dimensional keys, while a coordinate is a two-dimensional key where neither dimension is more important than the other.
## Multidimensional range queries
- Multidimensional range queries are the defining feature of a spatial application.
- Because a coordinate gives a position in space, it is called a spatial attribute.
- To implement spatial applications efficiently requires the use of a spatial data structure. 
- Spatial data structures store data objects organized by position and are an important class of data structures used in geographic information systems, computer graphics, robotics, and many other fields.
## Spatial data structure
### kd Tree
- A number of spatial data structures are used for storing point data in two or more dimensions. 
- The `kd tree` is a natural extension of the `BST` to multiple dimensions. 
- It is a binary tree whose splitting decisions alternate among the key dimensions. 
- Like the `BST`, the `kd` tree uses `object-space decomposition`. 
### PR Quadtree
- The `PR quadtree` uses `key-space decomposition` and so is a form of `trie`. 
- It is a binary tree only for one-dimensional keys (in which case it is a trie with a binary alphabet).
- For d dimensions it has 2d branches.
- Thus, in two dimensions, the PR quadtree has four branches (hence the name "quadtree"), splitting space into four equal-sized quadrants at each branch. 
### Bin Tree
- Two other variations on these data structures are the bintree and the point quadtree. 
### Point Quadtree
- In two dimensions, these four structures cover all four combinations of object- versus key-space decomposition on the one hand, and multi-level binary versus 2d-way branching on the other. 

# Reference 
https://www.youtube.com/watch?v=uHronVrSSdw
https://www.youtube.com/watch?v=_NY_1tCOuis
https://www.youtube.com/watch?v=qH2-xwUz3tU
