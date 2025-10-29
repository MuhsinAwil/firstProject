#include <stdio.h>
#include <math.h>
#include <time.h>

int isPrime(int num){
    if(num == 1) return -1;
    if(num == 2) return 1;
    for(int i = 2; i <= num/2; i++){
        if(num % i == 0){
            return 0;
        }
    }
    return 1;
}

int main() {
    int num1,num2,num,binary,result,choice;
    
    time_t currentTime;
    time(&currentTime);
    printf("Current Time: %s\n", ctime(&currentTime));
    
    while(1){
        printf("Which operation would you like to do. Enter a number\n1: Mathematical operation\n2: Logical operation\n3: Prime number detection\n4: Close calculator\n");
        scanf("%d", & choice);
        if(choice == 1){
            int choice1;
            printf("Which number operation would you like to do. Enter a number\n1: Arithmatic\n2: Modulus\n3: Power funciton\n");
            scanf("%d", & choice1);
            if(choice1 == 1){
                char operation;
                printf("Enter the first number\n");
                scanf("%d", & num1);
                printf("Enter the second number\n");
                scanf("%d", & num2);
                printf("Enter the operation you would like to perform\n");
                scanf(" %c",& operation);
                switch(operation){
                    case '+':
                        result = num1 + num2;
                        printf("%d + %d = %d\n", num1, num2, result);
                        break;
                    case '-':
                        result = num1 - num2;
                        printf("%d - %d = %d\n", num1, num2, result);
                        break;
                    case '*':
                        result = num1 * num2;
                        printf("%d * %d = %d\n", num1, num2, result);
                        break;
                    case '/':
                        result = num1 / num2;
                        if(num2 == 0){
                            printf("Error, dividing by zero, please try again\n");
                        }
                        else{
                            printf("%d / %d = %d", num1, num2, result);
                        }
                        break;
                    default:
                        printf("invalid input please try again");
                        break;
                    
                }
            }
            else if(choice1 == 2){
                printf("Enter the first number\n");
                scanf("%d", & num1);
                printf("Enter the second number\n");
                scanf("%d", & num2);
                result = num1 % num2;
                printf("%d modules with %d = %d\n", num1, num2, result);
            }
            else if(choice1 == 3){
                printf("Enter your base\n");
                scanf("%d", & num1);
                printf("Enter your power\n");
                scanf("%d", & num2);
                result = pow(num1,num2);
                if(result > 1000000000){
                    printf("Error: Output to large\n");
                }
                else{
                    printf("%d to the power of %d is %d\n", num1, num2, result);
                }
            }
            else{
                printf("Invalid input, please try again");
            }
        }
        else if (choice == 2){
            int choice2;
            printf("Which logical operation would you like to perform\n1: AND\n2: OR\n3: NOT\n");
            scanf("%d", & choice2);
            if(choice2 == 1){
                printf("Enter a binary number\n");
                scanf("%d", & num1);
                printf("Enter another binary number\n");
                scanf("%d", & num2);
                result = num1 && num2;
                printf("The end result of the logical operation is %d\n", result);
                
            }
            else if (choice2 == 2){
                printf("Enter a binary number\n");
                scanf("%d", & num1);
                printf("Enter another binary number\n");
                scanf("%d", & num2);
                result = num1 || num2;
                printf("The end result of the logical operation is %d\n", result);
            }
            else if(choice2 == 3){
                printf("Enter a binary number\n");
                scanf("%d", & num1);
                result != num1;
                printf("The end result of the logical operation is %d\n", result);
            }
            else{
                printf("Invalid input, please try again");
            }
        }
        else if(choice == 3){
            int choice3;
            printf("What would you like to do. Enter the number of your choice\n1: Determine whether a number is prime or not\n2: print all prime numbers up to a certain point\n");
            scanf("%d", & choice3);
            if(choice3 == 1){
                printf("Enter an integer\n");
                scanf("%d", & num);
                if(num <= 0){
                    printf("Invalid number, please try again\n");
                    continue;
                }
                result = isPrime(num);
                if(result == 1){
                    printf("The integer is a prime number\n");
                }
                else if(result == 0){
                    printf("The integer is a composite number\n");
                }
                else{
                    printf("The integer is neither prime nor composite\n");
                }
            }
            else if(choice3 == 2){
                printf("Enter a number\n");
                scanf("%d", & num);
                printf("Here are all the prime numebers leading up to the number\n");
                result = isPrime(num);
                for(int i = 1; i<=num; i++){
                    if(isPrime(i)){
                        printf("%d  ", i);
                    }
                }
                printf("\n");
            }
            else{
                printf("Invalid input, try again\n");
            }
        }
        else if(choice == 4){
            printf("Shutting down ... \n");
            return 0;
        }
        else{
            printf("Invalid input, please try again\n");
        }
    }
    return 0;
}
