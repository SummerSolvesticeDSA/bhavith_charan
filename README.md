#include <string.h>
#include <stdlib.h>

char * minWindow(char * s, char * t) {
    int map[128] = {0};
    for (int i = 0; t[i] != '\0'; i++) {
        map[t[i]]++;
    }
    
    int left = 0;
    int right = 0;
    int minLeft = 0;
    int minLen = 1e9; 
    int required = strlen(t);
    
    while (s[right] != '\0') {
        if (map[s[right]] > 0) {
            required--;
        }
        map[s[right]]--;
        right++;
        while (required == 0) {
            if (right - left < minLen) {
                minLen = right - left;
                minLeft = left;
            }
            map[s[left]]++;
            if (map[s[left]] > 0) {
                required++;
            }
            left++;
        }
    }
    if (minLen == 1e9) {
        return ""; 
    }
    char *result = (char *)malloc((minLen + 1) * sizeof(char));
    strncpy(result, s + minLeft, minLen);
    result[minLen] = '\0';
    
    return result;
}
