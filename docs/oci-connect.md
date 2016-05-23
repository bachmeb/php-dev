# oci connect

* *Returns a connection identifier needed for most other OCI8 operations.* 
* *The second and subsequent calls to oci_connect() with the same parameters will return the connection handle returned from the first call. This means that transactions in one handle are also in the other handles, because they use the same underlying database connection. If two handles need to be transactionally isolated from each other, use oci_new_connect() instead.*
* (http://php.net/manual/en/function.oci-connect.php)

## References
* http://php.net/manual/en/function.oci-connect.php
* http://www.oracle.com/technetwork/articles/dsl/technote-php-instant-084410.html

##### Install the Oracle Instant Client for Linux 
* *OCI8 is the PHP extension for connecting to Oracle Database. OCI8 is open source and included with PHP. The name is derived from Oracle's C "call interface" API first introduced in version 8 of Oracle Database. OCI8 links with Oracle client libraries, such as Oracle Instant Client.*
* *Oracle Instant Client is a free set of easily installed libraries that allow programs to connect to local or remote Oracle Database instances. To use Instant Client an existing database is needed - Instant Client does not include one. Typically the database will be on another machine. If the database is local then Instant Client, although convenient and still usable, is generally not needed because OCI8 can directly use the database libraries.*
* *When using Instant Client 11g, PHP OCI8 connects to all editions of Oracle 9.2, 10.x, and 11.x databases.*
* http://www.oracle.com/technetwork/articles/dsl/technote-php-instant-084410.html


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
