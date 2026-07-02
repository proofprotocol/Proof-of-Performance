# PROOF OF PERFORMANCE
### A Standards Proposal for Cryptographically Verifiable AI System Performance Claims

**Version:** 0.1 - Public Draft  
**Issued by:** HACKERverse® / Nebulonium, Inc.  
**Author:** Craig Ellrod, Founder & CEO  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)  
**Companion standard to:** Proof of Efficacy (PoE) v0.1  

---

## Abstract

AI vendors make performance claims. Enterprises buy on those claims. No independent, cryptographically verifiable mechanism exists to prove those claims are true under real operational conditions.

This document proposes Proof of Performance (PoP) as a formal standard for cryptographically verifiable evidence that an AI system met its specified performance commitments - throughput, latency, uptime, accuracy, and SLA terms - under defined operational conditions, at a specific point in time, witnessed independently, and sealed against post-hoc fabrication.

PoP is a companion standard to the Proof of Efficacy (PoE) standard published by HACKERverse®. Where PoE proves an AI agent worked under adversarial conditions, PoP proves an AI system performed to specification under operational load. These are complementary claims requiring separate proof regimes. Both are implemented via the Defensible Knowledge Proof (DKP) protocol.

The author, Craig Ellrod, brings more than 30 years of experience in system and device testing under operational and adversarial conditions. Craig's work on test environments and test products, including the System Under Test (SUT) and Device Under Test (DUT) methodology, dates back to 2004 and was documented in his book Technical Marketing. PoP is the formal cryptographic standard for what practitioners have been doing in labs for three decades.

## 1. Problem Statement

### 1.1 The Performance Claim Gap

Every AI vendor publishes benchmark results. Accuracy rates, inference latency, uptime guarantees, throughput figures, and SLA commitments are the currency of enterprise AI procurement. Enterprises sign contracts on these numbers.

None of these claims are independently verifiable after the fact. Benchmark results are produced in controlled conditions chosen by the vendor. SLA commitments are measured by the vendor's own monitoring systems. Uptime figures are reported by the party with a commercial interest in reporting favorably.

Without proof of performance, AI procurement is an act of faith. Enterprise buyers have no mechanism to verify that the system they purchased performs as specified in their environment, under their operational load, at the time they need it.

### 1.2 Why Attestation Is Not Proof

Vendor attestation - a signed statement that a system met performance targets - is the current state of the art. Attestation is better than nothing. It is not proof.

Attestation is produced by the party with a financial interest in the outcome. It reflects a point in time chosen by the vendor. It cannot be independently verified by a third party after the fact. It can be produced retroactively. None of these properties satisfy the requirements of enterprise procurement, regulatory compliance, or legal dispute resolution.

PoP requires pre-specification commitment, independent witnessing, and tamper-evident sealing. A performance claim that cannot be independently verified after the fact is not a claim - it is a marketing statement.

### 1.3 Regulatory and Contractual Context

Performance claims are increasingly subject to regulatory scrutiny. The EU AI Act, FTC guidelines on AI claims, and enterprise procurement standards all impose requirements that AI systems perform as represented. None of them specify a cryptographic verification mechanism. PoP provides that mechanism.

In contract law, a vendor's failure to meet SLA commitments triggers remedies. Without an independent, tamper-evident record of actual performance, disputes default to he-said/she-said. PoP creates the evidentiary record that resolves those disputes.

### 1.4 Distinction from Proof of Efficacy

Proof of Efficacy (PoE) proves an AI agent worked under adversarial conditions. The adversarial condition is the defining variable - PoE exists because an active opposing force was present and the agent was required to function despite it.

Proof of Performance (PoP) proves an AI system met its specified commitments under defined operational conditions. No adversarial force is required. The defining variable is the performance specification - throughput, latency, uptime, accuracy - and whether the system met it under real operational load.

Both standards are necessary. A system can perform to specification under normal load and fail under adversarial conditions. A system can withstand adversarial conditions and fail to meet throughput commitments under normal load. PoE and PoP measure different things. Neither substitutes for the other.

## 2. Definitions

The following terms are defined for the purposes of this standard:

| Term | Definition |
|------|------------|
| Proof of Performance (PoP) | A cryptographically verifiable record demonstrating that an AI system met its specified performance commitments under defined operational conditions - pre-specified before the measurement window, witnessed independently, and sealed against post-hoc fabrication. |
| Performance Specification | A documented, quantified commitment made by an AI vendor regarding system behavior under defined operational conditions. Examples include: inference latency (p99), throughput (requests per second), uptime (%), accuracy rate (%), and SLA terms. |
| Operational Condition | A defined set of environmental parameters under which performance is measured. Includes load level, infrastructure configuration, data volume, and any other variables that affect system behavior. |
| Pre-Specification Commitment | A cryptographic hash of the performance specification and measurement parameters, submitted to a publicly verifiable randomness beacon before the measurement window begins. |
| Measurement Window | The defined time period during which performance is measured. Must be specified in the Pre-Specification Commitment before the window opens. |
| Independent Witness | A third party with no commercial stake in the outcome who observes and signs the performance measurement in real time. |
| Performance Record | The complete, hash-chained record of a PoP pipeline: Pre-Specification Commitment, Measurement Window data, Independent Witness signature, Analysis verdict, and Sealed record. |
| SLA | Service Level Agreement. A contractual commitment by an AI vendor to meet defined performance specifications. PoP provides the cryptographic verification layer for SLA compliance claims. |
| ProofStamp | The HACKERverse® certification mark issued upon successful completion of a DKP pipeline, including PoP pipelines. |
| ProofRegister | The HACKERverse® public registry of sealed DKP records. Contains only cryptographic hash values - no raw performance data. Publicly queryable for independent verification. |
| ProofVault | The HACKERverse® private, offline storage of corroborating evidence for each PoP tier. Produced on demand for audit, litigation, or regulatory review. |
| DKP Protocol | The Defensible Knowledge Proof five-tier corroboration protocol: Activated, Committed, Witnessed, Analyzed, Sealed. The underlying mechanism for both PoE and PoP. |

## 3. The Proof of Performance Standard

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

A conformant PoP implementation MUST:

- Document the performance specification in full before the measurement window opens, including all metrics, thresholds, and operational conditions.
- Submit a cryptographic hash of the performance specification and measurement parameters to the NIST Randomness Beacon or equivalent publicly verifiable randomness source before the measurement window begins (Pre-Specification Commitment).
- Record the beacon pulse value and timestamp at the moment of commitment.
- Conduct measurement under the operational conditions specified in the Pre-Specification Commitment. Deviation from specified conditions invalidates the record.
- Submit all measurement data and the complete performance record to an independent witness for real-time observation and signature.
- Produce an independent analyst verdict evaluating measured performance against the pre-specified commitment.
- Seal the complete record - Pre-Specification Commitment through Analyst Verdict - with a cryptographic hash chain that renders post-hoc modification detectable.
- Publish the sealed record to a publicly queryable registry.
#### 3.2.2 SHOULD Requirements

A conformant PoP implementation SHOULD:

- Use the DKP five-tier corroboration model (Activated, Committed, Witnessed, Analyzed, Sealed) as the implementation framework.
- Anchor sealed records to a public blockchain or distributed ledger for independent verification.
- Specify measurement windows in advance and publish the schedule to allow third-party observation.
- Include raw measurement data in ProofVault for audit and dispute resolution purposes.
- Align with PoE records where the same system is subject to both performance and efficacy verification.
#### 3.2.3 MAY Requirements

A conformant PoP implementation MAY:

- Use ProofStamp as the certification mark upon successful completion.
- Register sealed records in ProofRegister for public query.
- Publish PoP records alongside PoE records for systems subject to both standards.
- Use PoP records as evidence in SLA dispute resolution or regulatory compliance proceedings.
### 3.3 Performance Metric Categories

PoP applies across four primary performance metric categories. Each category requires separate pre-specification and measurement:

| Category | Examples | Typical Buyer |
|----------|----------|---------------|
| Speed | Inference latency (p50/p99), time-to-first-token, throughput (requests per second), response time under load. | Engineering, operations, and procurement teams with latency SLAs. |
| Availability | Uptime percentage, mean time between failures (MTBF), mean time to recovery (MTTR), scheduled downtime. | Legal, procurement, and operations teams managing SLA contracts. |
| Accuracy | Task completion rate, false positive/negative rates, precision, recall, F1 score, hallucination rate. | Risk, compliance, and business stakeholders evaluating AI decision quality. |
| Scale | Concurrent user capacity, data volume handling, horizontal scaling behavior, degradation curve under peak load. | Architecture and capacity planning teams managing enterprise deployments. |

### 3.4 The DKP Five-Tier Model Applied to PoP

PoP is implemented via the DKP five-tier corroboration model. The tiers map to PoP as follows:

| Tier | Name | PoP Application | ProofRegister | ProofVault |
|------|------|-----------------|---------------|------------|
| 1 | Activated | System initialized. Performance specification documented. Operational conditions confirmed. Measurement window defined. | System ID hash, specification hash, operational condition hash. | Full performance specification, system configuration, operational condition documentation. |
| 2 | Committed | Cryptographic hash of performance specification and measurement parameters submitted to NIST Randomness Beacon before measurement window opens. The claim is made before the outcome is known. | Pre-specification commitment hash, NIST Beacon pulse value and timestamp. | Full specification, Beacon API response, PCID. |
| 3 | Witnessed | Measurement window runs. Independent witness observes in real time. Raw performance data and corroborating evidence captured. Witness signs the record. Hash-chained to Tier 2. | Witness signature hash, hash-chain link to Tier 2. | Signed witness record, raw measurement logs, interface capture artifacts. |
| 4 | Analyzed | Independent analyst evaluates measured performance against Tier 2 pre-specification commitment. Met or not met verdict per metric. Analyst signs the verdict. | Analyst signature hash, verdict hash, hash-chain link to Tier 3. | Signed analyst report, per-metric verdict, deviation documentation. |
| 5 | Sealed | Complete record - Tiers 1 through 4 - hash-sealed and published to ProofRegister. ProofStamp issued. Publicly queryable. Tamper-evident. | Final sealed hash of Tier 1-4 chain. ProofStamp issued. | Complete corroborating artifact bundle. Access-controlled. Produced on demand. |

## 4. Relationship to Existing Frameworks

### 4.1 Proof of Efficacy (PoE)

PoP and PoE are companion standards implementing the same DKP protocol against different proof questions. PoE asks: did the security agent work under adversarial conditions? PoP asks: did the system meet its performance specification under operational conditions?

A complete AI vendor assurance package requires both. PoE without PoP leaves performance claims unverified. PoP without PoE leaves adversarial resilience unverified. Enterprise buyers and regulators should require both.

### 4.2 SLA Contracts

Existing SLA frameworks define performance commitments but provide no independent verification mechanism. PoP provides that mechanism. A PoP record is an independently witnessed, cryptographically sealed artifact that can be produced in contract disputes as evidence of actual performance at a specific time under specified conditions.

PoP does not replace SLA contracts. It provides the evidentiary layer that makes SLA commitments enforceable with independently verifiable evidence rather than vendor-reported metrics.

### 4.3 EU AI Act and Regulatory Frameworks

The EU AI Act imposes performance and accuracy requirements on high-risk AI systems. Current compliance mechanisms rely on vendor attestation and third-party audits conducted at a point in time. PoP provides continuous, cryptographically verifiable performance records that satisfy regulatory requirements for demonstrated performance without relying on periodic assessments.

### 4.4 Benchmarks and Industry Testing Bodies

Industry benchmarks (MLPerf, HELM, and similar frameworks) measure performance under controlled conditions at a point in time chosen by the vendor or testing body. Results are not independently witnessed and can be gamed through benchmark-specific optimization. PoP requires pre-specification commitment before measurement begins, independent witnessing during measurement, and tamper-evident sealing of results. These requirements are structurally incompatible with benchmark gaming.

## 5. Certification

### 5.1 Standard vs. Certification

This standard is published under Creative Commons Attribution 4.0 International (CC BY 4.0). Any party may implement, reference, or build upon it without restriction, provided attribution is given to HACKERverse® / Nebulonium, Inc.

Certification against this standard - the right to carry the ProofStamp mark - is a separate function retained by HACKERverse®. The standard is open. The stamp is not.

### 5.2 ProofStamp

ProofStamp is the HACKERverse® certification mark issued upon successful completion of a DKP pipeline, including PoP pipelines. A ProofStamp on a performance claim means the claim was pre-specified before measurement, independently witnessed, independently analyzed, and sealed in ProofRegister. Enterprises and regulators can verify any ProofStamp by querying ProofRegister with the associated record hash.

### 5.3 ProofRegister

ProofRegister is the public registry of sealed DKP records. Publicly queryable at ProofRegister.com. Contains only cryptographic hash values - no raw performance data is exposed publicly.

### 5.4 ProofVault

ProofVault is the private, offline storage of corroborating evidence for each PoP tier. Contains raw measurement logs, witness signatures, analyst reports, and all supporting documentation. Access-controlled. Produced on demand for audit, SLA dispute resolution, litigation, or regulatory review.

## 6. Governance and Working Group

HACKERverse® invites comment and participation from:

- Enterprise AI buyers, procurement teams, and legal counsel managing SLA contracts
- AI vendors making performance claims to enterprise buyers or regulators
- EU AI Act compliance bodies and equivalent regulatory frameworks
- NIST, ISO, IEEE, and industry benchmarking bodies
- POCI founding members and the Advanced AI Society
- CSA AARM working group participants
Contributions to this standard that result in adopted specification language will be credited. Contributors do not acquire IP rights to the DKP protocol, ProofStamp mark, or ProofRegister platform.

Working group inquiries: HACKERverse®.ai

## 7. Prior Art and Timeline

Craig Ellrod has been proving system and device performance under defined test conditions since 2004. The System Under Test (SUT) and Device Under Test (DUT) methodology - formally documented in Craig's book Technical Marketing - is the foundational prior art from which PoP emerges. PoP is the formalization of three decades of test practice into a cryptographically verifiable, independently witnessed standard.

- 2004: Craig Ellrod develops SUT/DUT test methodology, documented in Technical Marketing. Foundational prior art for both PoP and PoE.
- 2004-2025: Thirty-plus years of system and device performance testing across Cisco, Armor Defense, JupiterOne, and Cequence Security.
- May 2025: HACKERverse® formalizes the Proof Economy category. DKP protocol named and architected. PoE and PoP emerge as companion standards.
- February 28, 2026: Earliest provisional patent application filed (HV-PROV-001). Six total provisional applications (HV-PROV-001 through HV-PROV-006). Conversion deadlines February-March 2027.
- March 24, 2026: Gartner releases Adversarial Exposure Validation (AEV) category - ten months after Proof Economy coinage.
- May 26, 2026: HACKERverse® registered in DoD CDAO Tradewinds at TRL 7, awardable.
- July 2026: This standards proposal published.
## 8. Contact

Craig Ellrod

Founder and CEO, Nebulonium, Inc. (HACKERverse® / World Hacker Games™)

HACKERverse®.ai | ProofRegister.com

License: Creative Commons Attribution 4.0 International (CC BY 4.0)

> *This document may be freely shared, referenced, and built upon with attribution. Certification rights are retained by HACKERverse®.*
