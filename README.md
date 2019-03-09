# CM Hub: Introduction to C++
Introduction to C++ course for the CM Hub at Imperial College

* **Part 0:** Setting up C++
* **Part 1:** Hello world! Your first steps with C++
* **Part 2:** Functions
* **Part 3:** ~~C++ with maths in mind~~

## Aims of the course

* You can write a simple C++ program
* You can understand and edit more complicated C++ programs you have been given
* You feel comfortable searching online for help

## Part 0. Setting up C++

**To do before coming to class. If you need some help completing this section, come to the pre-class drop-in at 00:00**

Before we start the class, you need to get C++ set up on your machine.

For some programming languages, like Matlab, there is just one program you need to open to write your code and then run it. For others, like C++, you will need one program to write your code, and then one program to 'compile' it: i.e., turn it into something you can run.

Before you come to class, you need to complete the following steps:

1. Have a text editor ready (we recommend [Atom](https://atom.io/))
2. Have a C++ compiler installed and working

### Step 1: Have a text editor ready
We are going to be writing our code in a text editor. This is a program which lets us produce plain text files. There are lots of choices available, but we recommend downloading [Atom](https://atom.io/).

### Step 2: Have a C++ compiler installed and working
A compiler is a program which takes the text file we have written and turns it into something we can run. Compilers do not look like normal programs, with windows and graphics. Instead they are run using the command line. We will discuss this in class but for now, follow the instructions below, depending on which type of machine you will use.

**If you have difficulties, come to the pre-class drop-in session.**

#### Instructions for Mac and Linux
1. Open Terminal.
2. Type `c++` and press Enter.
3. If it says `clang: error: no input files` or `c++: fatal error: no input files`, then you are ready to go. **If you get any other message, come to the pre-class drop-in session.**

#### Instructions for Windows (your own computer)
First let's check that you haven't already got a C++ compiler on your computer. If you have installed Fortran in the past, you might already have a C++ compiler.

1. Open Command Prompt from the Start menu (right-click the Start button and select Command Prompt).
2. Type `g++` and press Enter.
3. If you get the error `g++: fatal error: no input files`, then you are good to go. If you get a different message, you don't have a C++ compiler installed and should continue following these instructions.
4. To install the compiler, follow the instructions [on this YouTube video](https://www.youtube.com/watch?v=sXW2VLrQ3Bs). Is this awkward? Yes. Is it worth it? Yes!
5. Check that it works by following steps 1--3 above.

#### Instructions for Windows (college machine)

(For Krishna!)

## Part 1. Hello world!

### 1. Where C++ sits among other languages
<img src="/readme-images/maths-not-maths-languages.png" width="50%">

Pros of C++:
* Free
* Fast
* Lots of support
* Lots of libraries

Cons of C++:
* Ideosyncratic
* Steep learning curve
* Not obvious how best to use for science
* Difficult to debug

In short: C++ is a robust, fast language whose steep learning curve makes it worthwhile using for only large maths problems.

### 2. Getting ready

* Create a new folder somewhere
* Open up Terminal or Command Prompt and navigate to that folder using `cd`

### 3. Hello world!

* Open up Atom

```c++
#include <iostream>

using namespace std;

int main()
{
    cout << "Hello world!" << endl;
    return 0;
}
```

* Save as `helloworld.cpp` (colours!)
* Compile by going to the command line and typing
```bash
c++ helloworld.cpp -o hello
```
(or `g++` on Windows)

* Then run the program
```bash
./hello
```

Try:
* Adding an extra line to the message

### 4. Use of variables
Join in:
* `int x;`
* `x = 4;`
* `cout << "The value of x is" << x << endl;`
* Compile and run.

Your turn:
* Change the code so it prints *2x* instead.
* Let *x* = 3.9. What do you expect to happen? What happens?

Join in:
* `double x;`
* `double y;`
* `cout << "The value of x is " << x << "and the value of y is" << y << endl;`
* Compile and run.

Your turn:
* Change the code so that it also prints out the product of *x* and *y*.

### 5. Command-line input
Join in:
* New file! `height.cpp`. Note that we're going to use strings here, which need the `<string>` library.
```c++
#include <iostream>
#include <string>

using namespace std;

int main()
{
    string name;
    float height;
    cout << "What is your name?" << endl;
    cin >> name;
    cout << "What is your height?" << endl;
    cin >> height;
    cout << name << "is" << height << "metres tall."
    return 0;
}
```
* Compile and run.

Your turn:
* Convert the height into feet (1 metre = 3.28084 feet)
* Convert the height into feet and inches (1 foot = 12 inches). For example, entering 1.81 (metres) should produce "5 feet 11 inches". Hint: `a%b` = *a* mod *b*.
* What happens if we type nonsense into the inputs?

### 6. Maths
Basic arithmetic works out of the box, as you've seen. For 'scientific calculator' stuff, we need the `<cmath>` library. Libraries are like toolboxes.

Join in:
* New file! `calculator.cpp`
```c++
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    float x;
    cout << "Enter a number" << endl;
    cin >> x;
    cout << "That number squared is" << pow(x,2) << endl;
    cout << "The square root of that number is" << sqrt(x) << endl;
    return 0;
}
```

Your turn:
* Add a line displaying the sine of the inputted number.
* Change the code so that it inputs two integers, *a* and *b*, and displays *a*/*b*.

### 7. If
Join in:
* New file! `bartender.cpp`
```c++
#include <iostream>

using namespace std;

int main()
{
    int age;
    cout << "Welcome to the pub." << endl;
    cout << "What is your age?" << endl;
    cin >> age;
    if(age >= 18){
        cout << "Have a pint!" << endl;
    }
    cout << "Goodbye!" << endl;
    return 0;
}
```
* Compile and run!
* Let's make it more fun with `else`
```c++
if(age > 18){
    cout << "Have a pint!" << endl;
} else if(age == 18){
    cout << "Show me your ID and then have a pint!" << endl;
} else {
    cout << "I'm calling the police." << endl;
}
```
* Compile and run!

Your turn:
* Also input the name of the customer
* If the name of the customer does not equal your name, get the bartender to ask for money. Hint: `!=` is 'not equal to' in C++.

### 8. For and while loops
Join in:
* New file! `square_numbers.cpp`
```c++
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    int n = 10;
    for(int i=0; i<n; ++i){
        cout << pow(i,2) << endl;
    }
    return 0;
}
```
* Compile and run!

Try:
* Save the script as `cube_numbers.cpp`
* Change the script to display the 3rd to 9th cubes.

Join in:
* Change the file: let's **comment out** the for loop above and instead write it as a while loop.
```c++
int i=3; // We can define and initialise a variable at the same time.
while(i<10){
    cout << pow(i,3) << endl;
    ++i;
}
```

Try:
* Change the script to display the 3rd, 5th, 7th and 9th cubes (i.e. go up in 2s, not in 1s)

Try:
* The Collatz conjecture: create a new script, `collatz_conjecture.cpp`, which inputs a number *n*, and while *n* does not equal 1:
    * Let *f* = *n*/2 if *n* is even
    * Let *f* = 3*n* + 1 if *n* is odd
    * Display *f*
    * Let *n* = *f*

### 9. Saving and reading data

To save and read file, we need to include the `<fstream>` library.

Join in:

* New file! `save_to_file.cpp`

```c++
#include <iostream>
#include <fstream>

using namespace std;

int main()
{
    ofstream myfile;
    myfile.open ("greeting.txt");
    myfile << "Hello there!" << endl;
    myfile.close();

    return 0;
}
```

Your turn:
* Print the first 10 squares to a text file.

Join in:

* Now read in...

* New file! `read_from_file.cpp`

```c++
#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main()
{
    string line;
    ifstream myfile;
    myfile.open ("greeting.txt");
    while (getline(myfile,line)){
        cout << line << endl;
    }
    myfile.close();

    return 0;
}
```

### 10. Arrays

Join in:

* Edit `square_numbers.cpp`
```c++
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    int n = 10;
    int square_numbers[10];
    for(int i=0; i<n; ++i){
        square_numbers[i] = pow(i,2);
    }
    for(int i=0; i<n; ++i){
        cout << square_numbers[i] << endl;
    }    
    return 0;
}
```
* Note you can't `cout` an array
* We can also define arrays like this:
```c++
int main()
{
    int n = 10;
    int square_numbers[10];
    int favourite_numbers[10];

    for(int i=0; i<n; ++i){
        square_numbers[i] = pow(i,2);
    }

    favourite_numbers = {3, 1, -4, 1}; // Note we haven't defined them all.

    for(int i=0; i<n; ++i){
        cout << square_numbers[i] << endl;
    }    
    for(int i=0; i<n; ++i){
        cout << favourite_numbers[i] << endl;
    }        

    return 0;
}
```
* We can also declare:
    * `int favourite_numbers[10] {3,1,-4,1}`
    * `int favourite_numbers[] {3,1,-4,1}`

* Multidimensional arrays work too
    * `int magic_square[3][3] = {{4,9,2},{3,5,7},{8,1,6}}`

* Some basic functionality exists
    * `#include <algorithm>`
    * `max_element(favourite_numbers)`

Try:
* Create a new file `multiplication_table.cpp`. We are going to make it print a 10x10 multiplication table. Make it:
    * Set up a 10x10 array `product`.
    * Loop through all rows and columns, so that `product[row][col] = row * col;`
    * Loop through all rows and columns again, `cout`ing appropriately the elements of the table.

 Join in:
 * `const int numRows = 10;`


### 11. Functions and header files

Writing functions allows us to do more complicated things.

Join in:

* New file! `learning_functions.cpp`

```c++
#include <iostream>

using namespace std;

int sign_function(int n)
{
    int sign;
    if(n>0){
        sign = 1;
    } else if(n==0){
        sign = 0;
    } else {
        sign = -1;
    }
    return sign;
}

int main()
{
    int n;
    n = 3;
    cout << sign_function(n) << endl;

    return 0;
}
```
* Global and local variables.
* Note: order is important. What happens if you define `sign_function` after `main`?

Your turn:

* Add an extra function to this file, `absolute_value`, which returns the absolute value of an integer which is passed to it.
* Add an extra line to the `main` function so that it also displays the absolute value of *n*.

Join in:

* There is a way to define functions with `main` first: it's called 'forward declaration'.
* In general, this is better because it allows more flexible code.

```c++
#include <iostream>

using namespace std;

int sign_function(int n);

int main()
{
    int n;
    n = 3;
    cout << sign_function(n) << endl;

    return 0;
}

int sign_function(int n)
{
    int sign;
    if(n>0){
        sign = 1;
    } else if(n==0){
        sign = 0;
    } else {
        sign = -1;
    }
    return sign;
}

```
* Compile and run!
* Now we're going to split our `sign_function` and `absolute_value` functions into separate files, and call them from our main file.

`learning_functions.cpp`:
```c++
#include <iostream>

using namespace std;

int sign_function(int n);
int absolute_value(int n);

int main()
{
    int n;
    n = 3;
    cout << sign_function(n) << endl;

    return 0;
}
```

`sign_function.cpp`:
```c++
#include <iostream> // not strictly necessary

using namespace std;

int sign_function(int n)
{
    int sign;
    if(n>0){
        sign = 1;
    } else if(n==0){
        sign = 0;
    } else {
        sign = -1;
    }
    return sign;
}
```

`absolute_value.cpp`:
```c++
#include <iostream> // not strictly necessary

using namespace std;

int absolute_value(int n)
{
    return abs(n);
}
```

* And now we compile like this:
```bash
c++ sign_function.cpp absolute_value.cpp learning_functions.cpp -o sign
```
* All these forward declarations can be tiresome, so we can put them in a header file and `#include` it:

`learning_functions.hpp`:
```c++
int sign_function(int n);
int absolute_value(int n);
```

`learning_functions.cpp`:
```c++
#include <iostream>
#include "learning_functions.hpp" // double quotes for user-defined header files

using namespace std;

int main()
{
    int n;
    n = 3;
    cout << sign_function(n) << endl;

    return 0;
}
```

(`sign_function.cpp` and `absolute_value.cpp` unchanged)

* Compile and run, remembering to include all files in the compile command.
* The header file is also a good place to put constants you want to have pre-defined in all of the files in your project.

### 12. Libraries for mathematics

To do more advanced linear algebra in C++, you need to use a specialised library. I recommend [Armadillo](http://arma.sourceforge.net/), which uses syntax quite similar to that used in Matlab or Python (with NumPy). Setup is different for different operating systems but the instructions are pretty good.

### 13. Optimisation
* When compiling, use the flag `-O2` to optimise for speed a little bit. Use `-O3` for more optimisation. `-O0` is the default. Example:
```bash
c++ helloworld.cpp -o hello -O3
```

### 999. Extra stuff we won't do

#### Installing Armadillo

1. Download the stable version from [the Armadillo website](http://arma.sourceforge.net/download.html). It comes as a `.tar.xz` file.
2. Unzip this file. On Windows, you might need to use [7-Zip](https://www.7-zip.org/) to unzip it.
3. Move the armadillo folder to the folder you are creating the C++ files in.
4. Compile along these lines:
```bash
    g++ example1.cpp -o example1 -O2 -I ./armadillo-7.200.3/include -DARMA_DONT_USE_WRAPPER -lblas -llapack
```
Replace -lblas with -lopenblas if you have OpenBLAS. On macOS, replace -lblas -llapack with -framework Accelerate

#### Debugging
