# Useful dockers container
## sysbench 
[Sysbench](https://github.com/akopytov/sysbench) 1.0 in Ubuntu 16.4
Using for [Open Stack performance testing](http://docs.openstack.org/developer/performance-docs)

[![](https://images.microbadger.com/badges/image/sergeygals/sysbench.svg)](https://microbadger.com/images/sergeygals/sysbench "Get your own image badge on microbadger.com")

###Preparitons:

####Create DB for sysbench
```
CREATE USER 'sbtest'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'sbtest'@'%' WITH GRANT OPTION;
create database sbtest;
```

####Example for prepare and run:
```
docker run --rm -it  sergeygals/sysbench:1.0 /opt/sysbench/bin/sysbench --test=oltp --num-threads=20  --mysql-host=10.1.1.2 prepare
docker run --rm -it  sergeygals/sysbench:1.0 /opt/sysbench/bin/sysbench --test=oltp --num-threads=20  --mysql-host=10.1.1.2 run
```

## hadoop-pseudo-distributed
Hbase 1.2.3 with hadoop 2.7.3 in pseudo-distributed mode

[![](https://images.microbadger.com/badges/image/sergeygals/hadoop-pseudo-distributed.svg)](https://microbadger.com/images/sergeygals/hadoop-pseudo-distributed "Get your own image badge on microbadger.com")

### Run
docker run --rm sergeygalkin/hbase-pseudo-distributed:0.1

### Connect to running container
docker exec -i -t $(docker ps | grep 'sergeygalkin/hbase-pseudo-distributed:0.1' | awk '{print $1}')   /bin/bash

