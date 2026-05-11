
Bangalore, India • github.com/darthcoder • http://darthcoder.github.io • <ab.ahmad@icloud.com>

Technical program operator: I coordinate alignment research across cross-functional teams and external collaborators. I reduce Byzantine complexity (n stakeholders, incompatible incentives, unclear ownership) so researchers can focus on hard problems without context-switching or bureaucracy.

## INDEPENDENT WORK
  
**Factual Grounding through Confidence Calibration** • Independent Research 2024 to present

Identified neglected problem in model oversight: confidence calibration as proxy for factual grounding. Scoped research goal, designed end-to-end pipeline (corpus → training → eval → domain expansion), executed with production-grade implementation (31 tests, extensible architecture). Testing hypothesis across domains (entity recognition, historical narratives) to assess stability of calibration behavior.
  

> github.com/darthcoder/ner-paper

  
**Open Source Contribution** • DataHaskell/dataframe Apr 2026

Pull request #193: refactored extract applyDictWithRepStitch to reduce allocation pressure in decodeDictV1 rep-level path. The issue: Parquet decoding was allocating intermediate vectors during the stitch operation, creating memory pressure in large data pipelines. The fix: restructured the stitch logic to work in-place on the rep-level buffer, eliminating unnecessary allocations. This matters for production systems where decode throughput is latency-critical and memory fragmentation ripples downstream. Applied to a library used in data-heavy ML pipelines.

**Writing** • darthcoder.github.io 2026

*"In the Beginning Was the Backslash"* (Apr 2026): LLMs as protocol adapters sitting between intent and execution. The missing shell that speaks human intent and routes across incompatible APIs (email, cloud storage, local disk) without requiring the user to learn topology.

*"What Does It Feel Like to Be a Chat?"* (Mar 2026): Applies Nagel's phenomenology to AI scope constraints. Properly constrained systems don't develop orthogonal motivations. Practical constraint is superior to theoretical alignment for current-generation AI.

*"The Post Cost of Pre Alignment"* (Mar 2026): Luddite perspective on alignment work. Explores the axiom problem: Asimov's Laws are incomplete. What happens when you add profit as an axiom? What undefined behavior means as agency.

## EDUCATION

**Dual Degree: B.Tech & M.Tech, Mechanical Engineering** • IIT Kanpur May 2011
Numerical methods, computational fluid dynamics, applied mathematics. Foundation for later ML and simulation work.

## EXPERIENCE

**Junior Research Fellow** • IIT Patna Jan 2012 to Aug 2017

Designed, scoped, and executed independent research cycles end-to-end: hypothesis formulation → implementation → large-scale evaluation → publication. Built analytical frameworks from ambiguous problem statements. Developed and optimized algorithms for PDEs; led data-driven simulations; executed large-scale experiments independently using Python (NumPy, SciPy, Pandas, Scikit-learn).

**Manager** • Canara Bank May 2022 to present

Coordinated cross-functional digital infrastructure program: integrated 5+ external service providers (fraud detection via Crif HighMark, account aggregation via Sahamati/AA framework, government lending portal JanSamarth). Managed contracts, onboarding, and integration edge cases. Delivered 100+ digital projects in fiscal year (FY 2024). Synthesized technical, regulatory, and operational risk into monthly leadership briefings for senior management. Managed complex portfolio under uncertainty; reduced NPA to 0.44% (lowest in Bengaluru Region); executed 25% business growth through strategic credit portfolio management. Upgraded branch risk classification to Low Risk (RBIA March 2024). 

**Assistant Branch Manager** • Canara Bank August 2017 to May 2022

Responsible oversight of all branch operations and learnt day to day branch operations. Second line Manager of a team of 14+ full and part time staff. Responsible for translating the Branch Manager's vision into concrete action leading to doubling of business over a period of 3 and a half years. 


## SKILLS & CERTIFICATIONS

**Languages & Tools:** Python, Haskell, SQL, NumPy / SciPy / Pandas / Polars / sk-learn, uv, git, unsloth.ai

**Certifications:** IBM Data Science (Coursera), IBM AI Developer (Coursera), (both had 10 courses each+capstone), CS50 (edX)