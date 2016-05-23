# oci connect

* *Returns a connection identifier needed for most other OCI8 operations.* 
* *The second and subsequent calls to oci_connect() with the same parameters will return the connection handle returned from the first call. This means that transactions in one handle are also in the other handles, because they use the same underlying database connection. If two handles need to be transactionally isolated from each other, use oci_new_connect() instead.*
* (http://php.net/manual/en/function.oci-connect.php)

## References
* http://php.net/manual/en/function.oci-connect.php

##### Connects to the XE service (i.e. database) on the "localhost" machine using Easy Connect syntax
```php
<?php

// Connects to the XE service (i.e. database) on the "localhost" machine
$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```
