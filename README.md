# isat-subtask2.
#include <iostream>
#include <string>
#include <bitset>
#include <sstream>
#include <algorithm>

using namespace std;

// Function to convert Decimal to Binary
string decimalToBinary(int num) {
    return bitset<32>(num).to_string().substr(bitset<32>(num).to_string().find('1'));
}

// Function to convert Binary to Decimal
int binaryToDecimal(string binaryStr) {
    int decimal = 0;
    try {
        decimal = stoi(binaryStr, nullptr, 2);
    } catch (...) {
        throw invalid_argument("Invalid binary number.");
    }
    return decimal;
}

// Function to convert Decimal to Hexadecimal
string decimalToHexadecimal(int num) {
    stringstream ss;
    ss << hex << uppercase << num;
    return ss.str();
}

// Function to convert Hexadecimal to Decimal
int hexadecimalToDecimal(string hexStr) {
    int decimal = 0;
    try {
        decimal = stoi(hexStr, nullptr, 16);
    } catch (...) {
        throw invalid_argument("Invalid hexadecimal number.");
    }
    return decimal;
}

// Menu Function
void menu() {
    while (true) {
        cout << "\n=== Conversion Menu ===" << endl;
        cout << "1. Convert Decimal to Binary" << endl;
        cout << "2. Convert Binary to Decimal" << endl;
        cout << "3. Convert Decimal to Hexadecimal" << endl;
        cout << "4. Convert Hexadecimal to Decimal" << endl;
        cout << "5. Exit" << endl;

        cout << "Enter your choice (1-5): ";
        string choice;
        getline(cin, choice);

        if (choice == "1") {
            int dec;
            cout << "Enter a decimal number: ";
            cin >> dec;
            cin.ignore();
            cout << "Binary equivalent: " << decimalToBinary(dec) << endl;
        }
        else if (choice == "2") {
            string binary;
            cout << "Enter a binary number: ";
            getline(cin, binary);
            try {
                cout << "Decimal equivalent: " << binaryToDecimal(binary) << endl;
            } catch (const exception& e) {
                cout << e.what() << endl;
            }
        }
        else if (choice == "3") {
            int dec;
            cout << "Enter a decimal number: ";
            cin >> dec;
            cin.ignore();
            cout << "Hexadecimal equivalent: " << decimalToHexadecimal(dec) << endl;
        }
        else if (choice == "4") {
            string hex;
            cout << "Enter a hexadecimal number: ";
            getline(cin, hex);
            try {
                cout << "Decimal equivalent: " << hexadecimalToDecimal(hex) << endl;
            } catch (const exception& e) {
                cout << e.what() << endl;
            }
        }
        else if (choice == "5") {
            cout << "Exiting program..." << endl;
            break;
        }
        else {
            cout << "Invalid choice! Please try again." << endl;
        }
    }
}

// Main Function
int main() {
    menu();
    return 0;
}




