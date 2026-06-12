#define MIN(a, b) ((a) < (b) ? (a) : (b))
#define MAX(a, b) ((a) > (b) ? (a) : (b))

int maxArea(int* height, int heightSize) {
    int left = 0;
    int right = heightSize - 1;
    int max_area = 0;
    while (left < right) {
        
        int current_height = MIN(height[left], height[right]);
        int width = right - left;
        int current_area = current_height * width;
        max_area = MAX(max_area, current_area);
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }

    return max_area;
}
