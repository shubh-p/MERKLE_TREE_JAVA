CSE-1007 JAVA PROGRAMMING
THEORY DA 
MERKLE TREE
INTRODUCTION
Merkle tree also known as hash tree is a data structure used for data verification and synchronization. 
It is a tree data structure where each non-leaf node is a hash of it’s child nodes. All the leaf nodes are at the same depth and are as far left as possible. 
It maintains data integrity and uses hash functions for this purpose.
Hash Functions: 
So before understanding how Merkle trees work, we need to understand how hash functions work. 
A hash function maps an input to a fixed output and this output is called hash. 
The output is unique for every input and this enables fingerprinting of data. 
So, huge amounts of data can be easily identified through their hash.
ARCHITECTURE
 
 This is a binary merkel tree, the top hash is a hash of the entire tree. 
 
•	This structure of the tree allows efficient mapping of huge data and small changes made to the data can be easily identified.
•	If we want to know where data change has occurred then we can check if data is consistent with root hash and we will not have to traverse the whole structure but only a small part of the structure.
•	The root hash is used as the fingerprint for the entire data
Structure of the node of binary Merkle tree
It contains four variables:
•	It contains a key variable.
•	It contains value variable
•	It contains two links.



ALGORITHM
There are various operations that need to be implemented in a Merkle tree,namely
Algorithm of find function in Merkle tree
Step 1: We will take tree and key as parameters.
Step 2: If the tree is null then we will return null.
Step 3: If the tree->key is equal to the key we will return the tree.
Step 4: If the key is smaller than tree->key then we will return find(tree->left, key)
Step 5: else return find(tree->right, key)

Algorithm to add a node in Merkle tree.
Step 1: We will take key and value as parameters.
Step 2: Take the hash(key) and store it in a variable called index.
Step 3: store (struct node*) arr[index].head in a pointer called tree of datatype node.
Step 4: create a new node with its key as key and value as value and both links as null.
Step 5: If the tree is null then assign the new node to the head and increment the size by 1.
Step 6: If the tree is not null then we will check if the key is already present in the tree using the find function.
Step 7: If the key is already present in the tree then we will update the value.
Step 8: If it is not present in the tree then we will use the insert function to insert the element.
Algorithm of insert function.
Step 1: It will take tree and item pointers of node data type as parameters.
Step 2: If item->key is smaller than tree->key and tree->left is null then assign the item to tree->left.
Step 3: If item->key is smaller than tree->key and tree->left is not null then call insert function with tree->left and item as parameters.
Step 4: If item->key is greater than tree->key and tree->right is null then assign the item to tree->right.
Step 5: If item->key is greater than tree->key and tree->right is not null then call insert function with tree->right and item as parameters.


REFERENCES
https://www.pranaybathini.com/2021/05/merkle-tree.html
https://iq.opengenus.org/merkle-tree/#:~:text=Algorithm%20to%20add%20a%20node%20in%20Merkle%20tree.&text=Step%202%3A%20Take%20the%20hash,and%20both%20links%20as%20null.
https://www.geeksforgeeks.org/introduction-to-merkle-tree/
https://medium.com/@vinayprabhu19/merkel-tree-in-java-b45093c8c6bd
https://github.com/shubh-p/merkletree/tree/master/src




