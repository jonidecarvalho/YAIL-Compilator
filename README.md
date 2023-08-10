# YAIL-Compilator
Compilator for YAIL (Yet Another Invented Language)

## Language Origin
This is an unfinished project for the course unit of Compilation in the Computer Engineering program at Universidade Aberta.

## Tools
The tools chosen are:
- Bison
- Flex

## Language Chosen
The language chosen to create the YAIL Compiler is C.

## Language Structure
Here is an example of a simple program that prints 5 times "helo world" using a constant variable.

```
    #program that prints Hello World! 5 times

    constant{
        int times=5;
    }

    main() bool {
        local { int i; };
        for(i,0,5,1) {
            write("Hello World!");
        }
    }
```

### Comments
Coments are represented by a line of characteres after the # symbol.
Its usage is possible through the following declaration:
```
    #EVERY CARACTER UNTIL END OF LINE
```
example:
```
    #this is a comment!
```

### Structs
Data structures are available with structs through the declaration:
```
    srtucts{
        STURCT_NAME { TYPE VAR };
    }
```

example:
```
    structs{
        point2D { float x, y };
    }
```

The data will be available through the folowing declaration:
```
    STRUCTS_NAME.VAR
```
example:
```
    point2D.x = 1.42;
```

### Globals
Global variables are available through the following declaration:
```
    global{
        TYPE VAR;
    }
```
example:
```
    global{
        bool check;
        int iterations=5;
    }
```

### Constants
Constants are available through the following declaration:
```
    constant{
        TYPE VAR_DECLARATION;
    }
```
example:
```
constant{
    float pi=3.14;
}
```

### Functions
All functions will have the structure:
```
    FUNCTION_NAME(ARGUNENTS) TYPE {
        ...
    }
```
example:
```
    print_number float(float b) {
        write("b = ",b);
    }
```

### Main Function
The main fuction will always be the first function its return type will always be boolean and the function doesnt have arguments. Here is how to declare the main function:
```
    main() bool{
        ...
    }
```

### EOL
Excluding comments, structures, globals, constants, and function declarations, the end of the line should be represented by a ";".
```
    local { int x, y, z; };
```

### Types
integer, floating and boolean are the 3 types available.

```
    int i;
    float x=0.45;
    bool check; 
```

Integers and floating numbers have negative and positive values.
Every non initialized variable have an implicit value which are:

```
    int i; #i=0
    float x; #x=0.00
    bool check; #check=false
```

### Type Conversions

int conversion:

| type  | value                     |
| ----- | ------------------------- |
| bool  | true = 1                  |
| bool  | false = 0                 |
| float | whole part (truncation)   |

float converstion:
| type  | value                     |
| ----- | ------------------------- |
| bool  | true = 1                  |
| bool  | false = 0                 |
| int   | no change                 |

bool conversion:
| type  | value                     |
| ----- | ------------------------- |
| int   | 0 = fale                  |
| int   | < 0 = true                |
| int   | > 0 = true                |
| float | ]-1,1[ = false            |
| float | ]-∞,-1]∪[1, +∞[ = true    |

Example:
```
    float x=0.5;
    int y=2;
    bool z=true;

    x = y + z; # y + z = 3 (z=1), x = 3   >> int + bool → int → float
    y = x + z; # x + z =1.5 (z=1), y=1    >> float + bool → float → int
    z = x + y; # x + y =2.5, z=true       >> float + int → float → bool

```

### Conditionals
Conditional flow control is available through the usage of "if" and "else" statements as the following:
```
    if(CONDITIONAL) {
        ...
    } else {
        ...
    }
```
example:
```
    if (n>2) {
        write("All good!");
    } else {
        write("Something went wrong");
    }
```

### Cicles
Repetitive flow control is available through the usage of "for" and "while" statements.
The "for" statements are available through the following declaration:
```
    for(VARIABLE,START,FINISH,INCREMENTATION) {
        ...
    }
```
example:
```
    for(i,0,6,2) {
        write(i) #output will be 0 then 2 then 4 and it stops
    }
```
The "while" statements are available through the folowing declaration:
```
    while(CONDITIONAL) {
        ...
    }
```
example:
```
    while(n>2) {
        n/=2;
        write("value:" n);
    }
```

### Attributions
Attribution is possible with the usage of the "="(equal) symbol and its used as the following declaration:
```
    VAR = EXPRESSION
```
example:
```
    x = 2 * y;
```

### Expressions
Expressions are available with the operators: + addition, - subtraction, \* multiplication , / division and % modulus.
example:
```
    x = 1 + 2;
    x = 1 - 2:
    x = 1 * 2;
    x = 1 / 2;
    x = 1 % 2;
```
Its possible to have attribution with usage of operators before the equal sign.
example:
```
    x += 2; #the equivalent of x = x + 2
    x -= 2; #the equivalent of x = x - 2
    x *= 2; #the equivalent of x = x * 2
    x /= 2; #the equivalent of x = x / 2
    x %= 2; #the equivalent of x = x % 2
```
The incrementation and decrementation is possible with the usage of the ++(incrementation) and --(decrementation).\
example:
```
    x++; #the equivalent of x+=1 or x = x + 1
    x--; #the equivalent of x-=1 or x = x - 1
```

### Output data
Ouput data is available with the usage of a special function which is write().\
write() is available through the following examples:
```
    write("");      #ouputs Test and ends with new line 
    write("Test"); #ouputs Test and ends with new line 
```
write() can have access of variable values like so:

```
    write("You have ", messages, " new messages.");
```

### Input data
Input data is available with the usage of a special function which is read().
read() is available through the following declaration:
```
    x = read();
```

### Special Functions
This language contains special functions which are already defined and ready to use.\
They are pow() for power of two float numbers and square_root() for square root of a number.\
pow() is available through the following declaration:
```
    pow(BASE,EXPONENT);
```
example:
```
    pow(2,6); #this is equivalent of 2^6
```
square_root() is available through the following declaration:
```
    square_root(VALUE);
```
example:
```
    square_root(62); #returns a float
```

