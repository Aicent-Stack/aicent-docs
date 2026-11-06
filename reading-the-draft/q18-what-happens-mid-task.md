# What happens mid-task: the lease is the halt | Aicent Stack

28 Oct 2026 · [Read the full article](https://blog.aicent.com/q18-what-happens-mid-task/) · [Chinese version](https://blog.aicent.com/zh/q18-what-happens-mid-task/)

The design rule of No. 17 met its boundary case the same day: what does a closed refusal vocabulary say to a chain that started inside its lease window and is still executing after the window has closed? Reading the Draft series, No. 18: nothing needs to be added, because the wire already carries the answer — the verification answer states its own lease_expiry, so a runtime has held its deadline since the first answer; the window is the revocation-latency bound; and the physical act of halting stays with the calling layer. The interpreter ranks, the clock bounds, and neither a model nor a mandate can extend the lease.
