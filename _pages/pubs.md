---
permalink: /
title: "Publications"
author_profile: true
redirect_from: 
  - /pubs.html
  - /pubs/
---

## ParBFT: Faster Asynchronous BFT Consensus with a Parallel Optimistic Path
* Accepted by CCS 2023
* Authors: Xiaohai Dai, Bolin Zhang, Hai Jin, Ling Ren
* Available on \[[ACM DL](https://dl.acm.org/doi/10.1145/3576915.3623101)\]
### Abstract
To reduce latency and communication overhead of asynchronous Byzantine Fault Tolerance (BFT) consensus, an optimistic path is often added, with Ditto and BDT as state-of-the-art representatives. These protocols first attempt to run an optimistic path that is typically adapted from partially-synchronous BFT and promises good performance in good situations.  If the optimistic path fails to make progress, these protocols switch to a pessimistic path after a timeout, to guarantee liveness in an asynchronous network. This design crucially relies on an accurate estimation of the network delay Δ to set the timeout parameter correctly. A wrong estimation of Δ can lead to either premature or delayed switching to the pessimistic path, hurting the protocol's efficiency in both cases.<br><br>
To address the above issue, we propose ParBFT, which employs a parallel optimistic path. As long as the leader of the optimistic path is non-faulty, ParBFT ensures low latency without requiring an accurate estimation of the network delay. We propose two variants of ParBFT, namely ParBFT1 and ParBFT2, with a trade-off between latency and communication. ParBFT1 simultaneously launches the two paths, achieves lower latency under a faulty leader, but has a quadratic message complexity even in good situations. ParBFT2 reduces the message complexity in good situations by delaying the pessimistic path, at the cost of a higher latency under a faulty leader. Experimental results demonstrate that ParBFT outperforms Ditto or BDT. In particular, when the network condition is bad, ParBFT can reach consensus through the optimistic path, while Ditto and BDT suffer from path switching and have to make progress using the pessimistic path.
### Figures
![parbft](/files/par.jpg)
