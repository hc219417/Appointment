# Appointment
**Objective:** work with classes, strings, separate compilation, and operator overloading

Design a class called Appointment that stores the properties of a calendar appointment. Properties include the appointment title, date **(year, month, day)**, starting **time (military time)**, and duration. Your class must check for invalid values for year, month, day, time, and duration. Your class must include the following getters and setters for all member data **(function names and prototypes must match exactly)**:

- `Appointment() //default constructor`

It should initialize the title to "N/A". The date should be initialized to 1, 1, and 1. The time should be initialized to 0, and duration to 1.

- `Appointment(string appData)`

Add an appointment from a string in the format "`title|year|month|day|time|duration`". Time is given in standard time and duration is given in minutes. Leading and trailing spaces must be removed. Example: "`Meeting with Bob | 2021 |11 |23 |8:30 aM | 15`"

- `string getTitle()`
- `int getYear()`
- `int getMonth()`
- `int getDay()`
- `int getTime() //military time`
- `int getDuration()`
- `string getDate() //return a date in the format 2021-11-23`
- `string getStandardTime()`
- `void setTitle(string newTitle)`
- `void setYear(int newYear)`
- `void setMonth(int newMonth)`
- `void setDay(int newDay)`
- `void setTime(int newTime) //military time`
- `void setDuration(int newDuration)`
- `void setDate(int newYear, int newMonth, int newDay)`

In addition, the class must include the following helper functions:

- `string militaryToStandard(int time)`

Converts time from military (1830) to standard time ("6:30PM")

- `int standardToMilitary(string time)`

Converts standard time ("8:30PM") to military time (2030). It should handle lower and upper-case letters. Returns the time in military time format (2030).

- `bool operator == (const Appointment &first, const Appointment &second)`
 
Write a main program to test all the functions above. Make sure you check for invalid values. Separate your program into three files: (`appointment.h`, `appointment.cc`, and `appointment_main.cc`)

**Separate Compilation:**

First, test your program using a single file "appointment_main.cc". Divide your project into three files:

• `appointment.h`

Contains the class definition

• `appointment.cc`

Contains the class implementation (all the functions)

• `appointment_main.cc`

Main program to test your class

**Compiling your project manually:**

1. `g++ -Wall -c appointment.cc`

This creates the object file appointment.o

2. `g++ -Wall -c appointment_main.cc`

This creates the object file appointment_main.o

3. `g++ appointment.o appointment_main.o`

This creates the executable `a.out`

or

`g++ -Wall -c appointment.cc appointment_main.cc`

There is a Makefile provided to allow you to compile your program using the command:

`make` (Mac/Linux) or `mingw32-make` (Windows)

You can verify the correctness of your code by running the provided unit tests. To run the tests:

`make run_tests_mac` (Mac/Linux)

`mingw32-make run_tests_win` (Windows)
