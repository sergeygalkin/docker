## sysbench 
[Sysbench](https://github.com/akopytov/sysbench) 1.0 in Ubuntu 16.4
Using for [Open Stack performance testing](http://docs.openstack.org/developer/performance-docs)

[![](https://images.microbadger.com/badges/image/sergeygals/sysbench.svg)](https://microbadger.com/images/sergeygals/sysbench "Get your own image badge on microbadger.com")

### Preparitons:

#### Create DB for sysbench
```
CREATE USER 'sbtest'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'sbtest'@'%' WITH GRANT OPTION;
create database sbtest;
```

#### Example for prepare and run:
```
docker run --rm -it  sergeygals/sysbench:1.0 /opt/sysbench/bin/sysbench --test=oltp --num-threads=20  --mysql-host=10.1.1.2 prepare
docker run --rm -it  sergeygals/sysbench:1.0 /opt/sysbench/bin/sysbench --test=oltp --num-threads=20  --mysql-host=10.1.1.2 run
```
