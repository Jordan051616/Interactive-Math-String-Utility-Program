# Interactive-Math-String-Utility-Program
//Author: Jordan Garcia
//Assignmet: Loop Mastery - C++ Interactive Menu System
//Description: creating a loop mastery 

#include <iostream>
#include <string>
using namespace std;

void factorialCalculator() {
    int n;
    cout << "Enter a positive integer: ";
    cin >> n;

    unsigned long long factorial = 1;
    int i = 1;

    while (i <= n) {
        factorial *= i;
        i++;
    }

    cout << "Factorial of " << n << " is: " << factorial << endl;
}

void numberPyramid() {
    int rows;
    cout << "Enter number of rows: ";
    cin >> rows;

    for (int i = 1; i <= rows; i++) {
        for (int j = 1; j <= rows - i; j++) {
            cout << " ";
        }
        for (int k = 1; k <= i; k++) {
            cout << k << " ";
        }
        cout << endl;
    }
}

void sumEvenOrOdd() {
    int choice, limit;
    int sum = 0, i = 1;

    cout << "Choose an option:\n1. Sum of Even Numbers\n2. Sum of Odd Numbers\nEnter choice: ";
    cin >> choice;
    cout << "Enter the upper limit: ";
    cin >> limit;

    i = 1;
    do {
        if (choice == 1 && i % 2 == 0)
            sum += i;
        else if (choice == 2 && i % 2 != 0)
            sum += i;
        i++;
    } while (i <= limit);

    if (choice == 1)
        cout << "Sum of even numbers up to " << limit << ": " << sum << endl;
    else
        cout << "Sum of odd numbers up to " << limit << ": " << sum << endl;
}

void reverseString() {
    string str;
    cout << "Enter a string: ";
    cin >> str;

    int i = str.length() - 1;
    cout << "Reversed string: ";
    while (i >= 0) {
        cout << str[i];
        i--;
    }
    cout << endl;
}

int main() {
    int choice;

    do {
        cout << "\n========= Interactive Utility Program =========\n";
        cout << "1. Factorial Calculator\n";
        cout << "2. Number Pyramid\n";
        cout << "3. Sum of Even or Odd Numbers\n";
        cout << "4. Reverse a String\n";
        cout << "5. Exit\n";
        cout << "==============================================\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            factorialCalculator();
            break;
        case 2:
            numberPyramid();
            break;
        case 3:
            sumEvenOrOdd();
            break;
        case 4:
            reverseString();
            break;
        case 5:
            cout << "Goodbye! Thanks for using the program.\n";
            break;
        default:
            cout << "Invalid choice! Please try again.\n";
        }

    } while (choice != 5);

    return 0;
}
