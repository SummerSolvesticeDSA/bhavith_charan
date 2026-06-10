class Solution {
  public:
    bool armstrongNumber(int n) {
    int a=0;
    int num=n;
    while(n>0){
        int d=n%10;
        a=a+(d*d*d);
         n=n/10;

    }
    return (a==num);
}

};
