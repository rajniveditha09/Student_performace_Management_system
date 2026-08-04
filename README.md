#include<stdio.h>
#include<stdlib.h>
int inputmarks(int std[], int n)
{
    for(int i =0 ; i< n ; i++)
    {
        scanf("%d",&std[i]);
    }
}
int displaymarks(int std[],int n){
 for(int i =0 ; i< n ; i++)
    {
        printf("%d\n",std[i]);
    }
}
float calculateaverage(int std[],int n){
    int sum=0;
    int average;
    for(int i =0 ; i<n;i++){
        sum = sum + std[i];
    }
    average = sum/n;
    return (float)average;
}
int highest(int std[],int n){
    int highest = 0;
    for(int i =0; i<n;i++){
        if(std[i]>highest){
            highest = std[i];
        }
    }
    return highest;
}
int lowest(int std[], int n){
    int lowest = 100;
    for(int i =0; i<n;i++){
        if (std[i]< lowest){
            lowest = std[i];
        }
    }
    return lowest;
}
int countpass(int std[],int n){
    int count =0;
    for(int i =0; i<n;i++){
        if(std[i]>35){
            count++;
        }
    }
    return count;
}
int countfail(int std[],int n){
    int count1 = 0;
    for(int i =0;i<n;i++){
        if(std[i]<35){
            count1++;
        }
    }
    return count1;
}
char gradegiven(int std[], int n){
    for(int i =0;i<n;i++){
        if(std[i]>90 && std[i]<100){
            printf("grade of std[%d]= 'O'\n" ,i);
        }
         if(std[i]>80 && std[i]<90){
            printf("grade of std[%d]= 'A' \n" ,i);
        }
        if(std[i]>70 && std[i]<80){
            printf("grade of std[%d]= 'B' \n" ,i);
        }
        if(std[i]>60 && std[i]<70){
            printf("grade of std[%d]= 'C'\n " ,i);
        }
        if(std[i]>50 && std[i]<60){
            printf("grade of std[%d]= 'D'\n " ,i);
        }
        if(std[i]>35 && std[i]<50){
            printf("grade of std[%d]= 'E'\n " ,i);
        }
        if(std[i]>0 && std[i]<35){
            printf("grade of std[%d]= 'F' \n" ,i);
        }
    }
}
int searchstudentbyroll(int std[],int n){
    int input;
    scanf("%d",&input);
    for(int i =0;i<n;i++){
        if(input==i){
            printf("score of a[%d]=%d",i,std[i]);
        }
    }
}
int main(){
    int n;
    scanf("%d",&n);
    int std[n];
    inputmarks(std,n);
    displaymarks(std,n);
    printf("%0.2f\n",calculateaverage(std,n));
    printf("highest score is %d\n",highest(std,n));
    printf("lowest score is %d\n",lowest(std,n));
    printf("count of passed students is %d\n",countpass(std,n));
    printf("count of failed students is %d\n",countfail(std,n));
    searchstudentbyroll(std,n);
    return 0;
}
