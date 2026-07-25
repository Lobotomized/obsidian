[[Lenka]]

1.Primary Node: that takes all the writes. It records all changes in an operation log called oplog.
2.  Secondary Nodes: Continuously replicate the oplog and do the operations within it . You can also use them for read requests if you want.
3. Arbiter Empty node that acts as a tie breaker if you have even number of nodes


# Fail over handling
Members constantly ping each other to make sure they are alive. If the Primary node does not respond it is considered dead and an election occurs. The secondary node with the most recent oplog is chosen as the new Primary.