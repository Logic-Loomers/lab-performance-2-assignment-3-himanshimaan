[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Fmb6W2KK)
Design a C++ program for an employee payroll system. Create classes for Employee and Payroll. Users can add employees, enter hours worked, calculate salaries, and generate payroll reports.

#include <iostream>
#include <map>
#include <string>

using namespace std;

class Library {
private:
    map<string, string> bookMap;

public:
    Library() {
        // Initialize the library with some books
        bookMap["9780132350884"] = "The C++ Programming Language";
        bookMap["9780321563842"] = "Effective C++";
        bookMap["9780201633610"] = "Design Patterns";
    }

    string searchBook(const string& isbn) {
        auto bookIterator = bookMap.find(isbn);
        if (bookIterator != bookMap.end()) {
            return bookIterator->second;
        } else {
            return "Book not available in the library.";
        }
    }
};

int main() {
    Library library;
    string inputISBN;
    cout << "Enter the ISBN: ";
    cin >> inputISBN;

    // Search for the book title using the library object
    string bookTitle = library.searchBook(inputISBN);
    
    // Print the result
    cout << "Book Title: " << bookTitle << endl;

    return 0;
}
