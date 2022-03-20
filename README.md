# akka-reservations-mechanisms


## Motivation
Sometimes convergence is not enough. Sometimes, even if we ensure convergence with CRDTs, the invariants of application are not preserved under weak consistency.

Welcome Invariant preserving CRDTs (BoundedCounter, Multi-level lock)

 * Provide invariants on datatype level.
 * Replicas can trade their shares of the value but cannot touch other's share.

Key ideas:
 * Operations execute locally without coordination most of the time.
 * Successful operations guarante to maintain the invariants.
 * When no units are available on a local replica, it fetches from remote replica.
 * Proactive reservation mechanisms transfer resources in the background to guarantee low latency for majority of operations.
 
