# session_register()

## References
* http://php.net/manual/en/function.session-register.php

##### What does session_register() do?
* *session_register() accepts a variable number of arguments, any of which can be either a string holding the name of a variable or an array consisting of variable names or other arrays.*
* *For each name, session_register() registers the global variable with that name in the current session.*

##### Should session_register be used? 
* *Use of session_register() is deprecated*
* *Use of $_SESSION is preferred, as of PHP 4.1.0*
* *The old way was to use $HTTP_SESSION_VARS*
