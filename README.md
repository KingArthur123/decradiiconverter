# decradiiconverter
#include <stdio.h>
#include <math.h>
#include <string.h>
int decValue;
int radValue;
//void Dec2RadixI(int decValue, int radValue)
void main(int decValue, int radValue)
{

    printf("*****************************\nDECIMAL TO RADIX-i converter\nWritten by: ARTHUR NDEH FOUTE\nDate:2022/08/2022\n*****************************\n");

    while(decValue>=0){
       printf("Enter a decimal number:");
       scanf("%d",&decValue);

       if(decValue<0){
       printf("EXIT");
       break;
       }

       else
       printf("The number you have entered is %d\n", decValue);
       printf("Enter a radix for the converter between 2 and 16:");
       scanf("%d",&radValue);
       printf("The radix you have entered is %d\n", radValue);
       //result=log2(decValue);
       //int i;
       //i=0;
       int remainder=0; //initialising remainder
       char* rem[36];
       unsigned int c[36]={0};

       // converting num to alphabets when needed
       char change(int value)
       {
           if(value>=0 && value<=9)
            return (char)(value +'0');
           else
            return (char)(value-10 +'A');// return A from 10, B from 11 and so on
       }

       // reversing function

       void reverse(char *str)
       {
           int len= strlen(str);
           int i;
           for (i=0; i<len/2;i++)
           {
               char temp=str[i];
               str[i]=str[len-i-1];
               str[len-i-1]=temp;
           }

       }

       while(decValue!=0){
           printf("The log2 of the number is");
           float log2value=log2(decValue); // calculating log 2 of decimal value inputted
           printf(" %.2f\n", log2value);
           printf("The integer result of the number divided by 2 is");// divide the num by 2
           printf(" %d\n", decValue);

           rem[remainder++]=change(decValue%radValue); // remainder when divided by 2
           decValue=decValue/radValue;

           //printf("The remainder is");
           //printf(" %s\n", remainder);
           //c[i]=remainder;
           //i++;
       }
       printf("The radix-2 value is ");
       rem[remainder]='\0';
       reverse(rem);
       return rem;
       printf("%s",rem);
       //for(i=i-1; i>=0;i--)
           //printf("%d",c[i]);
       printf("\n");





}



    //return 0;   //print basic information about the coder and functions of the code
}
