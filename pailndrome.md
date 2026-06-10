bool isPalindrome(int x) {
    int a=x;
    long b=0;
    while(a>0){
        b=b*10+a%10;
        a=a/10;
    }
    if(b==x) return true;
    else return false;
}
