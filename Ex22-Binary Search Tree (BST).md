# Ex22 Searching for a Book ID in a Binary Search Tree (BST)
## DATE: 05/09/2026
## AIM:
To design and implement java program that constructs a Binary Search Tree (BST) using given Book IDs and checks whether a specific Book ID exists in the BST.
## Algorithm

1. Start the program.
   
2. Create a Node class with integer data, and left and right child references.
   
3. Create an insert() method to insert Book IDs into the BST:

   If the tree is empty, insert the new node as the root.

   Otherwise, traverse left or right depending on whether the value is smaller or larger.

4. Create a search() method to find a specified Book ID:

   If the node is null, return false.

   If the key matches, return true.

   Recursively search left or right according to BST rules.

5. Read Book IDs from the user and insert them into the BST.

6. Input a Book ID to search in the tree.

7. Display whether the Book ID exists or not.

8. Stop the program.

## Program:
```
/*
Program to constructs a Binary Search Tree (BST) using given Book IDs 
Developed by: VINOTHKUMAR R
RegisterNumber:  212224040361
*/


import java.util.*;

public class BookIDSearch {
    static class Node {
        int data;
        Node left, right;
        Node(int data) {
            this.data = data;
        }
    }

    public static Node insert(Node root, int key) {
        if (root == null) return new Node(key);
        if (key < root.data) root.left = insert(root.left, key);
        else root.right = insert(root.right, key);
        return root;
    }

    public static boolean search(Node root, int key) {
        if (root == null) return false;
        if (root.data == key) return true;
        if (key < root.data) return search(root.left, key);
        else return search(root.right, key);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Node root = null;
        for (int i = 0; i < n; i++) {
            root = insert(root, sc.nextInt());
        }
        int q = sc.nextInt();
        while (q-- > 0) {
            int key = sc.nextInt();
            System.out.println(search(root, key) ? "Found" : "Not Found");
        }
    }
}

```

## Output:

<img width="426" height="185" alt="514839099-2f3cb628-3246-4a10-88bf-bbce3361bed2" src="https://github.com/user-attachments/assets/9ddd8b80-e8f2-47b1-bee3-9089e4caad13" />


## Result:
The program has been successfully implemented and executed.
It constructs a Binary Search Tree from the given Book IDs and accurately determines whether a queried Book ID exists in the library system.
