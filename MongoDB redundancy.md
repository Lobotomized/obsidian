[[Lenka]]

1.Primary Node: that takes all the writes. It records all changes in an operation log called oplog.
2.  Secondary Nodes: Continuously replicate the oplog and do the operations within it . You can also use them for read requests if you want.
3. Arbiter Empty node that acts as a tie breaker if you have even number of nodes


# Fail over handling
Members constantly ping each other to make sure they are alive. If the Primary node does not respond it is considered dead and an election occurs. The secondary node with the most recent oplog is chosen as the new Primary.

***Writes:***  You have a choice between speed and reliability

If you want guarantees that your writes are safe, you can consider them successful only if the oplog is replicated  to one or one or more secondary nodes.
If you want speed you can consider them successful after the Primary log executes the commands.


***Reads:*** You have a choice between consistency and efficiency. If you allow reads to Secondary nodes you might give different data to users, but it will allow you to deal with higher volume of data.