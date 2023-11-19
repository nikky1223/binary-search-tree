// binary-search-tree
//using c language

#include<stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node *left;
    struct node *right;
};
struct node* insert(struct node *root,int d){
    struct node*temp;
    temp=(struct node*)malloc(sizeof(struct node));
    temp->data=d;
    temp->left=temp->right=NULL;
    if (root==NULL)
        return temp;
    if(d<root->data)
        root->left=insert(root->left,d);
    else
        root->right=insert(root->right,d);
    return root;
}

void preorder(struct node*root){
    if(root!=NULL){
    printf("%d",root->data);
    preorder(root->left);
    preorder(root->right);
}
}
void main(){
    int d;
    struct node *root=NULL;
    while(1){
        printf("give the value of the n");
        scanf("%d",&d);
        switch(d)
        {
            case 1: int d;
                    printf("give the data");
                    scanf("%d",&d);
                    root=insert(root,d);
                   break;
            case 2:preorder(root);
                   break;
            case 3:inorder(root);
                   break;
            case 4:postorder(root);
                   break;
            default:exit(0);
        }
    }
}
