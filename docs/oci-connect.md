# oci connect

* *Returns a connection identifier needed for most other OCI8 operations.* 
* *The second and subsequent calls to oci_connect() with the same parameters will return the connection handle returned from the first call. This means that transactions in one handle are also in the other handles, because they use the same underlying database connection. If two handles need to be transactionally isolated from each other, use oci_new_connect() instead.*
* (http://php.net/manual/en/function.oci-connect.php)

## References
* http://php.net/manual/en/function.oci-connect.php

##### 
