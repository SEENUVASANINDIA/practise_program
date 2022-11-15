    #include <stdio.h>  
    #include <string.h>    
    void substring(char s[], char sub[], int p, int len){  
       int c = 0;  
       while (c < len) {  
          sub[c] = s[p+c];  
          c++;  
       }  
       sub[c] = '\0';  
    }  

void pdrome(char string1[])
{
    int i, length;
    int flag = 0;
     length = strlen(string1);    
    for(i=0;i < length ;i++){
        if(string1[i] != string1[length-i-1]){
            flag = 1;
            break;
           }
        }
    
    if (flag) {
        printf("\n%s is not a palindrome\n", string1);
    }    
    else {
        printf("\n%s is a palindrome\n", string1);
    }
    
}

void main()  
    {  
        char c[10],str[10] ;  
        int i, j,len;  
        printf("\nEnter a string:");
       scanf("%s", str);
        len = strlen(str);
        printf("\nThe main string ");
       pdrome(str);
        printf("\nAll subsets for the given string are: ");  
        //This loop maintains the starting character  
        for(i = 0; i < len; i++){  
            //This loop adds the next character every iteration for the subset to form and add it to the array  
            for(j = 1; j <= len-i; j++){  
                substring(str,c,i,j); 
                printf("\n%s",c);
                pdrome(c); 
                 
            }  
        }    
    }  
