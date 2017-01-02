created from [vyshane/cassandra-kubernetes](https://github.com/vyshane/cassandra-kubernetes)

#Cassandra on Kubernetes

###START HERE
```
kubectl create -f cassandra-peer-service.yml
kubectl create -f cassandra-service.yml
kubectl create -f cassandra-replication-controller.yml
```
done.

-------

###to scale up

```
kubectl scale rc cassandra --replicas=3
```

###to cqlsh

```
kubectl exec <CASSANDRA POD NAME> -i -t -- bash -il
```

```
CREATE KEYSPACE mytest WITH replication = {'class': 'SimpleStrategy' , 'replication_factor': 3};
```

```
CREATE TABLE mytest.test1 ( one text primary KEY , two text);
```

```
INSERT INTO mytest.test1 (one, two ) VALUES ( 'a', 'b');
```

