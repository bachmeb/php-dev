# Persistent Database Connections 

## References
* http://php.net/manual/en/features.persistent-connections.php

* *Persistent connections are links that do not close when the execution of your script ends. When a persistent connection is requested, PHP checks if there's already an identical persistent connection (that remained open from earlier) - and if it exists, it uses it. If it does not exist, it creates the link. An 'identical' connection is a connection that was opened to the same host, with the same username and the same password (where applicable).* (http://php.net/manual/en/features.persistent-connections.php)
