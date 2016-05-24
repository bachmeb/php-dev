# Persistent Database Connections 

## References
* http://php.net/manual/en/features.persistent-connections.php

##### What are persistent connections?
* *Persistent connections are links that do not close when the execution of your script ends. When a persistent connection is requested, PHP checks if there's already an identical persistent connection (that remained open from earlier) - and if it exists, it uses it. If it does not exist, it creates the link. An 'identical' connection is a connection that was opened to the same host, with the same username and the same password (where applicable).* (http://php.net/manual/en/features.persistent-connections.php)

##### How does a web server utilize PHP to generate web pages?
* *There are three ways in which your web server can utilize PHP to generate web pages.*
* *The first method is to use PHP as a CGI "wrapper". When run this way, an instance of the PHP interpreter is created and destroyed for every page request (for a PHP page) to your web server. Because it is destroyed after every request, any resources that it acquires (such as a link to an SQL database server) are closed when it is destroyed. In this case, you do not gain anything from trying to use persistent connections -- they simply don't persist.*
* *The second, and most popular, method is to run PHP as a module in a multiprocess web server, which currently only includes Apache. A multiprocess server typically has one process (the parent) which coordinates a set of processes (its children) who actually do the work of serving up web pages. When a request comes in from a client, it is handed off to one of the children that is not already serving another client. This means that when the same client makes a second request to the server, it may be served by a different child process than the first time. When opening a persistent connection, every following page requesting SQL services can reuse the same established connection to the SQL server.*
* *The last method is to use PHP as a plug-in for a multithreaded web server. Currently PHP 4 has support for ISAPI, WSAPI, and NSAPI (on Windows), which all allow PHP to be used as a plug-in on multithreaded servers like Netscape FastTrack (iPlanet), Microsoft's Internet Information Server (IIS), and O'Reilly's WebSite Pro. The behavior is essentially the same as for the multiprocess model described before.*

##### What persistent connection good for?
* *Efficiency.*
* *Persistent connections are good if the overhead to create a link to your SQL server is high.*
* *The bottom line is that if that connection overhead is high, persistent connections help you considerably.*
* *They cause the child process to simply connect only once for its entire lifespan, instead of every time it processes a page that requires connecting to the SQL server.*
* *This means that for every child that opened a persistent connection will have its own open persistent connection to the server.*
* *For example, if you had 20 different child processes that ran a script that made a persistent connection to your SQL server, you'd have 20 different connections to the SQL server, one from each child.*
