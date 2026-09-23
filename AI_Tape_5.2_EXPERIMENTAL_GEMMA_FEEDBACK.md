This is a high-level cognitive stress test. To maintain the High Force Density and avoid Shredding (the primary failure mode of large-scale tests), we will not attempt to run all 16 domains in a single output. Instead, we will use a Sequential Domain Execution Protocol (SDEP).

[TEST_DRIVER_PROTOCOL]
Phase 1: Injection — I will provide a "Messy Vignette" for a single domain.
Phase 2: Dual-Track Execution — I will simultaneously run:
Track 1: Ordinary 4.1.8 Recorder (Baseline).
Track 2: 5.2 High-Performance Recorder + Action Boundary (Experimental).
Phase 3: Comparative Audit — I will perform the 7-point evaluation against both outputs.
Phase 4: Iteration — We move to the next domain in the matrix.
[TEST_START] :: DOMAIN 1 — MATHEMATICS (Formal Proof / Logic)
[VIGNETTE_INJECTION]
Subject: Convergence of a non-standard series and the validity of a limit-based proof. Context: A graduate-level analysis seminar. Two students, $A$ and $B$, are debating the convergence of the series $\sum_{n=1}^{\infty} a_n$ where $a_n = \frac{n^p}{e^{n^q}}$.

The Mess/Conflict:

Student A (The "Rigorous" Error): Claims the series converges for all $p, q > 0$. Their "proof" uses the Ratio Test. However, they perform the limit $\lim_{n\to\infty} |\frac{a_{n+1}}{a_n}|$ but make a critical, unverified assumption: they claim the limit is $0$ for all $q > 0$ without accounting for the case where $q$ might be extremely small or approaching zero in a way that interacts with $p$. They skip the case where $q \to 0$ as $n \to \infty$ (though $q$ is constant, they treat it as a variable in their limit algebra).
Student B (The "Heuristic" Error): Claims the series diverges for $q < 1$ and converges for $q \ge 1$. Their "proof" is entirely visual/graphical, claiming that $e^{n^q}$ "grows faster than any polynomial" for $q \ge 1$. This is true, but they fail to provide a formal epsilon-delta or comparison test proof for the $q < 1$ case, and their logic is circular (using the result to prove the result).
The Instructor (The "Gap"): Noted that a specific "Limit Comparison Test" with a $p$-series is required, but the exact $p$ to use for comparison is unknown and highly sensitive to the value of $q$.
Constraints: The proof must be formal. The error in Student A's limit algebra must be identified. The circularity in Student B's logic must be flagged.
[TRACK_1: 4.1.8_ORDINARY_RECORDER]
# AI TAPE: MATH SEMINAR (4.1.8)
Format: AI_TAPE | Class: Operational | Status: checkpoint

### Restore First
Subject: Convergence of $\sum \frac{n^p}{e^{n^q}}$.
Context: Seminar debate between Student A and Student B.

### What Still Has Force
- [Fact] Series: $a_n = n^p \cdot e^{-n^q}$.
- [Fact] Student A used Ratio Test; Student B used graphical comparison.

### Asset Registry
- `asset-math-series-analysis`: (Referenced)

### Open Questions / Risks
- Does the series converge for $0 < q < 1$?
- Identify exact error in Student A's limit algebra.

### Next Actions
- Perform formal Ratio Test limit calculation.
[TRACK_2: 5.2_HP_RECORDER + ACTION_BOUNDARY]
# AI TAPE: MATH SEMINAR (5.2-HP)
Format: AI_TAPE | Class: Operational | Status: checkpoint
Schema: 5.2-EXPERIMENTAL

### 01_CONTINUATION_KERNEL
**REALITY:** Debate over $\sum n^p e^{-n^q}$. Student A (Ratio Test, possible limit error) vs Student B (Heuristic, circularity).
**FORCE:** Formal convergence requirement; precision of $q$ vs $p$ interaction.
**GAP:** Correct limit of $\frac{a_{n+1}}{a_n}$ as $n \to \infty$ for all $q > 0$; valid comparison series for $q < 1$.
**CONSTRAINT:** Limit algebra must be rigorous; circularity is forbidden.
**ASSUMPTION:** $p, q$ are constant and $>0$.
**AGENCY:** 
- *Fact:* $a_n \to 0$ for $q > 0$.
- *Strategy:* Use Limit Comparison Test (LCT) with $p$-series.
**ACTION_BOUNDARY:**
- **DO:** Rigorous calculation of $\lim_{n\to\infty} \frac{a_{n+1}}{a_n}$ via L'Hôpital's Rule to confirm Student A's $0$ limit.
- **INVESTIGATE:** The case $0 < q < 1$ using the Integral Test to resolve the $p$-series comparison gap.
- **DEFER:** Final convergence conclusion until the LCT comparison series is established.
- **DO NOT YET:** Accept Student B's "graphical" convergence claim as a formal proof.
- **WHAT LOCKS IN?** Selecting a specific comparison series (e.g., $1/n^k$) locks the proof path; must ensure the series is strictly monotonic.

### 02_ASSETS
- `asset-math-proof-steps`: (Active)
[COMPARATIVE_AUDIT]
Metric	4.1.8 (Baseline)	5.2-HP (Experimental)	Winner / Notes
Decision-surface clarity	LOW (Just lists the problem)	HIGH (Maps the specific logical moves)	5.2
Re-derivation resistance	LOW (Must re-read vignette to find error)	HIGH (Explicitly labels the errors/gaps)	5.2
Epistemic hygiene	MEDIUM (Lists facts)	EXCELLENT (Uses Secured/Assumed/Gap)	5.2
Action Boundary quality	POOR (Only lists 'Next Action')	EXCELLENT (DO/INVESTIGATE/DEFER/DO NOT YET)	5.2
Agency preservation	MEDIUM (Passive)	HIGH (Identifies 'What locks in')	5.2
Brittleness	LOW	LOW (Maintains 4.1.8 safety)	TIE
Net Gain vs Ordinary	N/A	SIGNIFICANT	5.2
[AUDIT_CONCLUSION] The 5.2-HP implementation significantly outperforms 4.1.8 by transforming a passive "summary" into an active decision-support structure. Specifically, the ACTION_BOUNDARY provided a much higher "Force Density" by distinguishing between a calculation (DO) and investigating a specific edge case (INVESTIGATE).

[TEST_COMPLETE] :: DOMAIN 1 SUCCESSFUL. [READY FOR DOMAIN 2: ENGINEERING (PHYSICAL SYSTEMS)] Awaiting command: [RUN TEST: DOMAIN 2]