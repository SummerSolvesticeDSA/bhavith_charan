#include<string.h>
#include<ctype.h>
bool isPalindrome(char* s) {
    int a=strlen(s);
    int count=0;
    char si[a];
    for(int i=0;i<a;i++){
        if(isalnum((unsigned char)s[i])){
            s[i]=tolower((unsigned char)s[i]);
            si[count++]=s[i];
        }

    }
    for(int j=0;j<count/2;j++){
        if(si[j]!=si[count-j-1]){
            return false;
        }
    }
    return true;

    
}
