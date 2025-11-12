# Cpp
#include 

using namespace std; 

// Function for Linear Search 

int linearSearch(int arr[], int n, int key) { 

for (int i = 0; i < n; i++) { 

if (arr[i] == key) 

return i; // found 

} 

return -1; // not found 

} 

// Function for Binary Search 

int binarySearch(int arr[], int n, int key) { 

int low = 0, high = n - 1; 

while (low <= high) { 

int mid = (low + high) / 2; 

if (arr[mid] == key) 

return mid; // found 

else if (arr[mid] < key) 

low = mid + 1; 

else 

high = mid - 1; 

} 

return -1; // not found 

} 

int main() { 

int choice; 

int n, key, result; 

cout << "\nEnter number of students: "; 

cin >> n; 

int roll[n]; 

cout << "Enter roll numbers of students:\n"; 

for (int i = 0; i < n; i++) 

cin >> roll[i]; 

do { 

cout << "\n====== MENU ======\n"; 

cout << "1. Linear Search (Random Order)\n"; 

cout << "2. Binary Search (Sorted Order)\n"; 

cout << "3. Exit\n"; 

cout << "Enter your choice: "; 

cin >> choice;switch (choice) { 

case 1: 

cout << "Enter roll number to search: "; 

cin >> key; 

result = linearSearch(roll, n, key); 

if (result != -1) 

cout << "Student with roll number " << key << " attended the program.\n"; 

else 

cout << "Student with roll number " << key << " did NOT attend the program.\n"; 

break; 

case 2: 

cout << "Note: Enter roll numbers in sorted order for Binary Search.\n"; 

cout << "Enter roll number to search: "; 

cin >> key; 

result = binarySearch(roll, n, key); 

if (result != -1) 

cout << "Student with roll number " << key << " attended the program.\n"; 

else 

cout << "Student with roll number " << key << " did NOT attend the program.\n"; 

break; 

case 3: 

cout << "Exiting program...\n"; 

break; 

default: 

cout << "Invalid choice! Please try again.\n"; 

} 

} while (choice != 3); 

return 0; 

} 

