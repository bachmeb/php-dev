# hello

## References
* http://php.net/manual/en/tutorial.firstpage.php

##### Install Apache HTTPD 

##### Install PHP

##### Start httpd

##### Create a new file in the document root of the web server
```
nano /var/www/html/hello.php
```

##### Add markup language to the php file
```html
<html>
 <head>
  <title>PHP Test</title>
 </head>
 <body>
 <?php echo '<p>Hello World</p>'; ?> 
 </body>
</html>
```

##### Visit the php page
* http://localhost/hello.php
