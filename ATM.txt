#include <stdio.h>
//Global Variables
int balance =20000,k,amount,c;
char ch;

//Function Prototypes...
void quit();
void withdraw(int amount);
void deposit(int amount);
void check_balance();

//Function Declarations....
void check_balance(){
    printf("\nYour Account Balance is : %d\n",balance);
}

void withdraw(int amount){
    printf("Your current Account Balance is : %d\n",balance);
    if(balance-amount>=0){
        balance -= amount;
        printf("\nTransaction Successfull\nCash Withdrawn = %d\n",amount);
        printf("Your current Account Balance is : %d\n",balance);
    }else{
        printf("\nTransaction Failed - Insufficent Balance\n");
        printf("Your current Account Balance is : %d\n",balance);
    }
}

void deposit(int amount){
    printf("Your current Account Balance is : %d\n",balance);
    balance += amount;
    printf("Transaction Successfull\nAmount Deposited = %d\n",amount);
    printf("Your current Account Balance is : %d\n",balance);
}

void quit(){
    printf("\nThankYou for using Our ATM service:D:D\n");
}

int main(){
    int pin;
    printf("========Welcome========\n");
    printf("Enter Your Pin code(i.e 1005) : ");
    scanf("%d",&pin);
    while(pin!=1005){
        printf("Invalid pin code,Please enter valid Pin code\n");
        printf("\n========Welcome========\n");
        printf("Enter Your Pin code(i.e 1005) : ");
        scanf("%d",&pin);
    }
    do{
        printf("==========Welcome to ATM Service==========\n");
        printf("Enter 1 to check account balance\n");
        printf("Enter 2 to withdraw cash from account\n");
        printf("Enter 3 to deposit cash to the account\n");
        printf("Enter 4 to quit the ATM Service\n");
        printf("\nEnter Your Choice : ");
        scanf("%d",&c);
        switch(c){
            case 1 :check_balance();
                    break;
            case 2 :printf("Enter the amount to be Withdrawn : ");
                    scanf("%d",&amount);
                    withdraw(amount);
                    break;
            case 3 :printf("Enter the amount to be Deposited : ");
                    scanf("%d",&amount);
                    deposit(amount);
                    break;
            case 4 :quit();
                    break;
            default:printf("Invalid Choice pls try again\n");
        }
    }while(c!=4);

    return 0;
}