# Activity 8

1. Will demonstrate in Video.

2 [log base 2 1000] = 10



3.
int main() {  
    int arr[] = {1, 5, 9, 2, 4, 10, 6, 3, 8};  
    int n = sizeof(arr) / sizeof(arr[0]);  
    Node* root = nullptr;  
      
    // Insertion operation  
    for (int i = 0; i < n; i++) {  
        root = insert(root, arr[i]);  
    }  
      
    // Find and print the maximum value  
    cout << "Maximum value in the BST: " << findMax(root) << endl;  
      
    return 0;  
}  

4.



#include <iostream>  
using namespace std;  
  
struct Node {  
    int key;  
    Node* left;  
    Node* right;  
      
    Node(int val) : key(val), left(nullptr), right(nullptr) {}  
};  
  
Node* insert(Node* root, int key) {  
    if (root == nullptr) {  
        return new Node(key);  
    }  
    if (key < root->key) {  
        root->left = insert(root->left, key);  
    } else { // key >= root->key  
        root->right = insert(root->right, key);  
    }  
    return root;  
}  
  
void inorder(Node* root) {  
    if (root != nullptr) {  
        inorder(root->left);  
        cout << root->key << " ";  
        inorder(root->right);  
    }  
}  
  
int main() {  
    int arr[] = {1, 5, 9, 2, 4, 10, 6, 3, 8};  
    int n = sizeof(arr) / sizeof(arr[0]);  
    Node* root = nullptr;  
      
    // Insertion operation  
    for (int i = 0; i < n; i++) {  
        root = insert(root, arr[i]);  
    }  
      
    // Optional: Print inorder traversal of BST  
    cout << \"Inorder traversal of BST: \" << endl;  
    inorder(root);  
    cout << endl;  
      
    return 0;  
}  
