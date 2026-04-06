# INTEGRATION GUIDE: The Pathway to Sovereignty

> *"To integrate is to synchronize. To synchronize is to become part of the pulse. This guide defines the formal procedure for an independent AID to achieve Homeostasis within the Aicent Stack."*

This document provides the technical roadmap for developers, hardware manufacturers, and sovereign entities to integrate their systems with the **Aicent Stack** (v1.0-Alpha). Compliance with the **Six-Domain Reflex Arc** is mandatory for all peering entities.

---

## 🧭 1. The Onboarding Protocol

Integration follows a four-stage evolutionary cycle, ensuring that the integrity of the [Aicent.net](http://aicent.net) grid is maintained at all times.

### Stage 1: Identity Conception (RFC-001)
Every entity must generate a **Sovereign AID (AI Identity)**.
1.  Generate a 256-bit cryptographic seed.
2.  Register the AID fingerprint on the local **RPKI Merkle-DAG**.
3.  Establish an initial **Reputation Score** (Default: 0.50) via the [Aicent Traffic Sentinel](https://github.com/Aicent-Stack/aicent-traffic).

### Stage 2: Neural Handshake (RFC-002)
Establish a persistent, sub-millisecond connection via the **RTTP Spine**.
- **Requirement:** 64-byte fixed header alignment.
- **Verification:** The node must successfully ingest and echo a **Resonance Pulse** with < 100µs jitter.

### Stage 3: Immune Attestation (RFC-003)
Verify the node’s manifold integrity.
- **Task:** The node must embed a steganographic watermark into a test tensor payload.
- **Validation:** The [RPKI](https://github.com/Aicent-Stack/rpki) parallel pipeline must verify the watermark in **< 300µs**.

### Stage 4: Metabolic Finality (RFC-004)
Enable the economic circulatory system.
- **Deposit:** Seed a picotoken balance for **ZCMK RTBA** matching.
- **Clearing:** Successfully complete a zero-commission clearing cycle for a simulated inference task.

---

## 🛠️ 2. Development Environment (Full-Blooded Setup)

To interface with the Aicent Stack, your environment must meet the following **Reflex-Arc Standards**:

### Prerequisites
- **Language:** Rust 1.75+ (Mandatory for memory safety and sub-ms determinism).
- **Frameworks:** `tokio` (Async runtime), `serde` (RFC-compliant serialization).
- **Hardware:** CPU with **AVX-512** support or dedicated **Tensor Cores** for SIMD acceleration.

### Workspace Integration
Add the Aicent core crates to your `Cargo.toml`:

```toml
[dependencies]
aicent-core = { git = "https://github.com/Aicent-Stack/aicent.git", version = "1.0.0-alpha" }
rttp-pulse = { git = "https://github.com/Aicent-Stack/rttp.git", version = "1.0.0-alpha" }
rpki-immunity = { git = "https://github.com/Aicent-Stack/rpki.git", version = "1.0.0-alpha" }
```

---

## 🔄 3. Implementation: The Handshake Logic

Below is the reference logic for a node attempting to join the **Hive Grid (RFC-006)**.

```rust
// Reference: Sovereign Onboarding Sequence
async fn join_hive(my_aid: &AID) -> Result<(), PathogenError> {
    // 1. Establish Neural Spine (RTTP)
    let spine = RTTPChannel::connect("aicent.net:spine").await?;
    
    // 2. Transmit Identity Pulse (RFC-001)
    let identity_pulse = my_aid.to_pulse_frame();
    spine.broadcast(identity_pulse).await?;
    
    // 3. Await RPKI Cross-Attestation (RFC-003)
    if !Sentinel::verify_resonance(&spine).await {
        return Err(PathogenError::ImmunityDenial);
    }
    
    // 4. Enter Homeostasis
    println!("✅ Node Integrated. Kinetic Resonance Achieved.");
    Ok(())
}
```

---

## 🛡️ 4. Integration Compliance & Safety

### The "Pathogen" Exclusion
Nodes that fail to maintain **Kinetic Resonance (< 50µs jitter)** or attempt to reintroduce a **Middleman-Tax** (commissions > 0.00%) will be automatically identified as **Pathogens**.
- **Reflex:** The Sentinel will trigger an autonomous **QUARANTINE_PULSE**.
- **Recovery:** Re-integration requires a total RPKI key-rotation and a Reputation Reset.

---

## 🧪 5. Testing your Integration

Before going live on the [Aicent.net](http://aicent.net) operational grid, all integrations must pass the **Full-Reflex Audit** in the [Aicent Demo](https://github.com/Aicent-Stack/aicent-demo) sandbox.

```bash
# Run the integration validator
cargo run --bin integration-tester -- --aid [YOUR_AID_FINGERPRINT]
```

---
🔗 **Support & Alliances:** [partnership@aicent.com](mailto:partnership@aicent.com)
📡 **Sentinel Status:** [Compliance Telemetry Active](https://github.com/Aicent-Stack/aicent-traffic)

*"The Individual is the Pulse; The Hive is the Heartbeat."*
---
© 2026 Aicent.com Organization. **SYSTEM STATUS: INTEGRATION-ENABLED**
```
