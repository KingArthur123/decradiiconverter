#include <stdio.h>
#include <math.h>
#include <string.h>


// To return char for a value. For example '2'
// is returned for 2. 'A' is returned for 10. 'B'
// for 11
char res[3000];
char convert(int num)
{
    if (num >= 0 && num <= 9)
        return (char)(num + '0');
    else
        return (char)(num - 10 + 'A');
}

// Utility function to reverse a string
void reverse(char *str)
{
    int len = strlen(str);
    int i;
    for (i = 0; i < len/2; i++)
    {
        char temp = str[i];
        str[i] = str[len-i-1];
        str[len-i-1] = temp;
    }
}

// Function to convert a given decimal number
// to a base 'base' and
Dec2RadiixI( int decValue, int radValue)
{
    //char res[100];
    int index = 0;  // Initialize index of result

    // Convert input number is given base by repeatedly
    // dividing it by base and taking remainder
    while (decValue > 0)
    {
        res[index++] = convert(decValue % radValue);
        decValue /= radValue;
    }
    res[index] = '\0';

    // Reverse the result
    reverse(res);
    return res;
    //return res;
}



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


       printf("The log2 of the number is");
       //float log2value=(log2)(decValue); // calculating log 2 of decimal value inputted
        printf(" %.2f\n", log2(decValue));
        printf("The integer result of the number divided by %d is ",radValue);// divide the num by 2
        int value= (decValue /radValue);
        printf("%d\n",value);
        printf("The remainder is ");
        int rem=(decValue%radValue);
        printf("%d\n",rem);

        printf("The radix-2 value is ");
        printf("%s",Dec2RadiixI( decValue, radValue));
        printf("\n");

        return;
    }//print basic information about the coder and functions of the code

}
