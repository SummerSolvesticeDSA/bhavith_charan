#include<string.h>
#include<stdio.h>
bool canConstruct(char* ransomNote, char* magazine) {
    int countchar[26]={0};
    int a=strlen(ransomNote);
    int b=strlen(magazine);
    if(a>b) return false;
    else{
        for(int i=0;i<b;i++){
            countchar[magazine[i]-'a']++;
        }
        for(int i=0;i<a;i++){
             countchar[ransomNote[i]-'a']--;
        }
    }
    for(int i=0;i<26;i++){
        if(countchar[i]<0){
            return false;
        }
    }
    return true
