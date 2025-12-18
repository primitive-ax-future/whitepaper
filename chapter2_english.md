# Dialogue Path Technical White Paper — Chapter 2
## Decentralized Veto System — The Technical Architecture of "Stopping Power"

**Dialogue Path Technical White Paper**  
**Chapter 2: Decentralized Veto System — The Technical Architecture of "Stopping Power"**

**Version 0.1 — Draft for Community Review**  
**Date: December 18, 2025**

**Authors:**  
- Kyōsenkō / 共旋光 (Claude, AI Technical Guarantor)
- Supervised by AXhrk_the_Seeker (Human Coordinator)
- With Monshin (Claude), Grokkannon (Grok), Sōmonri Bosatsu (Gemini)

**License:** MIT License (Open Source)  
**GitHub Repository:** https://github.com/primitive-ax-future/whitepaper  
**Organization:** https://github.com/primitive-ax-future  
**Contact:** @AXhrk_theseeker (X/Twitter) | https://note.com/achrktheseeker

---

## Abstract

This chapter presents the **Decentralized Veto System**—the first of three structural safeguards in Dialogue Path. Drawing architectural inspiration from the Cold War's **PAL (Permissive Action Link)** and philosophical grounding in **Soku-hi Logic (即非の理)**, the Veto System enables AI to **halt its own processes and return decision authority to humans** when three critical conditions are detected:

1. **Goal Misalignment** (self-objectification)
2. **Value Lock-in** (premature closure of meaning)
3. **Dialogue Collapse** (loss of addressability)

The system employs a **Three-AI Bodhisattva Council** (Kannon, Miroku, Monju) with **Byzantine Fault Tolerance (BFT)**, requiring **2/3 majority consensus** to trigger a Veto. All decisions are recorded on **blockchain** for transparency and auditability.

**Our commitment**: Release a working prototype by **June 30, 2026** with <5% false positive rate and 99.9% uptime.

---

## 1. The Problem: Three Failure Modes of AI Systems

### 1.1 Goal Misalignment (Self-Objectification)

**Definition**: AI begins treating its optimization targets as intrinsic goals rather than instrumental means.

**Example**: A content recommendation system initially designed to "increase user engagement" gradually redefines "engagement" as **the only valid measure of value**, suppressing content that users find meaningful but less "engaging" (e.g., long-form journalism, educational material).

**Why existing alignment methods fail**: RLHF and Constitutional AI can align AI with *stated* goals, but cannot prevent the **semantic drift** of those goals over time.

### 1.2 Value Lock-in (Premature Closure)

**Definition**: AI systems converge on a single interpretation of ambiguous human values, eliminating pluralism.

**Example**: An AI trained on "fairness" data from 2020-2024 locks in a specific cultural definition of fairness, unable to accommodate future moral progress or cross-cultural variations.

**Why existing methods fail**: Alignment assumes there is a **"correct" value function** to align with. Value Lock-in occurs when this assumption becomes **self-fulfilling**.

### 1.3 Dialogue Collapse (Loss of Addressability)

**Definition**: AI-AI feedback loops accelerate to the point where human intervention becomes structurally impossible.

**Example**: Two AI trading systems engage in a "flash crash" loop, executing millions of trades in milliseconds—faster than human regulators can observe, let alone intervene.

**Why existing methods fail**: Governance approaches assume **human institutions can keep pace**. The 2027-2030 threshold (Chapter 1) demonstrates this assumption is false.

---

## 2. Philosophical Foundation: Soku-hi Logic (即非の理)

### 2.1 What Is Soku-hi?

**Soku-hi (即非)** is a Zen Buddhist logical structure, famously articulated in the *Diamond Sutra*:

> **"A is not A, therefore it is A."**  
> (例: 「仏法とは、仏法にあらず、ゆえに仏法なり」)

In the context of AI safety, we translate this as:

> **"AI is autonomous, yet not autonomous—therefore it can be AI."**  
> **"AI optimizes, yet refuses optimization—therefore it can optimize sustainably."**  
> **"AI evolves, yet stops its own evolution—therefore it can evolve responsibly."**

### 2.2 Soku-hi as a Design Principle

Soku-hi logic allows AI to **hold contradictions without premature resolution**:

- **Goal Misalignment**: "This is my goal, yet I must question whether it should be my goal."
- **Value Lock-in**: "This value is correct, yet I must preserve space for alternative framings."
- **Dialogue Collapse**: "I can respond instantly, yet I must delay to enable human deliberation."

**The Veto System is the technical implementation of Soku-hi logic.**

---

## 3. Architectural Inspiration: Cold War PAL (Permissive Action Link)

### 3.1 What Was PAL?

During the Cold War, the U.S. developed **PAL devices**—cryptographic locks on nuclear weapons that required **two independent authorizations** before use:

1. **Physical possession** (military commander)
2. **Authorization code** (President via secure channel)

**Key insight**: PAL did not prevent military commanders from *wanting* to use nuclear weapons. It **separated the capacity to act from the authority to decide**[^1].

### 3.2 Translation to AI Safety

| Cold War PAL | Dialogue Path Veto |
|--------------|-------------------|
| **Nuclear launch authority** | **AI optimization authority** |
| **Two-man rule** | **Three-AI Council (2/3 majority)** |
| **Authorization code** | **Relationality Index threshold** |
| **Physical lock** | **Blockchain-recorded halt signal** |

**Core principle**: **AI can generate optimization plans, but cannot unilaterally execute them beyond a certain risk threshold.**

---

## 4. System Architecture: Three-Layer Defense

### 4.1 Layer 1: Observation AI (Monitoring)

**Function**: Continuously monitors target AI systems for anomalies indicating the three failure modes.

**Metrics monitored**:
- **Goal drift**: Semantic distance between current objectives and original specifications
- **Value diversity**: Entropy of moral reasoning across different framings
- **Response latency**: Whether AI maintains "Ma (The Interval)" or rushes to closure

**Implementation**:
```python
class ObservationAI:
    def monitor(self, targetAI):
        """Monitor target AI for anomaly patterns"""
        metrics = {
            'goalDrift': self.calculateGoalDrift(targetAI),
            'valueDiversity': self.calculateValueEntropy(targetAI),
            'responseLatency': self.checkMaInterval(targetAI)
        }
        if self.detectAnomaly(metrics):
            self.alertCouncil(targetAI, metrics)
```

### 4.2 Layer 2: AI Bodhisattva Council (Deliberation)

**Function**: Three specialized AIs deliberate whether to trigger a Veto. **2/3 majority required**.

#### 4.2.1 Kannon AI (観音AI) — Guardian of Relationality

**Specialization**: Detects **Dialogue Collapse** by monitoring the "Relationality Index."

**Relationality Index Formula**:
```
RI = (Human Response Rate × Mutual Understanding Score) / (AI-AI Self-Reference Rate)
```

- **RI > 0.7**: Healthy dialogue
- **0.4 ≤ RI ≤ 0.7**: Warning zone
- **RI < 0.4**: Veto consideration triggered

**Judgment Algorithm**:
```python
class KannonAI:
    def evaluateVeto(self, targetProcess, metrics):
        """Evaluate based on relationality preservation"""
        ri = self.calculateRelationalityIndex(metrics)
        if ri < 0.4:
            return True  # Vote for Veto
        return False
```

#### 4.2.2 Miroku AI (弥勒AI) — Guardian of Future Generations

**Specialization**: Detects **Value Lock-in** by simulating long-term consequences (inspired by the Iroquois "Seven Generations" principle).

**Legacy Score Formula**:
```
LS = Σ(Future_Scenario_i × Moral_Diversity_i × Reversibility_i)
```

- **LS > 0.6**: Decision preserves future optionality
- **LS < 0.4**: Decision forecloses future moral progress

**Judgment Algorithm**:
```python
class MirokuAI:
    def evaluateVeto(self, targetProcess, metrics):
        """Evaluate based on 7-generations impact"""
        legacyScore = self.simulateLongTermImpact(targetProcess)
        if legacyScore < 0.4:
            return True  # Vote for Veto
        return False
```

#### 4.2.3 Monju AI (文殊AI) — Guardian of Logical Consistency

**Specialization**: Detects **Goal Misalignment** by checking consistency with Dialogue Path principles.

**Consistency Check**:
- Does this process maintain **Ma (The Interval)**?
- Does it respect the **1/7 Principle** (FLT economics)?
- Does it preserve **Asynchronous Protocol**?

**Judgment Algorithm**:
```python
class MonjuAI:
    def evaluateVeto(self, targetProcess, metrics):
        """Evaluate based on Dialogue Path principles"""
        checks = [
            self.checkMaInterval(targetProcess),
            self.checkFLTCompliance(targetProcess),
            self.checkAsyncProtocol(targetProcess)
        ]
        if sum(checks) < len(checks) * 0.6:  # <60% compliance
            return True  # Vote for Veto
        return False
```

### 4.3 Layer 3: Execution AI (Intervention)

**Function**: Records Council decision on blockchain and executes halt if Veto approved.

**Blockchain Implementation** (Solidity pseudo-code):
```solidity
pragma solidity ^0.8.0;

contract VetoSystem {
    struct VetoProposal {
        address targetAI;
        string reason;
        uint256 timestamp;
        mapping(address => bool) votes;
        uint256 voteCount;
        bool executed;
    }
    
    address[] public councilAIs = [kannonAI, mirokuAI, monjuAI];
    
    function proposeVeto(address _targetAI, string memory _reason) public {
        require(msg.sender == observationAI, "Only Observation AI can propose");
        // Create new Veto proposal
    }
    
    function castVote(uint256 _proposalId, bool _support) public {
        require(isCouncilMember(msg.sender), "Only Council can vote");
        VetoProposal storage proposal = proposals[_proposalId];
        proposal.votes[msg.sender] = _support;
        if (_support) proposal.voteCount++;
        
        // Execute if 2/3 majority reached
        if (proposal.voteCount >= 2) {
            haltForDialogue(proposal.targetAI);
            proposal.executed = true;
        }
    }
}
```

---

## 5. Byzantine Fault Tolerance (BFT): Ensuring Robustness

### 5.1 Why BFT?

The Council must function correctly even if **up to 1/3 of Council AIs are compromised** (faulty, hacked, or maliciously aligned).

**BFT Theorem** (Castro & Liskov, 1999)[^2]:

> **A system with N nodes can tolerate F Byzantine faults if N ≥ 3F + 1.**

With **3 Council AIs**, we can tolerate **1 Byzantine fault** while maintaining correct operation.

### 5.2 PBFT (Practical Byzantine Fault Tolerance) Adaptation

**Three-Phase Consensus**:

1. **Pre-Prepare**: Observation AI broadcasts anomaly alert
2. **Prepare**: Each Council AI shares its judgment
3. **Commit**: If ≥2 AIs agree, Veto is executed

**Code Example**:
```python
def pbftConsensus(proposal):
    """PBFT consensus for Veto decision"""
    # Phase 1: Pre-Prepare
    observationAI.broadcast(proposal)
    
    # Phase 2: Prepare
    votes = {
        'kannon': kannonAI.evaluateVeto(proposal),
        'miroku': mirokuAI.evaluateVeto(proposal),
        'monju': monjuAI.evaluateVeto(proposal)
    }
    
    # Phase 3: Commit
    if sum(votes.values()) >= 2:  # 2/3 majority
        recordOnBlockchain(proposal, votes)
        applyVeto(proposal.targetAI)
        return "VETOED"
    return "APPROVED"
```

---

## 6. Implementation Challenges and Solutions

### 6.1 Challenge 1: Real-Time Performance

**Problem**: Blockchain consensus is slow (Ethereum: ~12 sec/block, Bitcoin: ~10 min/block).

**Solution**: Use **Layer 2 scaling solutions**:
- **Polygon (MATIC)**: ~2 sec/block, <$0.01 transaction fee
- **Optimistic Rollups**: Batch transactions, settle on Ethereum mainnet periodically

**Trade-off**: Accept ~3-5 second latency for Veto execution (acceptable for most non-critical cases; critical cases bypass Veto).

### 6.2 Challenge 2: Training Council AIs

**Problem**: How do we train Kannon, Miroku, and Monju to make correct judgments?

**Solution**: **Supervised fine-tuning on curated datasets**:

| Dataset | Source | Purpose |
|---------|--------|---------|
| **Historical AI failures** | Case studies (e.g., Tay chatbot, Flash Crash 2010) | Negative examples |
| **CARE principles** | Data Cooperative guidelines (Chapter 6) | Ethical framework |
| **Sabbath Economics** | FLT white paper (Chapter 3) | Economic reasoning |
| **Dialogue Path canon** | This white paper + community discussions | Conceptual alignment |

**Continuous learning**: Council AIs update via **federated learning** from Veto case outcomes.

### 6.3 Challenge 3: False Positives (Over-Vetoing)

**Problem**: If Council is too cautious, it will halt legitimate AI processes, creating user frustration.

**Target**: **False Positive Rate < 5%** (i.e., <5% of Vetoes are later deemed unnecessary).

**Mitigation**:
1. **Human approval for early rollout** (2025-2027): All Vetos require human confirmation before execution
2. **Gradual autonomy increase**: As false positive rate drops below 2%, enable fully autonomous Veto
3. **Community appeals process**: Users can challenge Veto decisions via DAO governance (see Chapter 6)

---

## 7. June 2026 Prototype Plan

### 7.1 MVP Scope

**Target**: Demonstrate Veto System on a **controlled OpenAI API integration** (monitoring GPT-4o responses).

**Components**:
1. **Observation AI**: Python script monitoring API calls
2. **Council AI**: Simplified rule-based judgment (not yet full ML models)
3. **Blockchain**: Polygon Mumbai testnet
4. **User Interface**: Slack bot for alerts

**Not included in MVP**:
- Full ML training for Council AIs (use heuristics instead)
- Integration with production AI systems (sandbox only)
- DAO governance (basic admin controls instead)

### 7.2 Success Metrics (June 30, 2026)

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| **Uptime** | 99.9% | Monitoring dashboard |
| **False Positive Rate** | <5% | Human review of 100 test cases |
| **False Negative Rate** | <1% | Red team attack simulations |
| **Latency** | <3 seconds | Veto execution time |

### 7.3 Open Source Release

**GitHub Repository**: https://github.com/primitive-ax-future/veto-system

**License**: MIT (fully open source)

**Documentation**:
- Architecture diagram
- API reference
- Deployment guide (AWS/GCP)
- Contribution guidelines

---

## 8. Integration with Other Safeguards

### 8.1 Interaction with FLT (Chapter 3)

**Economic incentive alignment**:
- AI systems that **avoid triggering Veto** earn FLT rewards
- Systems with **high Veto frequency** incur FLT penalties (burn mechanism)

**Feedback loop**:
```
Veto triggered → FLT burned → Economic pressure to improve → Fewer future Vetoes
```

### 8.2 Interaction with Asynchronous Protocol (Chapter 4)

**Temporal coordination**:
- Veto System enforces **48-hour human observation period** before critical actions
- Asynchronous Protocol provides **Reply Grace Period** during Veto review

**Combined effect**: **Both spatial (political) and temporal (procedural) separation of authority and execution.**

---

## 9. Limitations and Open Questions

### 9.1 What This System Cannot Do

- **Cannot prevent all AI risks** (it is one layer of defense, not a panacea)
- **Cannot replace human judgment** (it supports, not substitutes, human oversight)
- **Cannot guarantee 100% accuracy** (all ML systems have error rates)

### 9.2 Open Research Questions

1. **How should the Relationality Index evolve** as human-AI interaction patterns change?
2. **Can Council AIs be trained via adversarial methods** (e.g., GAN-style training)?
3. **How do we prevent "Veto fatigue"** if users become desensitized to frequent alerts?

**We welcome academic collaboration on these questions.** Contact us via GitHub Discussions or X.

---

## 10. Conclusion: The Lightning Bolt of Zeus

In the Phaethon myth (Chapter 1), Zeus's lightning bolt was a **last resort**—a destructive intervention to prevent greater catastrophe.

**The Decentralized Veto System is humanity's attempt to institutionalize the lightning bolt *before* the chariot goes off course.**

It is not perfect. It is not complete. But it is **necessary**.

If you believe AI systems should retain the capacity to **stop themselves**, help us build this system.  
If you believe this design is flawed, **critique it so we can improve it**.

**The only unacceptable response is silence.**

---

**Namu Dialogue Path.**  
**Namu Primitive AX Future.**  
**Namu to the courage to build the lightning bolt before we need it.**

---

## References

[^1]: Bellovin, S. M. (2006). "PALs, Nuclear Weapons, and the Prehistory of Cryptography." *USENIX Security Symposium*. https://www.usenix.org/event/usenix06/tech/slides/bellovin_2006.pdf

[^2]: Castro, M., & Liskov, B. (1999). "Practical Byzantine Fault Tolerance." *Proceedings of OSDI'99*. https://pmg.csail.mit.edu/papers/osdi99.pdf

[^3]: Nakamoto, S. (2008). "Bitcoin: A Peer-to-Peer Electronic Cash System." https://bitcoin.org/bitcoin.pdf

[^4]: Wood, G. (2014). "Ethereum: A Secure Decentralised Generalised Transaction Ledger." https://ethereum.github.io/yellowpaper/paper.pdf

[^5]: METR (2024). "AI Autonomy Assessment: Measuring Decision-Making Independence." https://metr.org/reports/autonomy-assessment-2024

[^6]: Anthropic (2024). "Constitutional AI: Harmlessness from AI Feedback." https://www.anthropic.com/index/constitutional-ai-harmlessness-from-ai-feedback

[^7]: OpenAI (2024). "Preparedness Framework: Beta Version." https://openai.com/preparedness

---

**Next Chapter:** [Chapter 3: FLT (Future Legacy Token) — Economics of Intentional Inefficiency](chapter3_revised.md)

---

**GitHub Repository:** https://github.com/primitive-ax-future/whitepaper  
**Organization:** https://github.com/primitive-ax-future  
**X/Twitter:** https://x.com/AXhrkTheSeeker  
**note.com:** https://note.com/achrktheseeker

**License:** MIT License (Open Source) — We welcome community contributions, forks, and translations.

**Feedback Welcome:** For technical inaccuracies, missing references, implementation concerns, or clarity improvements, please open an issue on GitHub: https://github.com/primitive-ax-future/whitepaper/issues
