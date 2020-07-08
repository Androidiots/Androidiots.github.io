---
layout: page
title: BST
---

K-DSA
A Data Structure and Algorithm Repo with all Samples and Code Written in Kotlin


## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Androidiots/Androidiots.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown

PreOrder Traversal

fun main() {

 val tree  = BinarySearchTree() 

    /* Let us create following BST 
          50 
       /     \ 
      30      70 
     /  \    /  \ 
   20   40  60   80 */
    tree.insert(50)
    tree.insert(30)
    tree.insert(20)
    tree.insert(40)
    tree.insert(70)
    tree.insert(60)
    tree.insert(80)
    
     tree.preOrder(); 
}

class BinaryTreeNode ( /* Node data structure for binary search tree */
    var key: Int,
    var left: BinaryTreeNode? = null,
    var right: BinaryTreeNode? = null
)

class BinarySearchTree {

    var rootNode : BinaryTreeNode ?= null
    
    // This method mainly calls insertRec()
    open fun insert(key: Int) {
        rootNode = insertRec(rootNode, key)
    }

    /* A recursive function to insert a new key in BST */
    open fun insertRec( rootNode: BinaryTreeNode?, key: Int): BinaryTreeNode {
         
        var root: BinaryTreeNode? = rootNode
        /* If the tree is empty, return a new node */
        if (root == null) {
            root = BinaryTreeNode(key)
            return root
        }

        /* Otherwise, recur down the tree */if (key < root.key) root.left =
            insertRec(root.left, key) else if (key > root.key) root.right =
            insertRec(root.right, key)

        /* return the (unchanged) node pointer */
        return root
    }
    
    // This method mainly calls InorderRec() 
fun preOrder()  { 
   preOrderRec(rootNode); 
} 

// A utility function to do inorder traversal of BST 
fun preOrderRec( root : BinaryTreeNode?) { 
    if (root != null) { 
        System.out.println(root.key); 
        preOrderRec(root.left); 
        preOrderRec(root.right); 
    } 
} 
}

```


