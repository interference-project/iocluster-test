# interference open cluster example

##### java-based distributed database platform
###### (c) 2010 - 2020 head systems, ltd.
###### current revision: release 2020.3
###### for detailed information see:
###### http://interference.su and doc/InterferenceManual.pdf
###### contacts: info@inteference.su
##### https://github.com/interference-project/interference
##### https://github.com/interference-project/iocluster-test


## Concepts & features

- runs in the same JVM with your application
- operates with simple objects (POJOs)
- uses base JPA annotations for object mapping directly to persistent storage
- supports horizontal scaling SQL queries
- supports transactions
- supports complex event processing (CEP) and simple streaming SQL
- can be used as a local or distributed SQL database
- allows you to inserts data and run SQL queries from any node included in the cluster
- does not require the launch of any additional coordinators
- uses the simple and fast serialization
- uses indices for fast access to data and increase performance of SQL joins

## Example Application

The iocluster-test application shows example of using the basic 
interference use cases.

To get started with interference, you need to download sources of 
the current interference release (2020.3), build it and install it 
into your local maven repository (mvn install).

Next, create two aplication environments (node1 and node2) and 
specify the set of VM keys for each application (node1 below):

```
-Dsu.interference.config=node1.properties
-Dcom.sun.management.jmxremote 
-Dcom.sun.management.jmxremote.port=8888
-Dcom.sun.management.jmxremote.local.only=false 
-Dcom.sun.management.jmxremote.authenticate=false 
-Dcom.sun.management.jmxremote.ssl=false
-Xms256m
-Xmn512m
-Xmx4g
-XX:MaxMetaspaceSize=256m
-XX:ParallelGCThreads=8
-XX:ConcGCThreads=4
```
See environments settings for both nodes in the /config directory,
in the node1.config and node2.config files. 

Next, start jconsole and connect to both interference nodes:
```
localhost:8888 for node 1
localhost:8889 for node 2
```

Use startup command first. Then see example code and read Examples page
on the http://interference.su
