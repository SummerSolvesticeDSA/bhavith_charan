bool isPowerOfTwo(int n) {
   if(n<0){
    return false;
   }
    if(n==0){
        return false;
    }
    if(n==1){
        return true;
    }
    else if(n==2){
        return true;
    }
    if(n>2){
        if(n%2!=0){
            return false;
        }
        else if(n%2==0){
            while(n>0){
                n=n/2;
                if(n==1 || n==-1){
                    return true;
                }
                if(n%2!=0){
                    return false;
                }
            }
        }
    }
    return true;
}
    
