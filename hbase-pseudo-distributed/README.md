## hbase-pseudo-distributed
Hbase 1.2.3 with hadoop 2.7.3 in pseudo-distributed mode with Oracle Java 8

[![](https://images.microbadger.com/badges/image/sergeygals/hbase-pseudo-distributed.svg)](https://microbadger.com/images/sergeygals/hbase-pseudo-distributed "Get your own image badge on microbadger.com")

### Run
```
docker run --rm sergeygalkin/hbase-pseudo-distributed:0.1
```

### Connect to running container
```
docker exec -i -t $(docker ps | grep 'sergeygalkin/hbase-pseudo-distributed:0.1' | awk '{print $1}') /bin/bash
```

