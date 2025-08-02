VIL# Language Demonstration

This document provides an overview and detailed explanation of the core features of the VIL# language, using a single, structured program as a reference. VIL# is a hypothetical, simple language designed for educational purposes, demonstrating common programming concepts.
The VIL# Demonstration Program

The following code block contains a complete VIL# program that showcases all of the language's fundamental commands and structures, including variables, control flow, functions, classes, and more.

// =========================================================
// VIL# Demonstration Program
// This program showcases all supported VIL# commands and features,
// structured within a main demonstration function.
// =========================================================

// Define the main demonstration function
func mainDemoProgram() {

    // --- 1. Variable Declarations and Basic Operations ---
    print "\n--- 1. Variable Declarations and Basic Operations ---";
    var message = "Hello, VIL# World!";
    print message; // Output: Hello, VIL# World!

    var num1 = 10;
    var num2 = 5;
    var sum = num1 + num2;
    print "Sum of num1 and num2: ";
    print sum; // Output: 15

    var difference = num1 - num2;
    print "Difference: ";
    print difference; // Output: 5

    var product = num1 * num2;
    print "Product: ";
    print product; // Output: 50

    var quotient = num1 / num2;
    print "Quotient: ";
    print quotient; // Output: 2

    var remainder = num1 % num2;
    print "Remainder: ";
    print remainder; // Output: 0

    var isTrue = true;
    var isFalse = false;
    print "Is true: ";
    print isTrue; // Output: true
    print "Is false: ";
    print isFalse; // Output: false

    // Prefix operator: NOT
    var notTrue = !isTrue;
    print "Not true: ";
    print notTrue; // Output: false

    // Prefix operator: Unary Minus
    var negativeNum = -num1;
    print "Negative num1: ";
    print negativeNum; // Output: -10


    // --- 2. Conditional Statements (if-else) ---
    print "\n--- 2. Conditional Statements ---";
    var age = 20;
    if (age > 18) {
        print "You are an adult.";
    } else {
        print "You are a minor.";
    }

    var temperature = 25;
    if (temperature > 30) {
        print "It's hot!";
    } else if (temperature > 20 && temperature <= 30) { // Logical AND
        print "It's warm.";
    } else {
        print "It's cold!";
    }

    var isAdmin = true;
    var isAuthenticated = false;
    if (isAdmin || isAuthenticated) { // Logical OR
        print "Access granted (admin or authenticated).";
    } else {
        print "Access denied.";
    }


    // --- 3. Looping Constructs ---
    print "\n--- 3. Looping Constructs ---";

    // While loop
    print "While loop (counting down):";
    var counter = 3;
    while (counter > 0) {
        print "Count: ";
        print counter;
        counter = counter - 1;
    }

    // For loop
    print "For loop (counting up):";
    for (var i = 0; i < 3; i = i + 1) {
        print "Iteration: ";
        print i;
    }

    // Do-While loop
    print "Do-While loop (always runs at least once):";
    var doWhileCounter = 0;
    do {
        print "Do-While iteration: ";
        print doWhileCounter;
        doWhileCounter = doWhileCounter + 1;
    } while (doWhileCounter < 2);

    // Break and Continue in a loop
    print "Loop with break and continue:";
    for (var j = 0; j < 5; j = j + 1) {
        if (j == 1) {
            print "Skipping iteration 1 (continue)";
            continue; // Skips the rest of the current iteration
        }
        if (j == 3) {
            print "Breaking loop at iteration 3 (break)";
            break; // Exits the loop entirely
        }
        print "Loop value: ";
        print j;
    }


    // --- 4. Functions ---
    print "\n--- 4. Functions ---";

    // Function declaration
    func greet(name) {
        print "Hello, ";
        print name;
        print "!";
        return 1; // Example return value
    }

    // Function call
    var greetingResult = greet("Alice");
    print "Greeting function returned: ";
    print greetingResult;

    // Function with multiple parameters
    func add(a, b) {
        return a + b;
    }
    var result = add(10, 20);
    print "Result of add(10, 20): ";
    print result;

    // Async function (demonstrates keyword, actual async behavior depends on C# compilation)
    async func fetchData() {
        print "Fetching data asynchronously...";
        // In a real scenario, this would involve a network call or I/O
        // For demonstration, we'll simulate a delay.
        pause 100; // Simulate a short delay
        print "Data fetched!";
        return "Some data";
    }

    // Await expression
    async func runAsyncDemo() { // Renamed to avoid conflict with `mainAsync` if it were a top-level function
        print "Calling async function...";
        var data = await fetchData();
        print "Received data: ";
        print data;
    }

    // Call the async demo function
    runAsyncDemo();


    // --- 5. Classes (Basic Structure) ---
    print "\n--- 5. Classes ---";

    class MyClass {
        // Class field
        var classField = "I am a class field.";

        // Constructor-like function (VIL# 'init' maps to C# static constructor for simplicity)
        func init() {
            print "MyClass 'init' (constructor) called.";
        }

        // Class method
        func displayMessage(msg) {
            print "MyClass says: ";
            print msg;
            print "My class field value: ";
            print classField;
        }
    }

    // Calling a static method on the class (VIL# doesn't have instance creation yet)
    MyClass.init();
    MyClass.displayMessage("This is a message from MyClass.");


    // --- 6. Error Handling (try-catch) ---
    print "\n--- 6. Error Handling ---";
    try {
        print "Inside try block.";
        // Simulate an error (e.g., division by zero)
        var zero = 0;
        var errorResult = 10 / zero; // This will cause a runtime error
        print "This line will not be reached if an error occurs.";
    } catch (e) {
        print "Caught an error!";
        print "Error details (from VIL# 'e' variable): ";
        print e; // The generated C# will print the exception message
    }


    // --- 7. User Input ---
    print "\n--- 7. User Input ---";

    // String input
    input "Enter your name: ";
    var userName; // Variable to store the input
    print "Hello, ";
    print userName;
    print "!";

    // Integer input
    input_int "Enter your favorite number: ";
    var favNumber; // Variable to store the integer input
    print "Your favorite number is: ";
    print favNumber;
    var doubledFavNumber = favNumber * 2;
    print "Doubled: ";
    print doubledFavNumber;


    // --- 8. Built-in Math Functions ---
    print "\n--- 8. Built-in Math Functions ---";

    var val = 16;
    var resultSqrt = sqrt(val);
    print "Square root of 16: ";
    print resultSqrt; // Output: 4

    var negVal = -10;
    var resultAbs = abs(negVal);
    print "Absolute value of -10: ";
    print resultAbs; // Output: 10

    var baseVal = 2;
    var exponentVal = 3;
    var resultPow = pow(baseVal, exponentVal);
    print "2 raised to the power of 3: ";
    print resultPow; // Output: 8


    // --- 9. Control Commands ---
    print "\n--- 9. Control Commands ---";

    // Pause command (pauses execution for a specified duration in milliseconds)
    print "Pausing for 500 milliseconds...";
    pause 500;
    print "Resumed after pause.";

    // Stop command (terminates the program)
    // Uncomment the line below to see it in action.
    // print "Stopping program now...";
    // stop;
    // print "This line will not be reached if 'stop' is uncommented.";

    print "\n--- End of VIL# Demonstration Program ---";
}

// Call the main demonstration function to start the program execution
mainDemoProgram();


