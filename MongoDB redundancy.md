[[Lenka]]

1.Primary Node that takes all the writes
2. One or more secondary dbs that can take the reads.
3. Arbiter Empty node that acts as a tie breaker if you have even number of nodes

Members constantly ping each other to make sure they are alive. If the Primary node does not respond it is considered dead and an election occures. 