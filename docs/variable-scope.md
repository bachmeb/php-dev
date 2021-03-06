# variable scope

## References
* http://php.net/manual/en/language.variables.scope.php

##### What is scope
* *The scope of a variable is the context within which it is defined.*
* *For the most part all PHP variables only have a single scope.*

##### Included
* *The single scope spans included and required files.*

##### Local
* *Any variable used inside a function is by default limited to the local function scope.*

##### Global
* *In PHP global variables must be declared global inside a function if they are going to be used in that function.*
* *By declaring a variable global within a function, all references to the variable will refer to the global version.* 
* *There is no limit to the number of global variables that can be manipulated by a function.*
* *Another way to access variables from the global scope is to use the special PHP-defined $GLOBALS array.*
* *The $GLOBALS array is an associative array with the name of the global variable being the key and the contents of that variable being the value of the array element.*
