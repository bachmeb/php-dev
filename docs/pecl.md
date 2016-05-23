# pecl

* *PECL is a repository of PHP extensions that are made available to you via the » PEAR packaging system.* (http://au2.php.net/manual/en/install.pecl.intro.php)

## References
* http://au2.php.net/manual/en/install.pecl.php
* http://au2.php.net/manual/en/install.pecl.intro.php
* https://moodle.org/mod/forum/discuss.php?d=324931
* http://board.phpbuilder.com/showthread.php?10339128-RESOLVED-pecl-install-phpize-failed


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
