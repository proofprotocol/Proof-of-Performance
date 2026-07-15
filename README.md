> **Zenodo DOI:** [10.5281/zenodo.21379780](https://doi.org/10.5281/zenodo.21379780) — Published 2026-07-15

# Proof of Performance Specification

**Document ID:** PP-SPEC-013  
**Version:** 1.0  
**Status:** Published  
**License:** CC BY 4.0  
**Maintained by:** Proof Economy™ Standards Alliance (PESA)  
**Repository:** https://github.com/proofprotocol  
**Published:** 2026-07-14  
**Companion standard to:** PP-SPEC-006 (Proof of Efficacy Score)

---

## Abstract

AI vendors make performance claims. Enterprises buy on those claims. No independent, cryptographically verifiable mechanism exists to prove those claims are true under real operational conditions.

This specification defines Proof of Performance (ProofPerf™) as a formal standard for cryptographically verifiable evidence that an AI system met its specified performance commitments - throughput, latency, uptime, accuracy, and SLA terms - under defined operational conditions, at a specific point in time, witnessed independently, and sealed against post-hoc fabrication.

ProofPerf™ is a companion standard to PP-SPEC-006 (Proof of Efficacy Score). Where PES proves an AI agent worked under adversarial conditions, ProofPerf™ proves an AI system performed to specification under operational load. These are complementary claims requiring separate proof regimes. Both are implemented via the Proof Protocol™.

The author, Craig Ellrod, brings more than 30 years of experience in system and device testing under operational and adversarial conditions. The System Under Test (SUT) and Device Under Test (DUT) methodology - formally documented in Craig's book Technical Marketing - dates back to 2004 and is the foundational prior art from which ProofPerf™ emerges.

---

## 1. Problem Statement

### 1.1 The Performance Claim Gap

Every AI vendor publishes benchmark results. Accuracy rates, inference latency, uptime guarantees, throughput figures, and SLA commitments are the currency of enterprise AI procurement. Enterprises sign contracts on these numbers.

None of these claims are independently verifiable after the fact. Benchmark results are produced in controlled conditions chosen by the vendor. SLA commitments are measured by the vendor's own monitoring systems. Uptime figures are reported by the party with a commercial interest in reporting favorably.

Without proof of performance, AI procurement is an act of faith.

### 1.2 Why Attestation Is Not Proof

Vendor attestation - a signed statement that a system met performance targets - is the current state of the art. Attestation is better than nothing. It is not proof.

Attestation is produced by the party with a financial interest in the outcome. It reflects a point in time chosen by the vendor. It cannot be independently verified by a third party after the fact. It can be produced retroactively. None of these properties satisfy the requirements of enterprise procurement, regulatory compliance, or legal dispute resolution.

ProofPerf™ requires pre-specification commitment, independent witnessing, and tamper-evident sealing. A performance claim that cannot be independently verified after the fact is not a claim - it is a marketing statement.

### 1.3 Regulatory and Contractual Context

Performance claims are increasingly subject to regulatory scrutiny. The EU AI Act, FTC guidelines on AI claims, and enterprise procurement standards all impose requirements that AI systems perform as represented. None of them specify a cryptographic verification mechanism. ProofPerf™ provides that mechanism.

In contract law, a vendor's failure to meet SLA commitments triggers remedies. Without an independent, tamper-evident record of actual performance, disputes default to he-said/she-said. ProofPerf™ creates the evidentiary record that resolves those disputes.

### 1.4 Distinction from Proof of Efficacy Score

PES (PP-SPEC-006) proves an AI agent worked under adversarial conditions. The adversarial condition is the defining variable - PES exists because an active opposing force was present and the agent was required to function despite it.

ProofPerf™ proves an AI system met its specified commitments under defined operational conditions. No adversarial force is required. The defining variable is the performance specification - throughput, latency, uptime, accuracy - and whether the system met it under real operational load.

Both standards are necessary. A system can perform to specification under normal load and fail under adversarial conditions. A system can withstand adversarial conditions and fail to meet throughput commitments under normal load. PES and ProofPerf™ measure different things. Neither substitutes for the other.

---

## 2. Definitions

| Term | Definition |
|------|-----------|
| ProofPerf™ | A cryptographically verifiable record demonstrating that an AI system met its specified performance commitments under defined operational conditions - pre-specified before the measurement window, witnessed independently, and sealed against post-hoc fabrication. |
| Performance Specification | A documented, quantified commitment made by an AI vendor regarding system behavior under defined operational conditions. Examples: inference latency (p99), throughput (requests per second), uptime (%), accuracy rate (%), SLA terms. |
| Operational Condition | A defined set of environmental parameters under which performance is measured. Includes load level, infrastructure configuration, data volume, and any other variables that affect system behavior. |
| Pre-Specification Commitment | A cryptographic hash of the performance specification and measurement parameters, submitted to the NIST Randomness Beacon before the measurement window begins. |
| Measurement Window | The defined time period during which performance is measured. Must be specified in the Pre-Specification Commitment before the window opens. |
| Independent Witness | A third party with no commercial stake in the outcome who observes and signs the performance measurement in real time. See PP-SPEC-005. |
| Performance Record | The complete, hash-chained record of a ProofPerf™ pipeline: Pre-Specification Commitment, Measurement Window data, Independent Witness signature, Analysis verdict, and Sealed record. |
| SLA | Service Level Agreement. A contractual commitment by an AI vendor to meet defined performance specifications. ProofPerf™ provides the cryptographic verification layer for SLA compliance claims. |
| ProofStamp™ | The HACKERverse® certification mark issued upon successful completion of a Proof Protocol™ pipeline, including ProofPerf™ pipelines. See PP-SPEC-009. |
| ProofRegister™ | The HACKERverse® public registry of sealed Proof Protocol™ records. Contains only cryptographic hash values. Publicly queryable for independent verification. See PP-SPEC-004. |
| ProofVault™ | The HACKERverse® private, offline storage of corroborating evidence for each ProofPerf™ tier. Produced on demand for audit, litigation, or regulatory review. |
| Proof Protocol™ | The five-tier corroboration protocol: Activated → Committed → Witnessed → Analyzed → Sealed. The underlying mechanism for both PES and ProofPerf™. See PP-SPEC-001. |

---

## 3. The ProofPerf™ Standard

### 3.1 Scope

This standard applies to any AI system, platform, or service that makes quantified performance claims to enterprise buyers, regulators, or auditors. This includes but is not limited to:

- AI inference platforms making latency or throughput claims
- AI SaaS products with uptime or availability SLAs
- AI agents making accuracy or task completion rate claims
- AI vendors submitting benchmark results to procurement processes
- AI systems subject to regulatory performance requirements under the EU AI Act or equivalent frameworks
- AI vendors in contractual SLA disputes requiring independent performance verification

### 3.2 Requirements

#### 3.2.1 MUST Requirements

A conformant ProofPerf™ implementation MUST:

- Document the performance specification in full before the measurement window opens, including all metrics, thresholds, and operational conditions
- Submit a cryptographic hash of the performance specification and measurement parameters to the NIST Randomness Beacon before the measurement window begins
- Record the beacon pulse value and timestamp at the moment of commitment
- Conduct measurement under the operational conditions specified in the Pre-Specification Commitment
- Submit all measurement data and the complete performance record to an independent witness for real-time observation and signature
- Produce an independent analyst verdict evaluating measured performance against the pre-specified commitment
- Seal the complete record with a cryptographic hash chain that renders post-hoc modification detectable
- Publish the sealed record to a publicly queryable registry

#### 3.2.2 SHOULD Requirements

A conformant ProofPerf™ implementation SHOULD:

- Use the Proof Protocol™ five-tier corroboration model as the implementation framework
- Anchor sealed records to a public blockchain or distributed ledger for independent verification
- Specify measurement windows in advance and publish the schedule to allow third-party observation
- Include raw measurement data in ProofVault™ for audit and dispute resolution purposes
- Align with PES records where the same system is subject to both performance and efficacy verification

#### 3.2.3 MAY Requirements

A conformant ProofPerf™ implementation MAY:

- Use ProofStamp™ as the certification mark upon successful completion
- Register sealed records in ProofRegister™ for public query
- Publish ProofPerf™ records alongside PES records for systems subject to both standards
- Use ProofPerf™ records as evidence in SLA dispute resolution or regulatory compliance proceedings

### 3.3 Performance Metric Categories

ProofPerf™ applies across four primary performance metric categories. Each category requires separate pre-specification and measurement:

| Category | Examples | Typical Buyer |
|----------|---------|--------------|
| Speed | Inference latency (p50/p99), time-to-first-token, throughput (requests per second), response time under load | Engineering, operations, and procurement teams with latency SLAs |
| Availability | Uptime percentage, MTBF, MTTR, scheduled downtime | Legal, procurement, and operations teams managing SLA contracts |
| Accuracy | Task completion rate, false positive/negative rates, precision, recall, F1 score, hallucination rate | Risk, compliance, and business stakeholders evaluating AI decision quality |
| Scale | Concurrent user capacity, data volume handling, horizontal scaling behavior, degradation curve under peak load | Architecture and capacity planning teams managing enterprise deployments |

### 3.4 The Proof Protocol™ Five-Tier Model Applied to ProofPerf™

| Tier | Name | ProofPerf™ Application | ProofRegister™ | ProofVault™ |
|------|------|----------------------|---------------|------------|
| 1 | Activated | System initialized. Performance specification documented. Operational conditions confirmed. Measurement window defined. | System ID hash, specification hash, operational condition hash | Full performance specification, system configuration, operational condition documentation |
| 2 | Committed | Cryptographic hash of performance specification and measurement parameters submitted to NIST Randomness Beacon before measurement window opens. The claim is made before the outcome is known. | Pre-specification commitment hash, NIST Beacon pulse value and timestamp | Full specification, Beacon API response, PCID |
| 3 | Witnessed | Measurement window runs. Independent witness observes in real time. Raw performance data and corroborating evidence captured. Witness signs the record. Hash-chained to Tier 2. | Witness signature hash, hash-chain link to Tier 2 | Signed witness record, raw measurement logs, interface capture artifacts |
| 4 | Analyzed | Independent analyst evaluates measured performance against Tier 2 pre-specification commitment. Met or not met verdict per metric. Analyst signs the verdict. | Analyst signature hash, verdict hash, hash-chain link to Tier 3 | Signed analyst report, per-metric verdict, deviation documentation |
| 5 | Sealed | Complete record - Tiers 1 through 4 - hash-sealed and published to ProofRegister™. ProofStamp™ issued. Publicly queryable. Tamper-evident. | Final sealed hash of Tier 1–4 chain. ProofStamp™ issued. | Complete corroborating artifact bundle. Access-controlled. Produced on demand. |

---

## 4. Relationship to Existing Frameworks

### 4.1 Proof of Efficacy Score (PP-SPEC-006)

ProofPerf™ and PES are companion standards implementing the same Proof Protocol™ against different proof questions. PES asks: did the security agent work under adversarial conditions? ProofPerf™ asks: did the system meet its performance specification under operational conditions?

A complete AI vendor assurance package requires both. PES without ProofPerf™ leaves performance claims unverified. ProofPerf™ without PES leaves adversarial resilience unverified.

### 4.2 SLA Contracts

Existing SLA frameworks define performance commitments but provide no independent verification mechanism. ProofPerf™ provides that mechanism. A ProofPerf™ record is an independently witnessed, cryptographically sealed artifact that can be produced in contract disputes as evidence of actual performance at a specific time under specified conditions.

ProofPerf™ does not replace SLA contracts. It provides the evidentiary layer that makes SLA commitments enforceable with independently verifiable evidence rather than vendor-reported metrics.

### 4.3 EU AI Act and Regulatory Frameworks

The EU AI Act imposes performance and accuracy requirements on high-risk AI systems. Current compliance mechanisms rely on vendor attestation and third-party audits conducted at a point in time. ProofPerf™ provides continuous, cryptographically verifiable performance records that satisfy regulatory requirements for demonstrated performance without relying on periodic assessments.

### 4.4 Benchmarks and Industry Testing Bodies

Industry benchmarks (MLPerf, HELM, and similar frameworks) measure performance under controlled conditions at a point in time chosen by the vendor or testing body. Results are not independently witnessed and can be gamed through benchmark-specific optimization. ProofPerf™ requires pre-specification commitment before measurement begins, independent witnessing during measurement, and tamper-evident sealing of results. These requirements are structurally incompatible with benchmark gaming.

---

## 5. Certification

### 5.1 Standard vs. Certification

This specification is published under CC BY 4.0. Any party may implement, reference, or build upon it without restriction, provided attribution is given to Craig Ellrod / Nebulonium, Inc..

Certification against this standard - the right to carry the ProofStamp™ mark - is a separate function retained by HACKERverse® as the independent test lab. The standard is open. The stamp is not.

### 5.2 ProofStamp™

ProofStamp™ is the HACKERverse® certification mark issued upon successful completion of a Proof Protocol™ pipeline, including ProofPerf™ pipelines. A ProofStamp™ on a performance claim means the claim was pre-specified before measurement, independently witnessed, independently analyzed, and sealed in ProofRegister™.

### 5.3 ProofRegister™

ProofRegister™ is the public registry of sealed Proof Protocol™ records. Publicly queryable at ProofRegister™.com. Contains only cryptographic hash values - no raw performance data is exposed publicly.

### 5.4 ProofVault™

ProofVault™ is the private, offline storage of corroborating evidence for each ProofPerf™ tier. Contains raw measurement logs, witness signatures, analyst reports, and all supporting documentation. Access-controlled. Produced on demand for audit, SLA dispute resolution, litigation, or regulatory review.

---

## 6. Governance

PESA invites comment and participation from:

- Enterprise AI buyers, procurement teams, and legal counsel managing SLA contracts
- AI vendors making performance claims to enterprise buyers or regulators
- EU AI Act compliance bodies and equivalent regulatory frameworks
- NIST, ISO, IEEE, and industry benchmarking bodies

Contributions to this standard that result in adopted specification language will be credited. Contributors do not acquire IP rights to the Proof Protocol™, ProofStamp™ mark, or ProofRegister™ platform.

Working group inquiries: benchmark@proofbenchmark.com

---

## 7. Prior Art and Timeline

Craig Ellrod has been proving system and device performance under defined test conditions since 2004. The System Under Test (SUT) and Device Under Test (DUT) methodology - formally documented in Craig's book Technical Marketing - is the foundational prior art from which ProofPerf™ emerges.

| Date | Event |
|------|-------|
| 2004 | Craig Ellrod develops SUT/DUT test methodology, documented in Technical Marketing |
| 2004–2025 | System and device performance testing across Cisco, Armor Defense, JupiterOne, and Cequence Security |
| May 2025 | HACKERverse® formalizes the Proof Economy™ category. Proof Protocol™ named and architected. PES and ProofPerf™ emerge as companion standards. |
| Feb 28, 2026 | Earliest provisional patent application filed (HV-PROV-001). Six total provisionals (HV-PROV-001 through HV-PROV-006). Conversion deadlines February–March 2027. |
| March 24, 2026 | Gartner releases Adversarial Exposure Validation (AEV) category - ten months after Proof Economy™ coinage |
| May 26, 2026 | HACKERverse® registered in DoD CDAO Tradewinds at TRL 7, awardable |
| July 14, 2026 | This specification published as PP-SPEC-013 |

---

## 8. Authors

Craig Ellrod, Founder & CEO, Nebulonium, Inc. (d/b/a HACKERverse®)  
Castle Rock, Colorado  
2026-07-14

---

*CC BY 4.0 - Attribution to Craig Ellrod / Nebulonium, Inc. required.*  
*Proof Economy™ Standards Alliance (PESA) - proofprotocol.io*
