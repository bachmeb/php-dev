# oci connect

* *Returns a connection identifier needed for most other OCI8 operations.* 
* *The second and subsequent calls to oci_connect() with the same parameters will return the connection handle returned from the first call. This means that transactions in one handle are also in the other handles, because they use the same underlying database connection. If two handles need to be transactionally isolated from each other, use oci_new_connect() instead.*
* (http://php.net/manual/en/function.oci-connect.php)

## References
* http://php.net/manual/en/function.oci-connect.php
* http://www.oracle.com/technetwork/articles/dsl/technote-php-instant-084410.html
* http://www.hexblot.com/blog/making-connection-php-oracle-centos-64
* https://moodle.org/mod/forum/discuss.php?d=324931
* http://board.phpbuilder.com/showthread.php?10339128-RESOLVED-pecl-install-phpize-failed

##### Install the Oracle Instant Client for Linux 
* https://github.com/bachmeb/oracle-admin/blob/master/docs/oracle-instant-client.md

##### Install php-devel
```
sudo yum install php-devel
```

##### Search for php-pear
```
yum search php-pear
```

##### See if php-pear is installed
```
sudo yum list installed | grep php
```

##### Install php-pear
```
sudo yum install php-pear
```

##### Make sure pecl is installed
```
pecl help
```

##### Run channel update
```
sudo pecl channel-update pecl.php.net
```
```c
/*
Updating channel "pecl.php.net"
Update of Channel "pecl.php.net" succeeded
*/
```

##### Install OCI8 for PHP 5.3
```
sudo pecl install oci8-2.0.10
```
```c
/*
downloading oci8-2.0.10.tgz ...
Starting to download oci8-2.0.10.tgz (191,379 bytes)
.........................................done: 191,379 bytes
11 source files, building
running: phpize
Configuring for:
PHP Api Version:         20090626
Zend Module Api No:      20090626
Zend Extension Api No:   220090626
Please provide the path to the ORACLE_HOME directory. Use 'instantclient,/path/to/instant/client/lib' if you're compiling with Oracle Instant Client [autodetect] : 
building in /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10
running: /var/tmp/oci8/configure --with-oci8
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for a sed that does not truncate output... /bin/sed
checking for cc... cc
checking for C compiler default output file name... a.out
checking whether the C compiler works... yes
checking whether we are cross compiling... no
checking for suffix of executables...
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether cc accepts -g... yes
checking for cc option to accept ISO C89... none needed
checking how to run the C preprocessor... cc -E
checking for icc... no
checking for suncc... no
checking whether cc understands -c and -o together... yes
checking for system library directory... lib
checking if compiler supports -R... no
checking if compiler supports -Wl,-rpath,... yes
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
checking target system type... x86_64-unknown-linux-gnu
checking for PHP prefix... /usr
checking for PHP includes... -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib
checking for PHP extension directory... /usr/lib64/php/modules
checking for PHP installed headers prefix... /usr/include/php
checking if debug is enabled... no
checking if zts is enabled... no
checking for re2c... no
configure: WARNING: You will need re2c 0.13.4 or later if you want to regenerate PHP parsers.
checking for gawk... gawk
checking for Oracle Database OCI8 support... yes, shared
checking PHP version... 5.3.3, ok
checking OCI8 DTrace support... no
checking size of long int... 8
checking checking if we're on a 64-bit platform... yes
configure: WARNING: OCI8 extension: ORACLE_HOME is not set, looking for default Oracle Instant Client instead
checking Oracle Instant Client directory... /usr/lib/oracle/12.1/client64/lib
checking Oracle Instant Client SDK header directory... /usr/include/oracle/12.1/client64
checking Oracle Instant Client library version compatibility... 12.1
checking for a sed that does not truncate output... (cached) /bin/sed
checking for fgrep... /bin/grep -F
checking for ld used by cc... /usr/bin/ld
checking if the linker (/usr/bin/ld) is GNU ld... yes
checking for BSD- or MS-compatible name lister (nm)... /usr/bin/nm -B
checking the name lister (/usr/bin/nm -B) interface... BSD nm
checking whether ln -s works... yes
checking the maximum length of command line arguments... 1966080
checking whether the shell understands some XSI constructs... yes
checking whether the shell understands "+="... yes
checking for /usr/bin/ld option to reload object files... -r
checking for objdump... objdump
checking how to recognize dependent libraries... pass_all
checking for ar... ar
checking for strip... strip
checking for ranlib... ranlib
checking command to parse /usr/bin/nm -B output from cc object... ok
checking for dlfcn.h... yes
checking for objdir... .libs
checking if cc supports -fno-rtti -fno-exceptions... no
checking for cc option to produce PIC... -fPIC -DPIC
checking if cc PIC flag -fPIC -DPIC works... yes
checking if cc static flag -static works... no
checking if cc supports -c -o file.o... yes
checking if cc supports -c -o file.o... (cached) yes
checking whether the cc linker (/usr/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... no
configure: creating ./config.status
config.status: creating config.h
config.status: executing libtool commands
running: make
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=compile cc  -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -c /var/tmp/oci8/oci8.c -o oci8.lo
libtool: compile:  cc -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64 -DHAVE_CONFIG_H -g -O2 -c /var/tmp/oci8/oci8.c  -fPIC -DPIC -o .libs/oci8.o
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=compile cc  -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -c /var/tmp/oci8/oci8_lob.c -o oci8_lob.lo
libtool: compile:  cc -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64 -DHAVE_CONFIG_H -g -O2 -c /var/tmp/oci8/oci8_lob.c  -fPIC -DPIC -o .libs/oci8_lob.o
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=compile cc  -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -c /var/tmp/oci8/oci8_statement.c -o oci8_statement.lo
libtool: compile:  cc -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64 -DHAVE_CONFIG_H -g -O2 -c /var/tmp/oci8/oci8_statement.c  -fPIC -DPIC -o .libs/oci8_statement.o
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=compile cc  -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -c /var/tmp/oci8/oci8_collection.c -o oci8_collection.lo
libtool: compile:  cc -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64 -DHAVE_CONFIG_H -g -O2 -c /var/tmp/oci8/oci8_collection.c  -fPIC -DPIC -o .libs/oci8_collection.o
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=compile cc  -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -c /var/tmp/oci8/oci8_interface.c -o oci8_interface.lo
libtool: compile:  cc -I. -I/var/tmp/oci8 -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64 -DHAVE_CONFIG_H -g -O2 -c /var/tmp/oci8/oci8_interface.c  -fPIC -DPIC -o .libs/oci8_interface.o
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=link cc -DPHP_ATOM_INC -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/include -I/var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/main -I/var/tmp/oci8 -I/usr/include/php -I/usr/include/php/main -I/usr/include/php/TSRM -I/usr/include/php/Zend -I/usr/include/php/ext -I/usr/include/php/ext/date/lib -I/usr/include/oracle/12.1/client64  -DHAVE_CONFIG_H  -g -O2   -o oci8.la -export-dynamic -avoid-version -prefer-pic -module -rpath /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules  oci8.lo oci8_lob.lo oci8_statement.lo oci8_collection.lo oci8_interface.lo -Wl,-rpath,/usr/lib/oracle/12.1/client64/lib -L/usr/lib/oracle/12.1/client64/lib -lclntsh
libtool: link: cc -shared  .libs/oci8.o .libs/oci8_lob.o .libs/oci8_statement.o .libs/oci8_collection.o .libs/oci8_interface.o   -L/usr/lib/oracle/12.1/client64/lib -lclntsh  -Wl,-rpath -Wl,/usr/lib/oracle/12.1/client64/lib   -Wl,-soname -Wl,oci8.so -o .libs/oci8.so
libtool: link: ( cd ".libs" && rm -f "oci8.la" && ln -s "../oci8.la" "oci8.la" )
/bin/sh /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/libtool --mode=install cp ./oci8.la /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules
libtool: install: cp ./.libs/oci8.so /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules/oci8.so
libtool: install: cp ./.libs/oci8.lai /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules/oci8.la
libtool: finish: PATH="/usr/bin:/sbin:/bin:/usr/sbin:/usr/bin:/sbin" ldconfig -n /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules
----------------------------------------------------------------------
Libraries have been installed in:
   /var/tmp/pear-build-rootxyvVgY/oci8-2.0.10/modules

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the `LD_RUN_PATH' environment variable
     during linking
   - use the `-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to `/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------

Build complete.
Don't forget to run 'make test'.

running: make INSTALL_ROOT="/var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10" install
Installing shared extensions:     /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr/lib64/php/modules/
running: find "/var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10" | xargs ls -dils
1315063   4 drwxr-xr-x 3 root root   4096 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10
1315092   4 drwxr-xr-x 3 root root   4096 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr
1315093   4 drwxr-xr-x 3 root root   4096 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr/lib64
1315094   4 drwxr-xr-x 3 root root   4096 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr/lib64/php
1315095   4 drwxr-xr-x 2 root root   4096 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr/lib64/php/modules
1315091 476 -rwxr-xr-x 1 root root 484188 May 23 14:16 /var/tmp/pear-build-rootxyvVgY/install-oci8-2.0.10/usr/lib64/php/modules/oci8.so

Build process completed successfully
Installing '/usr/lib64/php/modules/oci8.so'
install ok: channel://pecl.php.net/oci8-2.0.10
configuration option "php_ini" is not set to php.ini location
You should add "extension=oci8.so" to php.ini
*/
```

##### Enable the PHP OCI8 Extension on Linux
* *OCI8 is the PHP extension for connecting to Oracle Database. OCI8 is open source and included with PHP. The name is derived from Oracle's C "call interface" API first introduced in version 8 of Oracle Database. OCI8 links with Oracle client libraries, such as Oracle Instant Client.*
* *Oracle Instant Client is a free set of easily installed libraries that allow programs to connect to local or remote Oracle Database instances. To use Instant Client an existing database is needed - Instant Client does not include one. Typically the database will be on another machine. If the database is local then Instant Client, although convenient and still usable, is generally not needed because OCI8 can directly use the database libraries.*
* *When using Instant Client 11g, PHP OCI8 connects to all editions of Oracle 9.2, 10.x, and 11.x databases.*
* http://www.oracle.com/technetwork/articles/dsl/technote-php-instant-084410.html

##### Connect to the XE service (i.e. database) on the "localhost" machine using Easy Connect syntax
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
