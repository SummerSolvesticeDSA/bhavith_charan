int getSumOfSquares(int n) {
    int sum = 0;
    while (n > 0) {
        int digit = n % 10;
        sum += digit * digit;
        n /= 10;
    }
    return sum;
}

bool isHappy(int n) {
    if (n <= 0) return false;
    
    do {
        n = getSumOfSquares(n);
    } while (n != 1 && n != 4);
    
    return n == 1;
}
