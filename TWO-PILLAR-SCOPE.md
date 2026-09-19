# V1.2.6 — the two-pillar protocol, split out from the Aicent Stack line

**Purpose of this document.** It states, in one place, what `V1.2.6` is, what it is *not*,
and how the two versions named in this organisation's material relate to each other. It is
written for anyone who arrives at this organisation's repositories or registrations and
needs to know which line a given document, number or claim belongs to.

**Audience.** Standards reviewers, package users, and contributors. It is deliberately
plain: no vision language, no performance claims.

---

## 1. The two-pillar protocol

`V1.2.6` is dedicated to exactly two URI schemes, submitted for Provisional
registration under RFC 7595:

| Pillar | Scheme | What the URI names | Specification |
| :--- | :--- | :--- | :--- |
| **Intent addressing** | `rttp` | a claim of intent directed at an identified subject | [RFC-002](https://rttp.com/RFC-002/) |
| **Citable standing (attestation)** | `iqa` | the attestation standing of a subject, as reported by a named organ | [RFC-009](https://iqa.org/RFC-009/) |

The two schemes are **two halves of one addressing model**:

* both use a three-segment authority, `<subject>.<organ>.<root>`, with an optional action
  path;
* both are restricted to lowercase US-ASCII and define no `userinfo`, port, query or
  fragment;
* neither resolves names through the DNS, and neither consults a registry at resolution
  time — the address is computed from the authority.

They are therefore resolved at the same layer and are intended to be encodable at the same
cost. Repositories: [`Aicent-Stack/rttp`](https://github.com/Aicent-Stack/rttp) ·
[`Aicent-Stack/iqa-org`](https://github.com/Aicent-Stack/iqa-org).

## 2. The lineage split

| Line | What it is | Where it lives | Version markers you will see |
| :--- | :--- | :--- | :--- |
| **Aicent Stack line** | The narrative, multi-pillar material, and the public code that accompanies it | This `aicent-docs` repository and the other pillar repositories | **up to `V1.2.5`**; later narrative revisions carry their own `V1.3.0` markers |
| **Two-pillar line (this one)** | The two URI schemes and their reference implementations | `rttp` · `iqa-org` · the two specifications · the two sites | **`V1.2.6`** |

**The rule, stated plainly:** the Aicent Stack's narrative and public code are published
**up to `V1.2.5`**. **`V1.2.6` is split out from that line and belongs to the two-pillar
protocol.** Anything carrying a different version marker is a different line and is not
part of the schemes.

**Why the split exists.** Registering a URI scheme requires a specification that stands on
its own and a description that a standards reviewer can check line by line. Material about
other pillars, private engine paths, or measurements taken on other builds cannot be
submitted, and mixing it into a scheme description would make the description
unverifiable. The split keeps the reviewable thing reviewable.

## 3. In scope for `V1.2.6`

* The `rttp` scheme: syntax, exclusions, default operation, client requirements.
* The `iqa` scheme: syntax, the closed sets (`organ`, `action`), action safety classes,
  the naming note.
* The attestation envelope format as specified in RFC-009.
* The published conformance vectors and the three reference implementations (Rust, Python,
  JavaScript) that replay them.
* The two IANA registration requests.

## 4. Explicitly out of scope for `V1.2.6`

| Not part of these schemes | Why it is called out |
| :--- | :--- |
| A transport layer or a client implementation | The schemes define addressing only; no transport is defined or shipped |
| The other pillars and their protocols | Different line (see §2) |
| Performance figures of any kind | The schemes make no latency, throughput or scale claim; the vectors test agreement, not speed |
| Private or unpublished engine paths | Not inspectable, therefore not part of a reviewable specification |
| Staking, vitality, or quality-scoring machinery | No implementation exists in these schemes |
| Deployment size, adoption or node counts | No verified figure exists; none is claimed |
| The DNS, key directories, or any lookup service | Resolution is a computation; a lookup would contradict the model |

## 5. The two names and the registration process

| | `rttp` | `iqa` |
| :--- | :--- | :--- |
| IANA ticket | `#1459939` | `#1459963` |
| Status requested | Provisional (RFC 7595) | Provisional (RFC 7595) |
| Naming | the name review passed | the name is still under review |
| CRI scheme number | `0–999` requested, under review | `0–999` requested, under review |
| State | **submitted · under review — not registered** | **submitted · under review — not registered** |

**A ticket number is not a registration.** As of 2026-09-19 the IANA "URI Schemes" registry
contains no entry for either name. Never describe either scheme as *registered*,
*standardised* or *approved*; the accurate description is *submitted, Provisional, under
review*.

`iqa` here denotes **Identity Quality Assurance**. It is not *Image Quality Assessment* and
it is not affiliated with the historical UK *Institute of Quality Assurance*.

## 6. Which number means what

| Number | Meaning |
| :--- | :--- |
| **`V1.2.6`** (also written `v1.2.6`) | The **stack / specification revision** carried by these two schemes and their sites |
| `1.2.6` · `1.2.7` | **Package** versions on PyPI and npm |
| `1.2.6-alpha` | **Package** version on crates.io — every published crate version is a pre-release |

Current package versions:

| Package | Registry | Version |
| :--- | :--- | :--- |
| `rttp` | PyPI · npm | `1.2.6` |
| `rttp` | crates.io | `1.2.6-alpha` |
| `iqa-org` (PyPI) · `@aicent/iqa` (npm) | PyPI · npm | `1.2.7` |
| `iqa-org` | crates.io | `1.2.6-alpha` |

The stack version and the package versions move on separate axes: a package version changes
when the package is republished (which, for a correction, requires a new number), while the
stack version changes only when the specification revision changes. On the sites, the stack
version appears in the page identity and the package versions appear only in the install
and verification sections.

## 7. Where things live

| Artifact | Location |
| :--- | :--- |
| `rttp` scheme, specification material, Rust crate | <https://github.com/Aicent-Stack/rttp> · <https://rttp.com/RFC-002/> |
| `iqa` scheme, specification material, Rust crate | <https://github.com/Aicent-Stack/iqa-org> · <https://iqa.org/RFC-009/> |
| Reference sites | <https://rttp.com/> · <https://iqa.org/> |
| Conformance vectors | shipped inside every package; `sha256 b28de8c7…` (`rttp`) · `sha256 9ec8d9b1…` (`iqa`) |
| Registration tickets | IANA `#1459939` (`rttp`) · `#1459963` (`iqa`) — Provisional requests, submitted and under review |

## 8. Citation rules

1. **Name the source.** Quote from *this repository* or from *the specification sites* —
   and say which. Two copies of the same filename can differ.
2. **Do not move numbers between lines.** A figure, badge or slogan belonging to the
   Aicent Stack line is not a statement about `rttp` or `iqa`.
3. **Never claim more than the registry does.** *Submitted, Provisional, under review.*
4. **Quote vectors by hash**, not by description: `sha256 b28de8c7…` /
   `sha256 9ec8d9b1…`.
5. **A passing conformance run means agreement, not performance.**

---

*Revision of this document: 2026-09-19. It is a scope statement for the two-pillar line; it
is not a specification, and it adds no requirement to either scheme. The specifications
themselves are RFC-002 and RFC-009.*
