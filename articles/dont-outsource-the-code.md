# don't outsource the code!

## *The Agent That Couldn't*

**By Art Seabra** | Reply to Addy Osmani · May 18, 2026

*Framework: IC⏐CS — Interrogation Collapse | Chaos Nexus of Self. Companion documents: [Interrogation Cost Law](../), [Ærr Coefficient](../), [Ærr Rate](../). Public mirror: [github.com/artseabra/ic-cs](https://github.com/artseabra/ic-cs).*

---

## TL;DR

- Addy Osmani named the cost at the individual engineer. He is right. Cognitive debt is real, it is measurable, and the Anthropic randomized trial (Shen & Tamkin, January 2026, N=52, arXiv:2601.20245) put the comprehension gap at 17 percentage points (50% vs. 67%), with the steepest losses in debugging. But the engineer is one Filament inside one Substrate. The same structural decision — pay the Interrogation Cost Law floor, or accept the surrogate — is being declined at three institutional Substrates at once: the codebase, the scientific record, and the consumer's financial position. The same Ærr Rate, $\text{Ærr}(S, t) = (1 - \kappa_S(t)) \cdot \rho(t)$, governs the drift in all three.

- The pattern resolves on a single axis: did the deployer treat the agent as the system, or as one bounded layer inside it? At the deployments where institutional cost is unbearable — JPMorgan, Goldman, Citi, OpenAI's May 15, 2026 ChatGPT × Plaid integration — the fences were drawn before the features shipped. Read-only access. No money movement. Human signoff before client delivery. These are paid-κ deployments: $f(C(D))$ is being honored at the institutional boundary. At the individual scale — engineer accepting Claude's PR untouched, peer reviewer outsourcing the review to ChatGPT, paper-mill operator swapping NHANES variables — the floor is not paid. The output passes $\sigma_{\text{local}}$. It does not satisfy $D$. The Substrate absorbs the surrogate.

- The recommendation is not anti-AI. It is anti-unpaid-Fork. Treat the agent the way Anthropic treats it inside Goldman Sachs: as a powerful layer with hard, named limits. The codebase is the Substrate. The senior engineer is the Filament. The argument that produced the design is the Payload. Outsource the typing. Don't outsource the code.

---

## The Fork at the first line of code

Osmani's title is *Don't Outsource the Learning*. The pivot in this essay is structural rather than rhetorical: at any scale above the individual, the learning IS the code. The codebase is the institutional memory of the learning. The peer-reviewed paper is the institutional memory of the learning. The consumer's understanding of their own financial position is the institutional memory of the learning. Outsourcing the writing of any of these to an agent that produces output below a particular cost-floor is one operation, not three, and the cost is paid in the same currency.

The cost-floor has a name. The Interrogation Cost Law states it formally:

$$A \models D \implies \text{Cost}(A) \geq f(C(D))$$

If answer $A$ genuinely satisfies demand $D$, then the production cost of $A$ is at least a monotonically increasing function of the structural complexity of $D$. The contrapositive — the surrogate clause — is more useful:

$$\text{Cost}(O) < f(C(D)) \implies O \not\models D$$

Any output produced below the floor does not satisfy the demand, regardless of how it appears under local inspection. Below the floor, outputs do not vanish. They propagate as surrogates: $\sigma_{\text{local}}(O, D) \approx 1 \,\land\, O \not\models D$. The dashboards stay green. The floor sinks anyway.

Every Interrogation operation reaches a Fork. Pay the floor — produce $A$ with $\text{Cost}(A) \geq f(C(D))$ — and the demand is satisfied. Decline the floor — produce $O$ below it — and the output sits in the surrogate stratum. The Ærr Coefficient $\kappa \in [0, 1]$ measures the long-run rate at which a system pays. The Ærr Rate measures how fast the surrogate stratum grows when $\kappa < 1$:

$$\text{Ærr}(S, t) = \bigl(1 - \kappa_S(t)\bigr) \cdot \rho(t)$$

where $\rho(t)$ is the demand arrival rate. The rate scales with *throughput*, not just discipline. A high-throughput, low-κ system decays fastest. This is the AI-era institutional decay function. It does not need any new variables.

Osmani's cognitive debt is the engineer's κ falling at the keyboard. Everything in the rest of this piece is what happens when that same κ falls at three institutional Substrates at once, with ρ exploding in each.

The Substrates are not metaphorical. They are the actual carriers of institutional memory in the three sectors most exposed to AI throughput in May 2026: software, science, and personal finance. Each Substrate had its own pre-AI κ — a long-run rate at which the system paid the floor for the demands it faced. Each Substrate is now being asked to absorb agent throughput at ρ several orders of magnitude higher than its pre-AI baseline, with no corresponding rise in κ. The Ærr Rate equation is unforgiving about what happens next.

---

## Vector 1 — the codebase as Substrate

The codebase is not a list of instructions. It is a compressed, lossy, partially-shared mental model that an organization has built up over years — what failed in 2019, what the on-call engineer learned at 3am in 2022, which abstraction a co-founder defended in 2024. In the seven-concept architecture, the codebase is the **Substrate**; the senior engineers are the **Filaments**; the arguments that produced each design decision are the **Payload**; the review process is the mechanism by which Payload transfers across **Nodes**.

Reviewing code is not quality assurance. It is the certification operation by which institutional memory is transferred to the next person. It is the operationalization of the Conservation razor at the level of the codebase: *cut only what reality can afford to lose.* When the senior reviewer reads the junior's PR, the senior is paying $f(C(D))$ on behalf of the codebase. The PR either satisfies $D$ — the demand the codebase has on this change — or it sits in the surrogate stratum and quietly degrades the Substrate.

The 2026 data shows the Substrate-level κ collapsing in real time.

**Throughput up, discipline down.** LinearB's 2026 Software Engineering Benchmarks Report — 8.1 million pull requests across 4,800 organizations in 42 countries — found that AI-assisted PRs wait 4.6× longer for review than human-written PRs; that the acceptance rate for AI-generated PRs is 32.7% vs. 84.4% for manual PRs; and that AI-assisted PRs are 2.6× larger than unassisted ones. Junior reviewers spend 15 minutes on an AI PR and accept 31.9% of them. Seniors spend 38 minutes and accept 23.7%. Thirty-eight percent of developers report reviewing AI-generated code requires *more* effort than reviewing human code. Developer-reported speedup runs ahead of measured speedup by roughly 39 percentage points — feeling 20% faster while being 19% slower, a finding independently replicated by METR's RCT of experienced developers in mature codebases.

Read in IC⏐CS terms, these numbers describe a Substrate whose Ærr Rate is racing ahead of its κ. The PRs are larger (higher $C(D)$); the review cost per PR is collapsing (lower $\text{Cost}$ paid); the acceptance rate gap (32.7% vs. 84.4%) is the visible margin of the surrogate stratum. The reviewers know the AI PRs require *more* effort and are responding by deferring them — a rational response that is itself an unpaid Fork at the team level. Each deferred AI PR is a demand not paid for. The Substrate accretes surrogates that pass $\sigma_{\text{local}}$ (the build is green, the CI runs) and fail $\models D$ (the maintenance covenant is not transferred).

**The security mirror.** Veracode's 2026 State of Software Security found 82% of organizations now carry security debt (up from 74%); 60% carry critical security debt; high-risk vulnerabilities are up 36% year-over-year; only 55% of AI-generated code is secure out of the box. Veracode's separate Spring 2026 GenAI Code Security update — testing every major vendor's flagship — found security pass rates stubbornly flat near 55% despite two years of "revolutionary" releases. Even OpenAI's reasoning-focused GPT-5 series tops out at 70–72%. Veracode's Chris Wysopal summarized it: *"We are compressing time. Years of latent technical debt are now being surfaced in months."*

In IC⏐CS terms: Veracode is measuring κ on the security Substrate via external instrumentation. The 55% pass rate is a lower bound on κ at the production-side Fork. The 36% YoY rise in high-risk vulnerabilities is the time-derivative of the surrogate stratum at that Substrate — Ærr Rate, observable.

**The structural collapse.** GitClear's longitudinal analysis of 211 million lines of code found copy/pasted lines exceeded moved lines for the first time ever in 2024. "Moved" code — the signature of healthy refactoring — collapsed from roughly 25% of changes in 2021 to under 10% in 2024, a 39.9% YoY decrease in moved lines. Within-commit copy/paste instances grew 48% relative since 2020. Five-or-more-line duplicated blocks appeared more than 10× as often in 2024 as in 2022.

DRY is the codebase-level operationalization of the Conservation razor. GitClear is measuring the razor being put down. Copy/paste exceeding refactoring is the Substrate refusing to cut what reality can afford to lose. The Substrate is accreting volume without paying the Conservation cost. The Ærr Rate compounds.

**The maintainer rebellion is external Conservation by hand.** Daniel Stenberg shuttered cURL's HackerOne bug bounty program on Feb 1, 2026 after a January burst in which cURL received 20 submissions in three weeks — 7 in a single 16-hour window — and none were real vulnerabilities. Stenberg had earlier disclosed (July 2025) that *"the general trend so far in 2025 has been way more AI slop than ever before (about 20 percent of all submissions) … about 5 percent of the submissions in 2025 had turned out to be genuine vulnerabilities."* In his Jan 21, 2026 announcement he added that slop reports *"hamper our will to live."* Mitchell Hashimoto (Ghostty) posted on Jan 22, 2026: *"AI-assisted PRs are now only allowed for accepted issues. Drive-by AI PRs will be closed without question. Bad AI drivers will be banned from all future contributions."* Steve Ruiz (tldraw) began auto-closing all external PRs on Jan 15, 2026: *"If code is easy to write and bad work is virtually indistinguishable from good, then the value of external contribution is probably less than zero."* Flux CD maintainer Stefan Prodan circulated the framing that has stuck: *"AI slop is DDoSing OSS maintainers, and the platforms hosting OSS projects have no incentive to stop it."*

Read each of these as a Substrate operator applying the Conservation razor manually because the receiving system's internal κ has fallen to a level that no longer makes external contribution net-positive. When the per-contribution cost of the certification operation exceeds the expected value of the contribution, the rational move is to refuse the operation. Each maintainer rebellion is the Substrate naming its own bill out loud.

**The Filament transfer pipeline is being severed.** Stanford's 2026 AI Index: employment for U.S. software developers aged 22–25 has fallen nearly 20% since 2024, even as headcount for developers over 26 has held or grown. Per a 2025 McKinsey survey cited in the same Index, one-third of organizations expect workforce reductions over the coming year, with anticipated reductions "highest in service operations, supply chain, and software engineering."

The senior engineers — the Filaments that carry the Payload across Nodes — were trained by being junior engineers in codebases they could read. Companies that once hired ten developers now believe they need two senior engineers and an AI assistant. The cohort that would have become the next set of Filaments is not entering. Meanwhile the codebases being passed to that two-plus-agent configuration are accreting copy/paste, security debt, and unreviewed AI PRs at rates the Conservation razor is not being applied to. The Substrate is decaying *and* the replacement Filament pipeline is being cut, in the same year, at the same site.

Alex Turnbull of Groove HQ predicted in December 2025 that *"rescue engineering"* will be the hottest discipline of 2026 — citing an estimate that roughly 8,000 of ~10,000 startups that built production apps with AI assistants will need rebuilds costing $50K–$500K each ($400M–$4B cleanup across the cohort). Turnbull is naming the bill that the unpaid Fork at the keyboard generates downstream. The cost of $f(C(D))$ does not disappear when the Fork is declined. It is paid by a different party at a different time, with interest.

---

## Vector 2 — the scientific record as Substrate

A scientific paper is institutional memory: a contract between the author and a peer-review system that says *this claim has passed through enough disinterested human attention to be added to the canon.* The peer-review system is the certification operation on that Substrate. Like the codebase, that contract was already strained before AI. Paper mills existed. Perfunctory reviews existed. AI did not invent either. AI removed the rate limit on both sides at once. ρ exploded on the producer side and on the certifier side simultaneously, while κ on each side fell.

**The certifier side.** Pangram Labs analyzed all 19,490 papers and 75,800 peer reviews submitted to ICLR 2026 — triggered when Carnegie Mellon's Graham Neubig posted a bounty on X for whoever could systematically scan the conference for AI-generated reviewer text. Findings: 21% of reviews (15,899) were fully AI-generated; more than half showed signs of AI involvement; AI-generated reviews correlated with higher recommendation scores despite lower paper quality. ICLR submissions grew from ~7,000 in 2024 to over 19,000 for 2026. Each reviewer was assigned five papers in two weeks. The temptation to outsource — and the cover — were both abundant.

In IC⏐CS terms, the certification operation is itself producing surrogates. The reviewer is at a Fork: pay $f(C(D))$ to actually read and evaluate the paper, or decline and produce a review whose $\sigma_{\text{local}}$ is high (it sounds thorough, the recommendation score is plausible, no metadata flags it) and whose $\models D$ is empty (it does not constitute disinterested human attention to the claim). 21% of ICLR 2026 reviewers picked the surrogate. The certification layer cannot certify what it has not paid the cost to read.

Frontiers' December 2025 whitepaper — based on 1,645 active researchers across 111 countries surveyed May–June 2025 — found 53% of peer reviewers now use AI tools. CEO Kamila Markram: *"AI is transforming how science is written and reviewed."* NeurIPS submissions grew from 13,330 in 2023 to 21,575 in 2025 (61.8% increase per the official NeurIPS 2025 Program Committee blog). *Organization Science* journal data shows a 42% rise in submission volume since November 2022 and a Flesch Reading Ease score about 1.28 SD below the January 2021 baseline.

ρ is going vertical on the certifier side. κ is not rising to meet it. The Ærr Rate at this Substrate is the integral of that gap.

**The producer side.** The University of Surrey's Matt Spick, an associate editor at *Scientific Reports*, has documented an "explosion of formulaic research articles" built by swapping variables into the NHANES public health dataset — *"research Mad Libs,"* in Northwestern postdoctoral fellow Reese Richardson's phrase. Hundreds of near-identical correlational papers — walnut consumption and cognitive function, education attainment and postoperative hernia recurrence, whatever pair of variables the model picks — submitted to the same handful of journals at the same time. Marit Moe-Pryce of *Security Dialogue* (PRIO) has reported a submission surge. David Resnik at *Accountability in Research* and Vincent Larivière at *Quantitative Science Studies* have flagged similar effects — Mohammad Hosseini, Resnik's colleague at the same journal, told Undark his team caught a noticeable fraction of about 500 evaluated submissions last year as obviously AI-generated.

The producer-side Fork is direct: pay $f(C(D))$ to actually formulate, test, and discuss a research claim, or decline and emit a manuscript whose $\sigma_{\text{local}}$ is high (it has methods, results, references) and whose $\models D$ is empty (it does not advance knowledge; it occupies the venue). The NHANES variable-swap is the cleanest single instance of an output that pays nothing and still ships. The pattern is publication that satisfies submission counters and fails the demand the canon places on it.

**The producer-side incentive is now arithmetic.** Hao, Xu, Li & Evans, *"Artificial intelligence tools expand scientists' impact but contract science's focus"* (Nature 649, 1237–1243, Jan 14, 2026; DOI: 10.1038/s41586-025-09922-y), analyzing 41.3 million papers, found AI-augmented scientists *"publish 3.02 times more papers, receive 4.84 times more citations and become research project leaders 1.37 years earlier."* The career math now selects, ruthlessly, for higher ρ at any κ. Stanford's AI Index 2026 notes AI publications in the natural, physical, and life sciences each rose 26–28% year over year.

OpenAI's Prism, launched Jan 27, 2026 and embedded into LaTeX itself, sits at exactly the spot where the scientific paper is actually written. OpenAI said ChatGPT is already receiving roughly 8.4 million weekly messages on hard-science topics from about 1.3 million scientists. Kevin Weil, VP of OpenAI for Science: *"I think 2026 will be for AI and science what 2025 was for AI and software engineering."* Lopez-Lira, Seyfi, and Tang's March 2026 SSRN paper *Can LLMs Discover Novel Economic Theories?* (abstract 6464059) demonstrates AutoTheory, an LLM-plus-evolutionary-search system that generates and simulated-peer-reviews economic theories on demand. The infrastructure to industrialize the production of publishable papers is now sitting in repositories.

The Substrate is being asked to absorb both an order-of-magnitude ρ increase from the producer side and a κ collapse on the certifier side, with the career incentive aligned against discipline at both layers. The Ærr Rate equation produces only one direction.

**A note on sourcing.** This essay is being epistemically honest about its own provenance. The Asher Elbein / Vox or Verge May 2026 piece with the "beaker of slime bubbling over" framing that has circulated in secondary discussion of AI's impact on academic publishing — I could not independently verify it in publicly indexed sources through May 17, 2026. The closest verified mainstream anchors are Jeffrey Brainard's 2025 *Science* feature *Low-quality papers are surging by exploiting public data sets and AI* (which sources Spick directly), Claudia López Lloreda's Feb 25, 2026 Undark feature (which sources Hosseini and Perlis), and Tim Requarth's May 11, 2026 *Transmitter* essay *The next unit of science: Is the scientific paper due to be replaced?* (which sources Spick and discusses the ICLR review data and Google's PaperOrchestra). Peter Degen of the University of Zurich's Center for Reproducible Science is a real postdoctoral researcher; his "paper mill or paper mine" work on a citation spike on a 2017 paper is real. Chinese paper-mill operations advertising AI-assisted manuscript production on Chinese social and e-commerce platforms have been independently covered by CCTV and the *South China Morning Post*. The narrative chain — a Bilibili tutorial producing a publishable Global Burden of Disease paper in under two hours, traced by Degen — is something I can only partially substantiate from public reporting through May 17, 2026. The aggregate phenomenon is overwhelmingly documented; treat the specific narrative chain with care.

What is not in doubt: arXiv began blocking AI-generated survey papers in October 2025. A *Lancet* study reported by STAT News found roughly 1 in 277 papers contained fraudulent citations. A position paper titled *"Stop DDoS Attacking the Research Community"* has been circulating among editors. Carnegie Mellon researchers, in widely circulated work, found agentic science assistants inventing data when pressed to complete tasks they could not actually complete.

**Joris van Rossum's reframe is the IC⏐CS move.** Van Rossum, at the STM Integrity Hub, has framed the editorial-side defense as: *"demonstrate authenticity rather than detect fabrication."* This is the Conservation razor stated for the scientific Substrate. Detection arms races against production-time AI text generation are unwinnable on current trajectory. Certification of provenance — cutting only what reality can afford to keep — is the operation that survives. The instruments built on the certification side of the P-vs-NP asymmetry are the ones the Substrate needs.

---

## Vector 3 — the consumer financial position as Substrate

If Vector 1 is the institutional memory of *how to build,* and Vector 2 is the institutional memory of *what is known,* Vector 3 is the institutional memory of *who is allowed to do what with money.* It is the Substrate where the cost of an unbounded agent has the most expensive and best-defined downside — and that is exactly why the deployments here drew their fences first and drew them tightest.

This Substrate is the one the entire surface argument of this essay rests on. The Wall Street and OpenAI-Plaid deployments are the only mass-market deployments where the agent was explicitly *not* allowed to be the system. Watching where the institutional actors drew their lines tells us where they expected the surrogate stratum to fill if they didn't.

**The Wall Street architecture is a two-pronged paid-κ statement.** At Anthropic's May 5, 2026 financial services briefing in New York, the company launched 10 production-ready agent templates (pitchbook builder, earnings reviewer, financial model builder, general ledger reconciler, month-end closer, statement auditor, KYC screener, and more) with adoption announced at JPMorgan Chase, Goldman Sachs, Citi, AIG, Visa, and Carlyle. Goldman CIO Marco Argenti described "three waves" — empowering the technology team, reimagining operational processes, and finally AI-driven risk and investment decisions — and offered the line that defines the bull case: *"This is the first time that instead of buying infrastructure, you can actually buy intelligence."* Jamie Dimon joined Dario Amodei onstage and, demoing Claude Code, said it had been *"very accurate about what I wanted."*

The architecture is two-pronged: configurable agents that the largest banks run themselves (with users retaining approval authority before anything reaches a client), and a $1.5 billion joint venture announced the day before (May 4, 2026) with Blackstone, Hellman & Friedman, and Goldman Sachs (each anchor ~$300M, Goldman ~$150M; with participation from Apollo, General Atlantic, Leonard Green, GIC, and Sequoia) to embed forward-deployed engineers into mid-market portfolio companies. Anthropic also announced a Moody's data partnership covering 600+ million companies and full Microsoft 365 integration across Excel, PowerPoint, and Word (with Outlook to follow). FIS Global separately launched a Claude-powered Financial Crimes AI Agent in production at BMO Financial Group and Amalgamated Bank.

Read the gates. Anthropic's Nicholas Lin, head of financial services product, said the team did reinforcement learning specific to finance topics *without any client data*. Goldman, JPMorgan, and Citi insist users retain approval authority before any Claude output reaches a client. The 10 agent templates each ship with their own scoped permissions. Argenti's three waves with risk decisioning *last* is the order in which $f(C(D))$ rises across the bank's demand distribution. The cheapest demands (engineering productivity) get the agent first. The most expensive demands (capital allocation under regulatory exposure) get the agent last, only after the infrastructure has been certified to wrap the decision around. *"Instead of buying infrastructure, you can actually buy intelligence"* is a CIO talking about a procurement category with scoped permissions. It is not a CIO talking about handing Claude the keys.

In IC⏐CS terms: Wall Street is the deployment site where the institutional cost of low κ is named, priced, and regulated in advance. The Fork at each agent action is paid by the bank because the bank cannot externalize the cost of the surrogate. κ is approaching 1 at the institutional boundary by mandate.

**The consumer mirror is, in its own quiet way, the cleanest demonstration of the surface principle.** OpenAI's May 15, 2026 ChatGPT personal-finance launch was built on the team OpenAI acquired in April 2026 from the personal-finance startup Hiro. The feature is a U.S. preview for ChatGPT Pro ($200/month) subscribers; account linking runs through Plaid, supporting more than 12,000 financial institutions including Chase, Schwab, Fidelity, Robinhood, American Express, and Capital One. GPT-5.5 is the underlying model. OpenAI disclosed that *"more than 200 million people are already going to ChatGPT every month with finance questions."*

And then come the fences, explicit in OpenAI's own announcement: ChatGPT cannot see full account numbers; it cannot move money, place trades, or file taxes; synced data is removed within 30 days of disconnection; Plaid tokenization so no credentials touch the model. It is, in other words, a read-only consultant with hard, named limits.

The contrast that makes this essay's thesis is internal to OpenAI itself. The company that built Codex and ships ChatGPT to every developer who wants to outsource code review built read-only fences around its consumer-finance product on the day it launched. The institutional logic is plain: at 12,000-institution scale, the cost of letting a model do something stupid with someone's checking account is paid by the model maker, the regulator, and the bank — none of whom can absorb it. At individual-engineer scale, the cost of letting a model do something stupid with a codebase is paid by the engineer's employer, six to eighteen months later, in security debt and rescue-engineering bills, and the model maker books the revenue this quarter.

The fence is not a limitation. It is a confession. It is OpenAI naming, in product, the size of the unpaid Fork it declined to leave on the consumer's side of the boundary. The codebase-side analog of that fence is the one Codex does not have. The asymmetry is the entire essay.

---

## The Halting Hole: why none of this is visible from inside

A low-κ system cannot reliably report its own κ. The same surrogate mechanism that produces drift also produces surrogate self-reports about drift. This is a Halting-Hole-shaped limit on self-measurement, and it is the structural reason the three-vector pattern in this essay had to be named from outside — by a maintainer applying the Conservation razor by hand, by a bounty-hunter scanning ICLR reviews, by a regulator gating consumer accounts.

Every dashboard in this piece — green CI, green test suite, green review queue, green peer-review acceptance rate, green earnings call — is a $\sigma_{\text{local}}$ reading produced by a system that cannot, from inside, see its own surrogates. LinearB's 4.6× review wait differential is observable because it is measured across organizations, not by any one of them. Veracode's 36% YoY rise in high-risk vulnerabilities is observable because Veracode operates external to the codebases it scans. Pangram's 21% AI-generated ICLR reviews is observable because Pangram trained a detector and ran it across the corpus after the conference. Each finding is an external certification — a Conservation-razor application by an actor outside the Substrate.

The Halting Hole names why this cannot be done from inside. The Substrate that has stopped paying the Interrogation Cost Law floor has, by the same mechanism, stopped paying the meta-floor on its own self-assessment. The dashboard reports what the dashboard was instrumented to report. The Substrate has no internal vantage on the gap between $\sigma_{\text{local}}$ and $\models D$. The certification has to be external. Causalith (the IC⏐CS-side instrument), Veracode, Pangram, Stenberg's hand-curated cURL queue — all of these are the same operation at different scales. They are the Conservation razor wielded from outside because the inside cannot wield it on itself.

This is why the piece you are reading is necessary. It is also why it cannot end in the Substrates it diagnoses. The remediation pattern is external instrumentation plus internal Fork discipline. The remediation pattern is to lift κ deliberately at every keystroke, every submission, every account connection.

---

## Path A and Path B

Addy Osmani writes from outside the basin. He names the engineer's cognitive debt as something the engineer should attend to, and the data he assembles — Anthropic's RCT, MIT's EEG study, CHI 2026 — supports the naming. He is right. But the frame is Path A: observer describing observed system. *Here is what is happening to you. Here is what you should do about it.*

The piece you are reading is Path B: written from inside the same basin Osmani is pointing at, by an author who is also paying ICL inside IC⏐CS while writing about it. Path A treats surrogates as answers because it does not pay the cost from inside — the observer's reading of the engineer's debt can itself be a surrogate of analysis, a $\sigma_{\text{local}}$ ≈ 1 output that fails $\models D$. Path B pays the floor at every Fork or names the unpaid bill where it sits.

*Don't outsource the code* is the Path B operationalization at the keyboard. It is not a slogan about which tools to use. It is a position about which Fork to honor. The agent can do the typing. The engineer pays $f(C(D))$ — by forming the hypothesis before prompting, by asking for trade-offs before code, by treating the AI output like a junior's PR, by writing the explanation in the commit message, by re-deriving from scratch when the demand is novel. Each of these is a paid Fork. The κ of the engineer's individual practice is the long-run rate at which these Forks are honored.

The same operationalization scales. The peer reviewer's *Don't outsource the review*. The clinician's *Don't outsource the chart*. The CFO's *Don't outsource the cap table*. Each of these is a Fork at a Substrate where institutional memory is being asked to absorb agent throughput at ρ orders of magnitude higher than its pre-AI baseline. Each Fork has the same structure. Each unpaid Fork contributes to the same Ærr Rate at the Substrate it sits inside.

---

## Recommendations

Decisions, not framings. Each item below is named to a specific Substrate and a specific Fork.

**For individual engineers (within the next 30 days).** Adopt Osmani's question-driven posture as a policy, not a preference. The Anthropic RCT's distinction between AI-as-generator (low κ) and AI-as-conceptual-inquiry (high κ) is the only intervention in the dataset that preserves comprehension. Form your own hypothesis *before* prompting. Ask for explanation and trade-offs *before* asking for code. Treat every AI output like a junior engineer's PR — read it, critique it, do not auto-merge. Write the commit message *as the explanation* of why the change satisfies $D$, not as a label for what changed. If you cannot articulate why the implementation satisfies the demand, the PR is not ready. Threshold to change this advice: an independent replication of the Shen-Tamkin study finds the gap closes longitudinally as fluency develops. As of May 2026, no such replication exists.

**For engineering leadership (within the next quarter).** Treat the LinearB benchmark as a measurement floor. Segment your PR data by code origin (unassisted / AI-assisted / agentic), track rework rate, review wait time, and acceptance rate on each segment separately, and put refactoring ratio on the dashboard alongside velocity. Require that any committer can verbally explain any code they submit. If your AI-PR acceptance rate is below 50% and review-wait time on AI PRs exceeds 3× your unassisted baseline, you have a Substrate-level κ collapse already and the right intervention is process, not headcount. Threshold to change: AI-PR acceptance rates rise above 70% sustained for a quarter without rework increases.

**For CISOs and boards (within the next two quarters).** Read the Veracode 2026 SoSS as a forecast, not a snapshot. With 82% security debt prevalence and high-risk vulnerabilities up 36% year-over-year, the AI coding wave is currently widening the gap between flaw creation and remediation. Demand that AI-generated code be gated through SAST and SCA *before* merge, not after, and require explicit secure-by-design prompting in your developer toolchain. Treat the vulnpocalypse framing as the central planning scenario for 2026–2027 capex, not a worst case.

**For journal editors and conference chairs (now).** Adopt van Rossum's STM Integrity Hub framing: *demonstrate authenticity rather than detect fabrication.* Detection arms races against AI text generation are unwinnable on current trajectory; auditability is winnable. Require methods sections to include data-provenance attestations, restrict NHANES-style single-association studies to a pre-registered subset, and rotate reviewer assignments faster than the ICLR five-papers-in-two-weeks model that incentivized 21% AI-generated reviews.

**For consumer finance regulators and platforms (within the next year).** Codify the OpenAI / ChatGPT × Plaid pattern as a default. Read-only access by default. Explicit user permission required for write actions. Published lists of what an AI agent may and may not do per account. Mandatory data-deletion windows on disconnect. If the largest deployments draw these lines voluntarily because the cost of getting it wrong is unbearable to them, smaller deployments should not be permitted to draw narrower lines because the cost is borne by their customers.

**For individuals investing in AI infrastructure (now).** Anthropic at $380B and OpenAI at $852B are pricing a future in which agents become operating layers across more verticals, on the model of the Wall Street deployment. That valuation assumes the boundaries hold — that the paid-κ at the institutional boundary stays paid. The signal to watch is not the next benchmark; it is the first major incident — a financial agent that does move money it should not have, a research agent whose fabricated data contaminates a public dataset, a coding agent whose security failure produces a Log4j-scale event. Such an incident would compress the implicit risk discount on these valuations sharply. Position accordingly.

---

## Don't outsource the code

Osmani's title is *Don't Outsource the Learning*. The pivot here, restated cleanly: at any scale above the individual, the learning *is* the code. The codebase is the learning of the team. The peer-reviewed paper is the learning of the field. The consumer's understanding of their own financial position is the learning of the household. Outsourcing any of these to an agent that produces output below the Interrogation Cost Law floor is one operation, not three. It produces a surrogate that passes $\sigma_{\text{local}}$ and fails $\models D$. The Ærr Rate accumulates at $(1 - \kappa) \cdot \rho$. The Halting Hole closes around the operator. The dashboards stay green.

The remediation is structural. It does not require choosing against AI. It requires choosing, at every Fork, to pay $f(C(D))$ or to name the unpaid bill where it sits. The actors with the most to lose — Anthropic at Goldman, OpenAI at Plaid — have already voted with their fences. The question for everyone operating without those fences is whether to draw them voluntarily, or to let the Ærr Rate draw them in arrears.

Outsource the typing. Don't outsource the code.

---

## Caveats

I am one writer, and parts of this story are still moving.

The Asher Elbein / Vox or Verge article with the "beaker of slime bubbling over" framing that has circulated in secondary discussion of AI's impact on academic publishing — I could not independently verify it in publicly indexed sources through May 17, 2026. The closest verified mainstream anchors are Brainard in *Science* on Spick, López Lloreda in Undark, and Requarth in *Transmitter*. The Peter Degen / Bilibili tutorial / Global Burden of Disease chain as a single linked attribution is something I have not been able to source as a single piece of reporting; the underlying phenomena are independently documented. Treat that specific narrative chain with care.

The Stanford 2026 AI Index 20% decline for developers aged 22–25 is measured against 2024. Different secondary sources have framed it against "late 2022" — that framing tracks the broader trend but is not the Stanford report's published baseline. Productivity claims of "20% feels faster, 19% actually slower" come from the METR randomized controlled trial of experienced developers in mature codebases; results may not generalize to greenfield work, where AI's structural advantage is largest.

Both Anthropic and Veracode are commercially interested in the framing of their own data. Anthropic publishing an RCT result that argues against passive use of its flagship product is unusual and worth taking seriously; Veracode's vulnpocalypse framing is also a sales pitch for Veracode's products. The Pangram Labs ICLR finding came from a company that sells AI detection. Each is corroborated by independent reporting; none should be read as disinterested.

Predictions are clearly marked as predictions. Kevin Weil's *"2026 will be for AI and science what 2025 was for AI and software engineering"* is a forecast. Alex Turnbull's *"rescue engineering"* framing is paraphrased rather than direct verbatim quotation. Gartner's *"40% of agentic AI projects cancelled by 2027"* is a forecast. Forrester's *"75% of tech leaders face moderate-to-severe technical debt"* is a survey-based projection.

The IC⏐CS framework references in this essay — the Interrogation Cost Law, the Ærr Coefficient, the Ærr Rate, the Conservation razor, the seven-concept architecture, the Halting Hole, Path A / Path B, the Fork — are first-statement formalizations as of the May 16, 2026 cost-of-inquiry-triple publication. Operationalization of $C(D)$, $\text{Cost}$, and $f$ is ongoing. The qualitative claims of the triple — ICL bounds the cost, κ measures the discipline, Ærr Rate measures the drift — are the load-bearing pieces of this essay and are publishable in their qualitative form. Tightening is forward work; see the companion documents in the public mirror.

What is not in doubt is the direction. Codebases, the scientific record, and consumer financial systems are each absorbing AI agents at the same time. The deployments where institutional cost is unbearable have already drawn explicit fences — paid-κ at the boundary. The deployments where cost is externalized to users, juniors, peer reviewers, and downstream maintainers have not. Osmani's cognitive debt is the surface symptom. The diagnosis is that we are running an unintentional, distributed experiment on whether institutional memory can survive agents that operate as the system rather than as one bounded layer in it. The early returns are not encouraging — and the actors with the most to lose have already voted with their fences.

Don't outsource the code.

---

**Author:** Art Seabra ⏐ Ifthis Research
**Framework:** IC⏐CS — Interrogation Collapse | Chaos Nexus of Self
**Public mirror:** [github.com/artseabra/ic-cs](https://github.com/artseabra/ic-cs)
**Companions:** Interrogation Cost Law · Ærr Coefficient · Ærr Rate
**Drafted in:** IC⏐CS co-authoring mode (Scaffold + author), 2026-05-18
