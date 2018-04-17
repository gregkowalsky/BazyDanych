# Projects

1. Setup a Master-Slave replication cluster in MySQL that will 
allow you to scale read operations beyond the current limit that 
you can discover using code from previous assignment. Verify performance.

2. Setup a multi-master replication that will allow you to scale write
operations beyond the current limit that you can discover using code
from previous assignment. Verify the performance.

3. Setup a redis instance and try to replicate the scenario from previous
assignment in redis. You can use redis' different data structure, e.g. hash 
fields to store data regarding users. Verify the performance.

4. Setup a MongoDB instance and try to replicate the scenario from previous
assignment in MongoDB. Remember **not** to use relations! Verify performance.

5. Setup a RocksDB cluster and try to replicate the scenario from previous 
assignment. Verify the performance.

6. Using Redis and it's publish/subscribe mechanism create a dataplane that
will allow separate services conneted via the subscribe mechanism to execute
specific tasks when incoming video rentals appear (via publish) in the system.

