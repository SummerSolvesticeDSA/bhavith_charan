int removeDuplicates(int* nums, int numsSize) {
    if (numsSize == 0) return 0;
    int w = 1; 
    for (int r = 1; r < numsSize; r++) {
        if (nums[r] != nums[r - 1]) {
            nums[w] = nums[r];
            w++; 
        }
    }
    return w; 
}
