# PHP-SYNTAX GUIDE

# PHP comments 
Are lines of code that are not live, that exist to keep notes or pass messages to other developers.

Ex.


    <?php
    // Single-line comment
    /* Multiline Comment */
    ?>

# PHP Variables
- Act like containers to store information, and start with $ sign.
- Must start with letter, or underscore character
- Cannot begin with a number 
- Can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Are case sensitive ($code and $CODE result different values
 

    <?php
    $txt = "Greetings Earthlings!";
    ?>

# PHP Echo / Print 
- Output data to the browser.  
- Echo has no return value, taking multiple parameters and is faster than print. 
- Print returns a value of 1 and can be used in expressions.


    <?php
    echo $variable_name;
    echo "<h2>Learning PHP!</h2>";
    echo "A ", "string , "made ", "with multiple parameters.";
    ?>

# PHP Data Types 
Variables can store data of different types, that can perform different actions.

### PHP String  
A sequence of characters, that exist inside quotes, like "greetings earthlings".


    <?php
    $txt = "greetings earthlings!";
    echo $txt;
    echo "<br>";
    ?> 

### PHP Integer 
- An integer data type is a non-decimal number between -2,147,483,648 and 2,147,483,647.
- Must have at least one digit
- Must not have a decimal point
- Can be either positive or negative
- Can be specified in: decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation

In the ex below, $y is an integer and **php var_dump()** function returns the data type and value

    <?php
    $y = 8000;
    var_dump($y);
    ?>

### PHP Float 
A number with a decimal point or a number in exponential form.

    <?php
    $y = 3.14;
    var_dump($y);
    ?>

### PHP Boolean  
Represents two possible states: TRUE or FALSE. 

### PHP Array  
Stores multiple values in one single variable.

    <?php
    $languages = array("english","french","Swahili");
    var_dump($languages);
    ?>

### PHP Object
- Classes and objects are the two main parts of object-oriented programming.
- When individual objects are created, properties and behaviors are inherited from the class, and each object will have different values for the properties.
- Let's say we have a class language. Properties of this would be type, tone, location, which would be defined as **$type** , **$tone** , **$location**
- When individula obects (swahili, soft, africa) is created, they inherit properites and behaviours from the class

When you create a **__construct()** function, PHP  automatically calls this function when you create an object from a class.

    <?php
    class language {
      public $type;
      public $tone;
      public function __construct($type, $tone) {
        $this->type = $type;
        $this->tone = $tone;
      }
      public function message() {
        return "My language " . $this->type . " " . $this->tone . "!";
      }
    }
    $myLanguage = new Language("english", "progressive");
    echo $myLanguage -> message();
    echo "<br>";
    $myCar = new Language("french ", "soft");
    echo $myLanguage -> message();
    ?>

### PHP NULL Value  
is a variable that has no value assigned to it, and if created without a value, by default is assigned  a value of NULL.

    <?php
    $y = "greeting earthlings!";
    $z = null;
    var_dump($y);
    ?> 

### PHP Resource 
A special resource type is not an actual data type. It  the stores reference to functions and resources external to PHP.

# PHP Strings 
A collection of characters , like " greetings earthlings"
	

### PHP Strings  
Are sequences of letters, numbers, special characters and arithmetic values and can be a combination of all. 

- Can be declared in single quotes or double quotes, but the results are different.

Ex. 

    <?php
    $my_str = 'earthlings';
    echo "greetings, $my_str!<br>";      // Displays: greetings earthlings!
    echo 'greetings, $my_str!<br>';      // Displays: greetings, $my_str!
    ?>

#### Escape Characters 
    \n — Line feed
    \r — Carriage return 
    \t — Horizontal tab 
    \v — Vertical tab 
    \e — Escape 
    \f — Form feed
    \\ — Backslash
    \$ — Dollar sign

##### Manipulating PHP Strings

   strlen() - Return the Length of a String

    <?php
    echo strlen("greetings earthlings!"); // outputs 19
    ?>

str_word_count() function counts the number of words in a string.

    <?php
    $my_str = 'We come in peace.';
    // Outputs: 4
    echo str_word_count($my_str);
    ?>

   str_replace() replaces all occurrences of the search text within the target string.

    <?php
    $my_str = 'If the hat fits, why not wear it .';
    // Display replaced string
    echo str_replace("car", "drive", $my_str);
    ?>

strrev() function reverses a string.

    <?php
    $my_str = 'If I move backwards, do I move forwards.';
    // Display reversed string
    echo strrev($my_str);
    ?>

# PHP Numbers
PHP provides automatic data type conversion.

PHP Integer data type is a non-decimal number between -2147483648 and 2147483647. 

**Integer Rules**
- At least one digit
- Not have a decimal point
- Can be either positive or negative
- Can be specified in three formats: decimal (10-based), hexadecimal (16-based prefixed with 0x) or octal (8-based - prefixed with 0)

##### How to check if variable is an integer
   is_int()
   is_integer() - alias of is_int()
   is_long() - alias of is_int()

    <?php
    $z = 6597;
    var_dump(is_int($z));
    $y = 65.97;
    var_dump(is_int($y));
    ?>

### PHP Floats 
Are numbers with a decimal point or a number in exponential form. 2.0, 256.4, 10.358, 7.64E+5, 5.56E-5 .
Can store a value up to 1.7976931348623E+308 , and have a maximum precision of 14 digits.

**How to check if integers are floats**

   is_float()
   is_double() - alias of is_float()

EX. 

    <?php
    $y = 3.14;
    var_dump(is_float($y));
    ?>


### PHP Infinity
It is considered infinate when a numeric value is larger than PHP_FLOAT_MAX 

**How to check if integers are floats**

   is_finite()
    is_infinite()

    <?php
    $y = 2.8e322;
    var_dump($y);
    ?>

### PHP NaN  
Not a Number

**How to check if integers are NAN**

   is_nan()

    <?php
    $y = acos(6);
    var_dump($y);
    ?>

### PHP Numerical Strings
- is_numeric() used to find whether a variable is numeric. 
- If the variable is a number the function returns true and false if not.


    <?php
    $y = 6597;
    var_dump(is_numeric($y));
    ?>

### PHP Casting Strings and Floats to Integers

(int), (integer), or intval() functions  convert a value to an integer.

    <?php
    // Cast float to int
    $y = 3.14;
    $int_cast = (int)$y;
    echo $int_cast;
    ?>

# PHP Constants  
- Are identifiers for a value, and the value cannot be changed.
- Starts with a letter or underscore
- Constants are global automatically.
- **define()** function creates constants.

Syntax
define(name, value, case-insensitive)

EX.

    <?php
    define("greetings", "welcome to 2021!");
    echo greetings;
    ?>

### PHP Constant Arrays
Use **define()** function to create an array

EX.

    <?php
    define("language", [
      "English",
      "French ",
      "Swahili"
    ]);
    echo language[0];
    ?>

# PHP Operators
#### Arithmetic Operators
    + — Addition
    - — Subtraction
    * — Multiplication
    / — Division
    % — Modulo (the remainder of value divided by another) ** — Exponentiation


#### Comparison Operators
    == — Equal
    === —Identical
    != — Not equal
    <> — Not equal
    !== —Notidentical
    < — Less than
    > — Greater than
    <= — Less than or equal to
    >= — Greater than or equal to
    <=> —Lessthan,equalto,orgreaterthan
    Logical Operators
    and —And
    or —Or
    xor —Exclusiveor ! —Not
    && —And
    || —Or


#### Increment/Decrement Operators
    ++$v
    Increments a variable by one, then returns it
    $v++
    Returns a variable, then increments it by one
    --$v
    Decrements the variable by one, returns it afterward
    $v--
    Returns the variable then decrements it by one
    String Operators
    .
    Used to concatenate (mean combine) arguments
    .=
    Used to append the argument on the right to the left-side argument

# PHP if & Else, Elseif

**if Statement** = executes if 1 condition is true:

    if (condition) {
      code to be executed if condition is true;
    }

EX.
Output "greetings earthlings!" if the current time (HOUR) is less than 5:

    <?php
    $y = date("H");
    if ($t < "5") {
      echo "greetings earthlings!";
    }
    ?>

#### PHP - The if...else Statement

    if (condition) {
      code  executed if condition is true;
    } else {
      code  executed if condition is false;
    }

EX.
Output "greetings earthlings!" if the current time is less than 5, and "we come in peace" otherwise:

    <?php
    $t = date("H");
    if ($t < "20") {
      echo "greetings earthlings!";
    } else {
      echo "we come in peace!";
    }
    ?>

#### PHP - The if...elseif...else Statement

    if (condition) {
       executed if this condition is true;
    } elseif (condition) {
       executed if first condition is false and this condition is true;
    } else {
       executed if all conditions are false;
    }

EX.
Output "greetings earthlings!" if the current time is less than 5, and "we come in peace!" if the current time is less than 10. Otherwise it will output "bring us to your leader!":

    <?php
    $t = date("H");
    if ($t < "5") {
      echo "greetings earthlings!";
    } elseif ($t < "10") {
      echo "we come in peace!";
    } else {
      echo "bring us to your leader!";
    }
    ?>

# PHP User Defined Functions

Functions can be repeatedly used, will not automatically execute when page loads, and executed by a call

**Syntax**

    function functionName() {
      code to be executed;
    }

Ex.

    <?php
    function msgWrite() {
      echo "greeting earthlings!";
    }
    msgWrite(); // call the function
    ?>

#### PHP Function Arguments
Passes information and is similar to a variable.

    <?php
    function diffLanguage($dlang) {
      echo "$fdlang Refsnes.<br>";
    }
    diffLanguage("english");
    diffLanguage("Swahili");
    ?>

#### PHP Functions - Returning values  
Use the return statement.

EX.

    <?php declare(strict_types=1); // strict requirement
    function sum(int $x, int $y) {
      $z = $x + $y;
      return $z;
    }
    echo "3 + 4 = " . sum(3, 14) . "<br>";
    echo "5 + 7 = " . sum(5, 7) . "<br>";
    echo "1+ 3 = " . sum(1, 3);
    ?>

# PHP Arrays 
**array()** function is used to create an array:

There are 3 types of array

1. **Indexed arrays** - Arrays with a numeric index
2. **Associative arrays** - Arrays with named keys
3. **Multidimensional arrays** - Arrays containing one or more arrays

 **count()** Function = Getting the length of an array 

EX.

    <?php
    $language = array("english", "french", "Swahili");
    echo count($Language);
    ?>

# PHP Loop

#### Loop Types
- **while** - loops through code if the condition is true
- **do...while** - loops through code once, and then repeats the loop if condition is true
- **for** - loops through code a specific number of times
- **foreach** - loops through code for each element in an array
