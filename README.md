# akka-reservations-mechanisms


## Motivation
Sometimes convergence is not enough. Sometimes, even if we ensure convergence with CRDTs, the invariants of applications are not preserved under weak consistency.

Welcome Invariant Preserving CRDTs (BoundedCounter, Multi-level lock)

 * They provide invariants on datatype level.
 * Replicas can trade their units of the value but cannot touch other's share.

Key ideas:
 * Operations are executed locally without coordination most of the time.
 * Successful operations guarantee the invariants to be maintained.
 * When no units are available on the local replica, the algorithm fetches them from a remote replica.
 * Proactive reservation mechanisms transfer resources in the background to guarantee low latency for the majority of operations.
