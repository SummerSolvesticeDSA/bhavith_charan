#include <stdlib.h>
void swap(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
int factorial(int n) {
    int res = 1;
    for (int i = 2; i <= n; i++) {
        res *= i;
    }
    return res;
}
void backtrack(int* nums, int numsSize, int start, int** result, int* returnSize) {
    if (start == numsSize) {
        result[*returnSize] = (int*)malloc(numsSize * sizeof(int));
        for (int i = 0; i < numsSize; i++) {
            result[*returnSize][i] = nums[i];
        }
        (*returnSize)++;
        return;
    }
    for (int i = start; i < numsSize; i++) {
        swap(&nums[start], &nums[i]);
        backtrack(nums, numsSize, start + 1, result, returnSize);
        swap(&nums[start], &nums[i]); 
    }
}

int** permute(int* nums, int numsSize, int* returnSize, int** returnColumnSizes) {
    int maxPermutations = factorial(numsSize);
    int** result = (int**)malloc(maxPermutations * sizeof(int*));
    *returnColumnSizes = (int*)malloc(maxPermutations * sizeof(int));
    for (int i = 0; i < maxPermutations; i++) {
        (*returnColumnSizes)[i] = numsSize;
    }
    *returnSize = 0;
    backtrack(nums, numsSize, 0, result, returnSize);
    
    return result;
}
