# debug php

## References
* http://www.eclipse.org/pdt/help/html/troubleshooting_remote_debugging.htm
* http://www.eclipse.org/pdt/help/html/setting_your_zend_studio_for_eclipse_to_be_an_allowed_host.htm
* https://www.zend.com/topics/Zend-Debugger-Installation-Guide.pdf
* http://www.eclipse.org/pdt/articles/debugger/os-php-eclipse-pdt-debug-pdf.pdf
* http://www.eclipse.org/pdt/help/html/php_servers.htm#Adding_servers

##### Install Zend Debugger on the application server
```
sudo yum install php-ZendFramework2-Debug
```

##### Install PDT on your local machine
* [/docs/pdt](/docs/pdt.md)

##### Add Zend to Available Software Sites
* Help
  * Install New Software
    * Click Add
      * Name: Zend
      * Location: http://downloads.zend.com/pdt
      * Click OK

##### Install Zend Debugger
* Help
  * Install New Software
    * Work with: Zend
    * Select available software
      * Name: Zend CE Features
        * Zend Debugger Feature
    * Click Next
    * Click Next
    * Agree to license terms
    * Click Finish
    * Restart Eclipse

##### Find php.ini on the application server
```
sudo find / -name php.ini
```

##### Open php.ini on the application server
```
sudo nano /etc/php.ini
```

##### Add a line to php.ini allowing your local machine to be a remote zend debugger
```
zend_debugger.allow_hosts=127.0.0.1/32
```

##### Ensure the address is not in the zend_debugger.deny_hosts parameter list

Add a line to php.ini to tell the Debug Server to expose itself to remote clients
```
zend_debugger.expose_remotely=always
```

##### Restart the Web server
```
sudo /sbin/service httpd status
sudo /sbin/service httpd restart
```

##### Add a PHP server in Eclipse
* Window > Preferences > PHP > Servers
 * Click New
  * Server Name: Whatever
  * Base URL: http://[web server address]
  * Document Root: 
  * Click Next
  * Debugger: Zend Debugger
  * Client IP(s)/Host: [auto-populated]
  * Port: 10137
  * Response Timeout (ms): 60000
  * Click Next
  * Path Mapping
  * Click Finish

##### Confirm the settings in PHP Debug Preferences
* Window > Preferences > PHP > Debug
 * PHP Server: pick one
 * Debugger: Zend debugger
 * CLI Settings: None Defined
 * Debugger: None Defined
 * Debug Transfer Encoding: UTF-8
 * Debug Output Encoding: UTF-8
 * Break at First Line: YES
 * Click OK

##### Confirm the settings in PHP Installed Debuggers
* Window > Preferences > PHP > Debug > Debuggers
 * Select Zend Debugger
 * Click Configure
  * Client Host/IP: Auto
  * Debug Port: 10137
  * Debug Response Timeout (ms): 60000
  * Broadcast Port: 20080
  * Dummy File Name: dummy.php

##### Create dummy.php in the document root of the web server
```
cat /etc/httpd/conf/httpd.conf | grep DocumentRoot
cd /var/www/html
touch dummy.php
```

