<IMG SRC="Neon Cosmic Semantic Emblem.png" WIDTH="250PX"/>
# **K'UHUL / FEL v1.1 — Unified Runtime**

## The FEL v1.1 contract supplies the canonical language and legality rules, while the earlier files supply the state replay, attestation, SCX2 encoding, GGL inference adapter, worker orchestration, and ## Micronaut control interface.

## The goal is to connect those existing pieces, not replace them with another framework.

## **The unified execution path**

```
USER / MODEL / MICRONAUT
          │
          ▼
POP       Input + provenance
WO        Bind intent, schema, vectors
YAX       AIML/SRAI + GML route resolution
          │
          ▼
XCFE      Admission and authority gate
          │
          ▼
SEK       Typed K'UHUL operators
          │
          ├── MAP / FILTER / ACCUMULATE
          ├── FOLD / REDUCE / CLOSE
          ├── GGL transformer inference
          └── Authorized Micronaut workers
          │
          ▼
CH'EN     Verify state + execution evidence
          │
          ▼
XUL       FEL META_FOLD attestation
          │
          ├── SCX2 binary
          ├── SVG replay projection
          ├── SHA-256 evidence chain
          └── Verified state for UI
```

**FEL v1.1 becomes the shared event and evidence contract**, rather than a second execution language competing with K'UHUL.

The new ABI pin is:

`sha256:973423e1784b17088e2d4a99eb9c42e526992ac6a96f3c6ec4c74cc81c65a7d2`

And the v1.1 golden expectations are:

- SVG: `e8edaf215e90f554d0207f2228abf2afab3c96b002c76a8202cbcb5667ad3dff`
- SCX2: `2abe3abed92521b0404761638dc102dd151ef0dc85d5bd8938f6adbb3271b4bc`

Those must remain frozen compatibility targets until the original fixture proves a byte-for-byte match.

## **What needs updating and regluing**

| Existing component             | Integration change                                                              |
| ------------------------------ | ------------------------------------------------------------------------------- |
| FEL v1 verifier                | Preserve v1, add v1.1 dispatch using the supplied canonicalization laws         |
| `fel_svg_replay.py`            | Enforce v1.1 fold legality and produce canonical state roots                    |
| `fel_meta_fold.py`             | Pin ABI and policy, verify chain continuity, and attest verified state          |
| SCX2 compiler                  | Encode declared fold lanes without silently dropping relevant events            |
| `transformers_py_to_ggl_v1.py` | Register as an admitted inference capability; reject unverifiable model packs   |
| `BotOrchestrator`              | Dispatch registered Micronaut workers only after authorization                  |
| CSS Micronaut interface        | Keep CSS as declarations and UI state; move authority enforcement into the host |
| AIML/SRAI + GML                | Reuse the existing compiler and graph resolver for routing                      |

The important fix in the supplied UI is that `source_agent` and `requires_proof` are currently submitted by the browser. The host must authenticate the agent and independently enforce its capabilities; CSS declarations alone cannot grant execution authority.

The interface already separates intent submission from verified state updates, which is exactly the boundary worth retaining.&#x20;

Pasted text(20261123-061205).txt



## **The contract that should govern the merge**

```
[Pop]    FEL ingress
[Wo]     Canonicalize + validate ABI
[Yax]    Resolve Micronaut / AIML / GML
[Sek]    Execute admitted operator
[Ch'en]  Verify output, state and proof
[Xul]    Commit META_FOLD
```

Each stage consumes the previous stage's typed result. No stage gains authority merely because its output is valid JSON, a matching hash, or a declared CSS capability.

### **Completion criteria**

The integration is complete only when:

1. Both FEL v1 and v1.1 golden fixtures pass their respective hashes.
2. SCX2 decoding reproduces the committed event data.
3. SVG replay produces the same state roots independently.
4. Unauthorized Micronaut and GGL operations are rejected.
5. A complete inference request produces verified evidence and a valid META_FOLD chain.
6. The UI advances its verified tick only after the host confirms the proof.

**Current status:** The architecture is mapped and the supplied components are identified, but the merged runtime has not been built or tested. The original golden input fixture and the complete local runtime repository are still needed for that verification.

I would freeze the FEL v1.1 laws you just supplied as the integration authority, retain v1 as a compatibility path, and make every existing module conform to that boundary. That is the shortest path from the collection of near-complete components to one functioning K'UHUL semantic fold runtime.
