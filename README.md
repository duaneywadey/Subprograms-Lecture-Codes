# Subprograms Implementation

## Basic subprograms example using Python:

```python

# Subprogram: Convert inches to centimeters
def inches_to_cm(inches):
    cm = inches * 2.54
    return cm

# Subprogram: Convert centimeters to inches
def cm_to_inches(cm):
    inches = cm / 2.54
    return inches

# Main program
def main():
    # Convert inches to centimeters
    inches = 10
    cm = inches_to_cm(inches)
    print(f"{inches} inches is equal to {cm} centimeters.")

    # Convert centimeters to inches
    cm = 25
    inches = cm_to_inches(cm)
    print(f"{cm} centimeters is equal to {inches} inches.")

# Calling the main program
main()

```

## Subprograms modularity example:

```python

# Subprogram 1: Calculate the square of a number
def calculate_square(num):
    return num * num

# Subprogram 2: Calculate the cube of a number
def calculate_cube(num):
    return num * num * num

# Main program
def main():
    number = 5

    # Calling the subprograms
    square_result = calculate_square(number)
    cube_result = calculate_cube(number)

    # Outputting the results
    print(f"The square of {number} is: {square_result}")
    print(f"The cube of {number} is: {cube_result}")

# Calling the main program
main()

```

## Subprograms reusability example:

```python

# Subprogram: Check if a number is even
def is_even(num):
    return num % 2 == 0

# Main program
def main():
    number1 = 10
    number2 = 7
    number3 = 15
    number4 = 8

    # Calling the subprogram multiple times
    print(f"{number1} is {'even' if is_even(number1) else 'odd'}")
    print(f"{number2} is {'even' if is_even(number2) else 'odd'}")
    print(f"{number3} is {'even' if is_even(number3) else 'odd'}")
    print(f"{number4} is {'even' if is_even(number4) else 'odd'}")

# Calling the main program
main()


```

## Subprograms encapsulation example:

```python


# Subprogram: Calculate the average of a list of numbers
def calculate_average(numbers):
    total = sum(numbers)
    average = total / len(numbers)
    return average

# Main program
def main():
    # List of numbers
    numbers = [5, 10, 15, 20, 25]

    # Calling the subprogram
    average_result = calculate_average(numbers)

    # Outputting the result
    print(f"The average of the numbers is: {average_result}")

# Calling the main program
main()



```


## Pass by value (Java implementation)

```java


public class PassByValue {

    public static void main(String[] args) {
        int x = 5;
        changeValue(x);
        System.out.println(x); // Prints 5
    }

    private static void changeValue(int x) {
        x = 10;
    }
}


```

## Pass by result (Java implementation)

```java


public class PassByResult {

    public static void main(String[] args) {
        int x = 5;
        x = changeValueAndReturnResult(x);
        System.out.println(x); // Prints 10
    }

    private static int changeValueAndReturnResult(int x) {
        x = 10;
        return x;
    }
}



```


## Pass by reference (C++ Implementation)

```cpp



#include <iostream>

// Function to swap two integers using call by reference
void swapByReference(int& a, int& b) {
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int x = 5;
    int y = 10;

    std::cout << "Before swap: x = " << x << ", y = " << y << std::endl;

    // Call the function
    swapByReference(x, y);

    std::cout << "After swap: x = " << x << ", y = " << y << std::endl;

    return 0;
}



```

## Pointer example

```cpp


#include <iostream>

int main() {
    
    int num1 = 4; 
    int num2 = 8; 

    // Declare a pointer variable ptr and assign it the address of num1
    int *ptr = &num1; 
    
    // Change the value of num1 to 5
    num1 = 5;

    // Dereference the pointer ptr and assign the 
    // value 10 to the variable it points to (num1) 
    *ptr = 10;

    // Change the value of the pointer ptr to the address of num2
    ptr = &num2;

    // Change the value of num2 to 15 
    num2 = 15; 

    // Print the values
    std::cout<<"Num 1: " << num1 << std::endl; 
    std::cout<<"Num 2: " << num2 << std::endl; 
    std::cout<<"Pointer value: " << *ptr << std::endl;

    return 0;
}




```

## Basic Error Handling in Python

```python

 
def find_nth_value(x, n):

    # Attempt to access the n-th element of list x
    try:
        result = x[n]

    # Catch the IndexError exception if it occurs      
    except IndexError as err: 
        print(err)  

    # If no exception occurs, print the result
    else:
        print("Your answer is ", result)  

x = [5,8,9,13]

find_nth_value(x, 2)  
find_nth_value(x, 3)  
find_nth_value(x, 4) 


 

```

## Bank System with Error Handling

```python
class BankAccount:
    def __init__(self, account_holder, balance):
        self.account_holder = account_holder
        self.balance = balance

    def withdraw(self, amount):
        try:
            if amount <= 0:
                raise ValueError("Invalid amount for withdrawal.")
            if self.balance < amount:
                raise Exception("Insufficient funds.")
            self.balance -= amount
            print(f"Withdrew {amount} from the account. New balance: {self.balance}")
        except ValueError as e:
            print(str(e))
        except Exception as e:
            print(str(e))

    def deposit(self, amount):
        try:
            if amount <= 0:
                raise ValueError("Invalid amount for deposit.")
            self.balance += amount
            print(f"Deposited {amount} into the account. New balance: {self.balance}")
        except ValueError as e:
            print(str(e))

# Usage:
account = BankAccount("John Doe", 1000)
account.withdraw(500)
account.withdraw(2000)
account.withdraw(-100)
account.deposit(1000)

```
