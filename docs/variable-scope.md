# variable scope

## References
* http://php.net/manual/en/language.variables.scope.php

##### What is scope
* *The scope of a variable is the context within which it is defined. For the most part all PHP variables only have a single scope. This single scope spans included and required files as well.*

##### Local
* *Any variable used inside a function is by default limited to the local function scope.*

##### Global
* *In PHP global variables must be declared global inside a function if they are going to be used in that function.*
* By declaring $a and $b global within the function, all references to either variable will refer to the global version. There is no limit to the number of global variables that can be manipulated by a function.
