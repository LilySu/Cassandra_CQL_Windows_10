#### When Following [This Video](https://www.youtube.com/watch?v=EEXtVn3zAqc&ab_channel=jumpstartCS)
Install Javas 8U251 instead of the latest 8U261

#### When There are Multiple Versions of Python and cqlsh to Execute with Python 2
- Prereq: Download Python 2.7
1. Rename C:/Python27/python.exe to C:/Python27/python2.exe
2. Run `python2 -m cqlsh` in C:/Program Files/apache-cassandra-3.11.8/bin


#### In Cassandra Shell Running cqlsh
`CREATE KEYSPACE test_keyspace WITH replication = {'class':'SimpleStrategy','replication_factor':'1'} AND durable_writes = 'true';`
- specify name of keyspace
- specify settings - set replication factor for # nodes to replicate in cluster, ie copied 3 times would be 3
- specify replication class - a one-node cluster is 'SimpleStrategy'
- set if we want durable writes - default to true, false increases speed of writes and also increases data loss.