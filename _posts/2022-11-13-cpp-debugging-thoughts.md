## Indeed a fake cs student I am. 

To make myself more similar to a cs student, I started to write some blog and study a bit about front-end. 

Recently I have spent about ~3-4 days on an algorithm assignment about implementing an AVL tree. The functions I needed to implemennt include insert, delete, and find kthMin in the AVL tree. 
Having done the coding within the first afternoon, bugs keep occuring. I struggled for the 2nd and 3rd day. 

The most annoying thing is probably that when you have a specific input, the output constantly changes. That was something I did not quite expect. 
In fact, I expect some pointer errors, but I didn't expect the output for a same input can change... This makes it clueless for me to find out where the bug is. 

Of course I divided my program into functions; nevertheless, I tested all of them but still could not find the error. 

# First attempt: 
I implemented a function `void showTreeStatus(TreeNode *T)` which can output the state of the tree. It was nice to use when I wanted to check whether the program is correct for some small-size input. 
However, the program runs well for the small-size inputs. Errors occur for large input size sample input. (I did not use GDB because I thought there was no problem for small input size; and for large input size, it was difficult to keep track of the addresses, isn't it? )

# Second attempt: 
I implemented helper functions to determine the state of the tree. 
 ```tsql
 bool isAVL (TreeNode *T)
 bool isBST (TreeNode *T)
 ```
And I called these functions for each operation. When the return value is false, immediately output the operation which caused the tree to be no longer balanced. 
Still, I did not find out the problem, because I have tested that insertion should be good; but the last step before error was always an insertion...

# Thrid attempt: 
In fact, I did notice there should be a pointer error of reading attributes of a NULL pointer, because sometimes the terminal appeared to be in a non-responsive state when running the program; but I still could not locate it. 
I modified the sample input, and removed all delete operations, and then I found out that the program worked smoothly! This immediately helps locate that the bug occurred in the `deleteNote` function. 

# Conclusion: 
Later I noticed that because I immediately used the code I wrote for deleting a node from a BST, the parent pointers for the child of the node to be deleted was not updated correspondingly. 
The strange phenomenon occurred because after
 ```tsql
 delete y;
 ```
is being run, you can still access to y! 
[This ](https://stackoverflow.com/questions/44182049/pointers-in-c-after-delete) passage and [this](https://blog.csdn.net/Echo_Hsu/article/details/105074860) explains how it worked. 
I think I'd better take this lesson to be more careful while dealing with pointers in C++ =.=