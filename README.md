# YAIL-Compilator
Compilator for YAIL (Yet Another Invented Language)

##Language origin
This is an unfinished project for the course unit of Compilation in the Computer Engineering program at Universidade Aberta.

##language structure

###comments
Coments are represented by a line of characteres after the # symbol.
Its usage is possible through the following declaration:
#EVERY CARACTER UNTIL END OF LINE
'''
#this is a comment!
''

###structs
Data structures are available with structs through the declaration:
srtucts{
    STURCT_NAME { VAR_DECLARATION };
}

'''
structs{
    point2D { float x, y };
}
''

The data will be available through the folowing declaration:
STRUCTS_NAME.VAR
'''
point2D.x = 1.42;
''

###globals
Global variables are available through the following declaration:
global{
    TYPE VAR_DECLARATION/VAR_INITIATION;
}
'''
global{
    bool check;
    int iterations=5;
}
''

###constants
Constants are available through the following declaration:
constant{
    TYPE VAR_DECLARATION;
}
'''
constant{
    float pi=3.14;
}
''


###functions
All functions will have the structure:
FUNCTION_NAME TYPE(ARGUNENTS) {
    BODY
}

'''
average float(float b) {
...
}
''

###main function
the main fuction will always be the first function and its type will be boolean
'''
main bool() {
    ...
}
''

###EOL
Excluding comments, structures, globals, constants, and function declarations, the end of the line is represented by a ; (semicolon).
'''
int x, y, z;
''

###types
integer, floating and boolean are the 3 types available.
'''
int i;
float x=0.45;
bool check; 
''

Integers and floating numbers have negative and positive values.
Every non initialized variable have a default value witch are:
'''
#default values
int i; #i=0
float x; #x=0.00
bool check; #check=false
''

###type conversions
