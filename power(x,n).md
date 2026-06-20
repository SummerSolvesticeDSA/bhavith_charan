double myPow(double x, int n) {
    long long power = n; 
    if (power < 0) {
        x = 1.0 / x;
        power = -power;
    }
    
    double result = 1.0;
    while (power > 0) {
        if (power & 1) { 
            result = result * x;
        }
        x = x * x;       
        power >>= 1;     
    }
    
    return result;
}
