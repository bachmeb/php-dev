# debug php

## References
* http://www.eclipse.org/pdt/help/html/troubleshooting_remote_debugging.htm
* http://www.eclipse.org/pdt/help/html/setting_your_zend_studio_for_eclipse_to_be_an_allowed_host.htm
* https://www.zend.com/topics/Zend-Debugger-Installation-Guide.pdf
* http://www.eclipse.org/pdt/articles/debugger/os-php-eclipse-pdt-debug-pdf.pdf

##### 


##### Install Zend Debugger on the application server
```
sudo yum install php-ZendFramework2-Debug
```

##### Install PDT on your local machine
* [/docs/pdt](/docs/pdt.md)

##### Ensure the machine on which your PDT is installed is an allowed host for your debugger. 


	
To configure your debugger to allow your PDT to debug:
Open your php.ini file.
Edit the zend_debugger.allow_hosts parameters to include the IP address of the machine on which your PDT is installed.
e.g. zend_debugger.allow_hosts=127.0.0.1/32
Ensure the address is not in your zend_debugger.deny_hosts parameter list.
Set the Debug Server to expose itself to remote clients by setting the zend_debugger.expose_remotely parameter to Always.
(e.g. zend_debugger.expose_remotely=always).
Save the file.
Restart your Web server for the settings to take effect.


##### In PDT , configure your server according to the instructions under Adding Servers in the PHP Servers Preferences.
##### Ensure the correct settings are configured in your Debug Preferences and Installed Debuggers Preferences pages.
##### Ensure you have a dummy.php file in your remote server's document root.
