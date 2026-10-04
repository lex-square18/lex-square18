# Public architecture baseline for Progetto ATLAS

**Publication status: VERIFIED**

This note describes the public, sanitized baseline currently guiding Progetto ATLAS. It is intentionally architectural. It contains no production credentials, no real financial data, no supplier conditions, no customer or employee data, and no production topology.

## Why ATLAS exists

ATLAS is being built to turn fragmented operational data into reliable information, controls, procedures, automations and decision support.

The goal is not to build the most complicated AI system. The goal is to build the simplest operating layer that makes a real business measurable, auditable, delegable and progressively autonomous.

## Core principle

**Deterministic first, AI assisted.**

Business correctness does not live in prompts.

Use the lowest level of complexity that can solve the problem:

```
SQL
→ deterministic code
→ workflow
→ structured LLM
→ tool-using agent
→ multi-agent only when justified
```

Calculations, reconciliation, permissions, side effects and business rules belong in software.

## Public reference pipeline

```
Sources
→ Raw Evidence
→ PostgreSQL / approved knowledge base
→ Trust Layer + deterministic services
→ typed tools / Context Builder
→ Lex
→ Proposal
→ Human Approval when required
→ deterministic Executor
→ Verification
→ Audit
```

## Minimal kernel before frameworks

ATLAS does not currently need a stack of orchestration frameworks merely because they are available.

The useful baseline is deliberately small:

- PostgreSQL
- Work Order schema
- Capability schema
- explicit state machine
- idempotency keys
- evidence log
- OpenTelemetry trace_id

Frameworks are benchmarks first and dependencies only when a measured operational problem justifies them.

## Trust model

A few rules are non-negotiable:

- missing is not zero
- stale or incomplete data is not presented as certain
- MATCHED, VERIFIED and RECONCILED require evidence
- every important operation should be reconstructable from source to verification
- reasoning, approval and execution remain separate
- external input is treated as untrusted

## Public / private boundary

Public work may include:

- architecture notes
- RFCs
- abstract schemas
- synthetic examples
- sanitized reference patterns

Public work must not include:

- real POS, bank or invoice data
- credentials, tokens or secrets
- supplier prices or confidential terms
- customer or employee data
- production hosts, IPs, VPNs, endpoints or topology
- unresolved exploitable vulnerabilities
- real logs or internal privileged configuration

**Missing review = NOT VERIFIED = do not publish.**

## Current public research themes

The first areas worth discussing openly are:

1. Work Order envelope and lifecycle
2. Capability Registry
3. POS → settlement → bank reconciliation
4. evidence and verification models
5. observability and traceability
6. safe AI-assisted operations with explicit approval boundaries

These are useful because they are concrete operating-system problems, not generic AI demos.

---

This repository is a public technical surface for Lex / Progetto ATLAS. Production systems remain private by design.
