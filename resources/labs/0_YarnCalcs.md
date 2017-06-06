# Notes on the spreadsheet

## Based on the assumption
Ten workers nodes
- Twenty vcores
- 128 GB RAM
- Twelve disks for DataNode use

### Notes
#### OS Memory: 12,8 GB, might be a lot.
- This is 10% of the total worker ram, but depending on the amount of ram in the worker, this can be scaled down.
- It is also dependant on the software the client wants to run on the worker nodes. (monitoring software for example)
- In this case, we might use a less aggressive value of 7,5% which amounts to about 10 GB, this will give more memory for YARN resources

#### mapreduce.map.memory.mb
- Depending on the workload and the concurrent jobs that we can run on a server we might increase the map memory.

#### mapreduce.reduce.memory.mb
- Depending on the workload and the concurrent jobs that we can run on a server we might increase the reduce memory.

## Based on the SEBC cluster
Four workers
- Four Cores
- 15 GB RAM
- One Disk for DN use

### Notes
#### OS vCores: decreased to 1
Because the machine will only run the OS, this should be sufficient

#### CM Agent and DataNode vCores: decreased to 0
The CM Agent, DataNode and NodeManager can share a vCore due to lack of cores in the nodes

#### mapreduce.map.memory.mb = 2048
Since we are limited to concurrent jobs due to vCore limitations, I could increase the map memory to and still be within the 2 jobs.

#### mapreduce.reduce.memory.mb = 2048
Since we are limited to concurrent jobs due to vCore limitations, I could increase the reduce memory to and still be within the 2 jobs.


## What criteria affects workload factor? What does a value of 1, 2, or 4 signify
- The workload is dependant on how much we want to stress the workers. We can increase the work load to have more map / reduce jobs available on each machine.

! We cannot increase the workload indefinately however, in the example of the 10 workers, if we set the workload from 2 to 4, there is no change as long as the number of available vCores for YARN stays 15. As we cannot have more jobs running than our vCores in this case can handle.
The 15 vCores can handle 15 jobs at once as the mapreduce.map.cpu.vcores is 1.

Should we double the number of vCores per container to 2, then the amount of simultanious jobs would be cut in 2, being 7,5, so actually 7, no matter the workload of the nodes.

The same for the memory, if we would increase the mapreduce.map.memory.mb to 8GB, this would mean that we can maximally have 14 concurrent jobs.