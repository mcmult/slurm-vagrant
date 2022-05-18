This centos8 vm example will by default create 3 VMs.

- dbd	- intended to be the slurmdbd and mysql host
- ctld	- the slurmctld
- node0	- The first node.

Compute nodes by default have 2 numa nodes.

You can create more compute nodes by setting the SLURMD_NODE_CNT environment
variable.  Note that it will either need to be in your bashrc, or set before
most commands.  If not, you could bring up 6 nodes, but only destroy the dbd,
ctld, and node0.
