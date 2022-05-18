This centos8 vm example will by default create 3 VMs.

- dbd		- intended to be the slurmdbd and mysql host
- ctld		- the slurmctld
- node0		- The first node.

Compute nodes by default have 2 numa nodes.

You can create more compute nodes by setting the SLURMD_NODE_CNT environment
variable.
