#include <stdio.h>
#include <stdlib.h> 


long long* getCollatzSequence(long long n, int* returnSize) {
    int capacity = 100; 
    long long* sequence = (long long*)malloc(capacity * sizeof(long long));
    int count = 0;
    sequence[count] = n;
    count++;
    while (n != 1) {
        if (n % 2 == 0) {
            n = n / 2;
        } 
        else {
            n = 3 * n + 1;
        }
        if (count == capacity) {
            capacity *= 2; 
            sequence = (long long*)realloc(sequence, capacity * sizeof(long long));
        }
        sequence[count] = n;
        count++;
    }
    *returnSize = count;
    
    return sequence;
}

int main() {
    long long startNumber = 3;
    int sizeOfArray = 0;
    long long* result = getCollatzSequence(startNumber, &sizeOfArray);
    printf("Sequence for %lld: ", startNumber);
    for (int i = 0; i < sizeOfArray; i++) {
        printf("%lld ", result[i]);
    }
    printf("\n");
    free(result);
    
    return 0;
}
