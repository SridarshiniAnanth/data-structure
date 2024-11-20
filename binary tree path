/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
#define SIZE_BUFF 100

int size;
char** ret;

void binaryTreePaths_r(struct TreeNode* root, char* prefix) {
    if (root == NULL)
        return;
    char* p = prefix + strlen(prefix);
    sprintf(p, "%s%d", strlen(prefix) == 0 ? "" : "->", root->val);
    if (root->left == NULL && root->right == NULL) {
        ret[size] = calloc(strlen(prefix) + 1, sizeof(char));
        strcpy(ret[size], prefix);
        size++;
    } else {
        binaryTreePaths_r(root->left, prefix);
        binaryTreePaths_r(root->right, prefix);
    }
    *p = '\0';
}

char** binaryTreePaths(struct TreeNode* root, int* returnSize) {
    char buff[SIZE_BUFF] = {0};
    ret = calloc(SIZE_BUFF, sizeof(char*));
    size = 0;

    binaryTreePaths_r(root, buff);

    *returnSize = size;
    return ret;
}
