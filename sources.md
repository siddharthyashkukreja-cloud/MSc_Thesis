# sources.md — per-paper key points for the literature review (full-read rebuild)

Notes for writing the lit review (~2k words target). Each paper was read in full where
the text was accessible; entries built from the actual papers, not just abstracts.
For each: the **lines that matter for the thesis** (paraphrasable; verified figures noted),
a `✦ Use for:` line, and flags.

**Sourcing:** `✓full` = full text read · `≈abs` = abstract/secondary only (full text paywalled
or unreachable; content corroborated). **Flags:** `[VERIFY]` confirm a figure/citation ·
`[CANNOT ACCESS]` full text not obtained · `[DUPLICATE]` same work as another entry ·
`[REMOVE?]` low marginal value for a 2k-word review.

## Corrections from the full reads (apply these)
- **Huang, Menkveld & Yu (2021): the "28%→42%" figure was wrong.** Top-5 members' share of CCP exposure rises **27.8% (full sample) → 46.8% (top-1% subsample)**; crowding + volatility together drive **~30%** of the top-100 exposure increases (volatility 17.1%, crowding 12.8%).
- **OFR 2026 = Gadgil, Lumsdaine & Paddrik (2026), OFR WP 26-03**, "Clearing Markets and Client Clearing Services." **OFR 2025 = Heilbron & Tompaidis (2025), OFR WP 25-03.**
- **Galbiati & Soramäki (2013) = Bank of England WP No. 480, "Central Counterparties and the Topology of Clearing Networks."**
- **BCBS-CPMI-IOSCO "Review of Margining Practices" is BIS d537 (final, Sept 2022)**, not d526 (that's the Oct-2021 consultative report).
- **`XGBoostCalibration.pdf` IS Lamperti, Roventini & Sani (2018)** — the same paper as the calibration entry; not a separate work. `[DUPLICATE]`
- **Menkveld duplicates resolved** (see §1): the 2014 Tinbergen "Crowded Trades" = the RAPS 2017 "Crowded Positions" (cite RAPS 2017); SSRN 2367287 "Should Crowded Trades Be Avoided?" is a *separate, unpublished* welfare paper; the 2013 Tinbergen "Central Clearing and Asset Prices" = Menkveld–Pagnotta–Zoican "Does Central Clearing Affect Price Stability?".
- **The ABN AMRO ~$200M loss is NOT in the Riksbank 2025 memo** — drop that attribution (find the real source before citing).
- **Paddrik, Rajan & Young (2020) issue/pages/DOI conflict** — confirm Management Science vol/issue/pages and DOI before citing.

## Trim plan (→ ~22–25 papers for ~2k words)
Dedupe Menkveld (3 crowding entries → 1; merge 2013/2015). Drop/compress `[REMOVE?]`: Borovkova, ESRB-Mitigating (keep one ESRB), Cont 2007, Heckinger-Cox-Marshall (→ model background), Barker. The SV-MJD + jump-measure cluster (Stein–Stein … Lou-Polk-Skouras) lives in the **Model/Data chapter**, not the lit review.

---

## 1. Clearing and CCPs

### Menkveld & Vuillemey (2021) — The Economics of Central Clearing `[core]` ≈abs
- Three rationales for a CCP: **multilateral netting**, **insurance against counterparty default** (CCP as buyer-to-every-seller), **fire-sale mitigation** (orderly default management vs bilateral unwind races) — but the same centralisation can amplify fire sales if margins are procyclical.
- Margin interacts with prices via a **margin-CAPM channel**: higher (procyclical) IM tightens funding, raises required returns, depresses prices.
- **Client clearing is named as an open question** — the tiered structure (client → clearing member → CCP) and its risks are under-studied. This is the thesis's gap.
✦ Use for: §1 opening (three-rationale taxonomy) + the explicit "gap" sentence; H2 motivation.
Flags: [CANNOT ACCESS] body (Annual Reviews paywall); use SSRN 3736580. [VERIFY] page for the "open question" wording (pp. 153–178).

### Paddrik, Rajan & Young (2020) — Contagion in Derivatives Markets `[core]` ✓full (working-paper versions)
- DTCC CDS network of **~900 firms** (26 ICE Clear Credit members + 900+ nonmember clients); a CCAR-type credit shock generates large intraday **variation-margin** obligations.
- **"Soft default"** formalised by a transmission factor τ∈[0,1.5]: when net VM exceeds a firm's liquidity buffer it delays/partially pays/defaults pro-rata, passing stress downstream (equilibrium = greatest fixed point of a monotone map).
- The **CCP, though the most central node, contributes less to contagion than several large peripheral net sellers** of protection; some members/one nonmember each exceed 7× the CCP's marginal contagion.
- Cover-2 nominally adequate, but network spillover can exhaust the guarantee fund (when τ ≥ ~0.95); under a 1.25× shock the CCP is ~4–5× more likely to fail than a typical member. Post-2016 bilateral IM cuts total contagion sharply.
- **No endogenous prices, no LOB, no fire-sale-into-price feedback, no client tier** (clients are pass-through obligations). ← exactly your differentiators.
✦ Use for: the closest modelling cousin — position the thesis against it (endogenous LOB + fire-sale feedback + client tier); waterfall/Cover-2 sizing motivation.
Flags: [VERIFY] published Management Science vol/issue/pages + DOI (sources conflict: 66(8):3603–3616 vs 66(6):3125–3161). WP findings consistent across OFR 16-12 and 17-06.

### Paddrik & Young (2021) — Assessing the Safety of Central Counterparties `[core]` ✓full
- Defines a **CCP stress index** = aggregate margin call / prefunded resources, and a **guarantee-fund breach probability β\*** = P(sum of IM breaches on a day exceeds the whole GF) — a fuller standard than Cover-2.
- From CPMI-IOSCO PQD data (77 CCPs, 2015Q3–2020Q1): margin-call/resources ratio is **heavy-tailed (Pareto)**; estimated annual GF-breach probability **~6.5% (North America) vs ~0.5% (Europe)**.
- COVID 2020Q1: quarterly IM-breach probability rose **8.9% → 27.1%** (North America) — strong positive correlation of breaches (crowding in stress).
- **Cover-2 gives only ~40% partial coverage** for a median CCP; comprehensive coverage needs **~2.5× more GF** per dollar of IM.
✦ Use for: framing the cover-2 sufficiency question; COVID-2020Q1 as the stress benchmark; default-fund adequacy.
Flags: none.

### Barker, Dickinson, Lipton & Virmani (2016) — Systemic Risks in CCP Networks `[opt]` ✓full
- Multi-CCP/multi-GCM simulation (LCH.SwapClear + CME; 101 GCMs in both); IM via VaR/CVaR with volatility-scaled lookback; Cover-2 default fund; a **regime-switching feedback** linking GCM defaults to higher volatility.
- **Liquidity dominates credit:** at the 99th percentile, **IM top-up demands exceed default losses** in dollar terms; default losses stay a small fraction of diversified GCM capital.
- Concludes central clearing does **not** pose a large *credit* contagion threat, but flags **wrong-way risk** (defaults ↔ volatility) — the channel your Almgren–Chriss fire-sale makes endogenous.
- No client tier; no LOB; GCM portfolios imputed, shocks from exogenous rate/FX processes.
✦ Use for: a modelling cousin to differentiate from; supports "liquidity (IM top-ups) is the dominant stress channel" for H2.
Flags: [REMOVE?] — keep to one line if space is tight.

### Borovkova & El Mouttalibi (2013) — Systemic Risk and Centralized Clearing of OTC Derivatives: A Network Approach `[opt]` ≈abs
- Monte-Carlo networks ± a CCP. **Homogeneous** members: the CCP stabilises (its own default ≈ 0). **Heterogeneous** (realistic, size-varied) members: the CCP **raises contagion**, especially for smaller firms, and its own default probability is non-trivial.
- **Stricter clearing-member capital requirements help more than the clearing mandate itself.**
✦ Use for: motivating a *size-heterogeneous* member + client population; "a CCP is not safer for all."
Flags: [CANNOT ACCESS] full text (SSRN/Newton PDF blocked); abstract + Barker et al.'s characterisation. [REMOVE?] tangential.

---

## 1.1 Client Clearing

### Gadgil, Lumsdaine & Paddrik (2026) — Clearing Markets and Client Clearing Services (OFR WP 26-03) `[core/H1]` ✓full
- **Clients = 73% of margin** at the largest US/EU CCPs (Jan 2025); clients reach the CCP only through member intermediaries.
- DTCC CDS data (2010–2022; 1,885 clients, 33 dealers, 12 clearing agents): clearing **improves dealer netting** (~6¢ gross exposure per $ volume uncleared vs ~3¢ cleared) and gives clients better pricing; clients clear more when the **dealer is riskier** and to **reduce margin**.
- **Modal client has a single clearing agent; 87% of cleared client trades clear through an agent ≠ the trading dealer.** Agent provision is a high-fixed-cost, concentrated business → "operational fragilities under stress, especially for those with limited member relationships."
- **Archegos/Credit Suisse:** CS's distressed clients cut cleared positions relative to peers, more so for clients with fewer agent alternatives.
✦ Use for: the core single-agent-dependency fragility; BCM/NBCM structure; H1 motivation; COVID-stress context.
Flags: [VERIFY] exact WP number/date (26-03, Feb 2026). CDS setting (mechanisms generalise to ES; magnitudes may not).

### Galbiati & Soramäki (2013) — Central Counterparties and the Topology of Clearing Networks (BoE WP 480) `[core/H1]` ≈abs
- Models clearing as a network transform (clients → GCMs → CCP). Varying topology from flat (all direct members) to tiered (few GCMs, many indirect clients).
- **Tiering reduces the CCP's number of counterparties / total exposure but concentrates positions in fewer, larger GCMs → larger and more *unpredictable* single exposures** to the CCP.
✦ Use for: the H1 tiering trade-off (diffuse risk → concentrated dependence).
Flags: [VERIFY] exact section/page for the single-exposure claim (BoE PDF fetched but too large to confirm verbatim). Companion: Galbiati & Soramäki (2012), "Clearing Networks," JEBO 83(3):609–626.

### Duffie, Scheicher & Vuillemey (2015) — Central Clearing and Collateral Demand `[core]` ✓full
- DTCC CDS data (~31.5% of single-name market, Dec 2011). **Dealer IM is the binding collateral cost**: dealer-to-dealer IM raises system-wide demand from ~10.2% to ~17.3% of net notional (+69.7%), cleared or not.
- Given dealer IM, **mandatory clearing lowers** system-wide collateral demand (absent CCP proliferation), but **redistributes** it across participants.
- Introduces **VM "velocity drag"** (κ^D=0.5: half of margin sent is "in flight," unusable till next day) + a **precautionary VM buffer** (κ^VM=2× daily net-payment SD); together these VM frictions are **17.1%** of system-wide demand. Largest dealers receive **>$7bn/day** in margin.
- **Client clearing reduces** system-wide demand only if dealers can reuse client collateral; small clients can face *higher* demand. CCP proliferation raises demand; specialised CCPs are more efficient.
✦ Use for: liquidity/collateral demand is the binding cost; VM-timing friction precedent (precautionary buffers / velocity drag); client-clearing distributional effects.
Flags: 2011 CDS data — mechanisms transfer to ES, magnitudes don't.

### Haynes, McPhail & Zhu (2019) — When the Leverage Ratio Meets Derivatives `[core/H1]` ✓full
- The Basel III **leverage ratio is notional-based and ignores netting/collateral**, so for derivatives it is **more likely the binding constraint** than risk-based capital.
- On **S&P 500 E-mini futures options** (2013–2018; Jan-2015 LR disclosure): banks→nonbanks, US→European banks, **customer→house accounts**, low-delta options most affected; short-dated Treasury options (zero LR exposure) show no effect (clean counterfactual). US nonbanks' customer share ~9.6%→~11.9%.
✦ Use for: justify a notional **leverage-ratio constraint** on banking CMs; BCM/NBCM asymmetry; customer→house = shrinking client clearing. (Same instrument as your thesis — ES.)
Flags: [VERIFY] the 9.6/11.9% page. Options result (low-delta) doesn't transfer to your linear futures; use the core findings.

### Acosta-Smith, Ferrara & Rodriguez-Tous (2018/2022) — Bank Capital Regulation and Derivatives Clearing (BoE WP 735) `[core/H1]` ✓full
- Under the LR, a clearing broker must treat a client guarantee "as if it entered the trade directly" — **IM cannot reduce the exposure measure**, a step-change in client-clearing capital cost absent under risk-based capital.
- UK's early LR (Jan 2016, 7 largest UK banks; diff-in-diff): affected dealers cut OTC-IRD client market share by **~2.9pp**, concentrated in **>5-year** maturities; **16.3pp less likely** to provide client clearing in 2016Q1 vs 2015Q1; shed **6–14 clients**; less willing to take new ones.
- LCH SwapClear: only **40–46 of 103–105 members** offer client clearing — client clearing is concentrated in a subset (your BCM/NBCM concentration).
- Framed as an **"unexpected interaction"** between the LR and the G20 clearing mandate.
✦ Use for: client-clearing-specific evidence for shrinking capacity / single-agent dependency; companion to Haynes et al. for the LR constraint.
Flags: cite as Acosta-Smith, Ferrara & Rodriguez-Tous (2022) (updated) or note "2018 WP, updated 2022."

### Heilbron & Tompaidis (2025) — The Impact of CCP Liquidity and Capital Demands on Clearing Members Under Stress (OFR WP 25-03) `[opt]` ✓full
- 11 major CCPs, 6 US G-SIBs. Under stress, CCP demands consume single-digit-to-~25% of stressed CM liquidity (historical peak **32.2%** of avg CM liquid resources, 13.3% of capital).
- **First principal component of max daily VM calls across CCPs explains ~70%** of variation → stress is highly **systematic**; CMs face simultaneous multi-CCP demands (the COVID-type scenario).
- **IM top-ups dominate** moderate-stress demands; DF losses/assessments matter only at extreme shocks. Can't speak to smaller/NBCM members or to clients failing margin (which would burden their BCMs).
✦ Use for: magnitude calibration of CCP demands on members under stress; H2 (IM top-ups dominate); waterfall design.
Flags: [REMOVE?] overlaps the margin/liquidity story; keep one line if kept.

---

## 1.2 Margins and Procyclicality

### Cont (2017) — Central Clearing and Risk Transformation `[core]` ✓full (Norges Bank WP 3/2017 = FSR 21)
- Central clearing **transforms counterparty risk into liquidity risk**: under bilateral trading MtM losses are accounting losses; under clearing the same losses become **realised daily/intraday cash margin calls** drawing on liquidity buffers (solvency-neutral but liquidity-consuming).
- CCP members held **>$400bn** in liquid assets as collateral (2016) — comparable to dealer banks' total liquid assets.
- Stress tests then focused on solvency, **ignoring liquidity** — "misguided": Bear/Lehman/AIG failed on margin calls they couldn't meet, not insolvency. **Recovery tools (assessments, VMGH) are procyclical.**
- Liquidation cost scales **~N^(3/2)** in position size → VaR margins understate large-position cost; argues for a liquidity charge in IM.
✦ Use for: the narrative spine (counterparty→liquidity); VM as the stress channel; N^(3/2) rationale for large-member liquidity stress.
Flags: cite Banque de France FSR 21 (2017), pp. 141–147; open via Norges Bank WP 3/2017 or SSRN 2919260.

### Glasserman & Wu (2018) — Persistence and Procyclicality in Margin Requirements `[core/H2]` ✓full
- GARCH framework: risk-sensitive (conditional) margin tracks current volatility but **destabilises** in stress; the stable alternative is the **unconditional quantile** of price changes = a **through-the-cycle** level. ← directly: your "flat through-the-cycle" regime = their stable benchmark; "reactive EWMA-VaR" = their risk-sensitive one.
- Stable/procyclical margin ratio diverges as confidence→1, governed by a tail exponent κ: **S&P 500 κ ≈ 5.2** (lighter tail, smaller buffer) vs **CDX κ ≈ 2.4** (heavier, larger buffer). At 99% one-day, the unconditional/conditional ratio for the S&P is **~1.17**.
- The EU EMIR **25% APC buffer is about right for equities but too small for credit**; a 10-year lookback only helps if it's a *quantile*, and clustering (extremal index) sets how long a history is needed.
✦ Use for: H2 theoretical anchor + buffer sizing for the ES regime comparison.
Flags: none.

### Murphy, Vasios & Vause (2014) — Procyclicality of Risk-Based Initial Margin Models `[core]` ✓full
- Three implementable metrics: **peak-to-trough ratio**, **n-day** largest margin increase, **stressed n-day** (motivated by the 30-day liquidity horizon).
- On S&P 500: peak-to-trough CV 2.1 / EWMA 1.9 / floored-EWMA 1.7 / HS-VaR 2.2 / **Hull-White 6.2**; 30-day call sizes 1.0%–4.0% of portfolio (HW worst). Models that pass risk-sensitivity (Kupiec) tests can still be very different in procyclicality.
- **SPAN is not intrinsically procyclical** (fixed scan ranges) but its *meta-model* (recalibrating ranges) can be — distinguish intrinsic vs meta-model procyclicality.
✦ Use for: H2 output metrics (directly implementable); 30-day stress horizon; floor/buffer regime calibration.
Flags: none.

### Brunnermeier & Pedersen (2009) — Market Liquidity and Funding Liquidity `[core]` ✓full
- Two-way feedback: tight funding → smaller positions → lower market liquidity → higher volatility. Two named spirals — the **margin spiral** (uninformed financiers raise VaR margins on liquidity-driven drops) and the **loss spiral** — interact **superlinearly**.
- VaR-based margins are **destabilising** (procyclical) when financiers can't tell fundamental from liquidity shocks; the rule m = σ̄ + θ̄|p| embeds this.
- Fig. 1: **S&P 500 futures margins (CME) spiked from ~2–3% to ~12–14%** at 1987, 1990, LTCM 1998, 2007 — the canonical empirical motivation in your exact market. Multiple equilibria → sudden liquidity dry-ups; flight-to-quality concentrates illiquidity in high-margin assets.
✦ Use for: the theoretical spiral behind margin→fire-sale→price-impact; Fig. 1 motivates the ES-futures setting.
Flags: none.

### BCBS-CPMI-IOSCO (2022) — Review of Margining Practices (BIS d537, final, Sept 2022) `[core/H2]` ✓full
- March 2020 = **"the most significant test of the resilience of financial markets since the GFC of 2007–09."**
- VM peaked at **~$140bn (9 Mar 2020)** vs ~$25bn/day in Feb (~460%); equity VM **+2,000%**. Centrally cleared **IM rose ~$300bn (~40%)** end-Feb→mid-March (+$115bn excess collateral); **~90% of the IM rise was core model**, ~10% add-ons.
- IM rose less than volatility; avg peak 5-day IM increase ~one-third; **~half of CCPs had no formal APC framework**; non-cleared SIMM stayed flat (a useful counterfactual).
✦ Use for: H2 March-2020 calibration (IM +$300bn / VM peak); COVID-stress framing.
Flags: [VERIFY] cite **d537** (final, 2022), not d526 (Oct-2021 consultative).

### BCBS-CPMI-IOSCO (2025) — Transparency and Responsiveness of Initial Margin in Centrally Cleared Markets (BIS d590) `[core/H2]` ✓full
- Phase-2 final report. Documents **wide variation in APC practice** (explicit EMIR frameworks vs implicit design choices); names the **three-way tension: coverage vs collateral cost vs responsiveness/procyclicality**.
- Proposals: CCP **margin simulators** for members/clients; disclose lookback, liquidation horizon, confidence, APC approach; a standardised **ΔIM% vs ΔVol%** responsiveness measure; CM→client transparency on how client margins are set. **Outcomes-based** (no hard thresholds).
✦ Use for: H2 regulatory endpoint; framing the design of your margin regimes (responsiveness vs stability).
Flags: none.

### ESRB (2020) — Liquidity Risks Arising from Margin Calls `[core]` ✓full
- "Transformation of credit risk into liquidity risk." Total IM at the four largest EU/UK CCPs rose **~€34bn (>1/3 of pre-crisis)**, **€28bn of it in March**; the IM rise came **mainly from client (not house) portfolios**.
- **Daily VM on euro-area investment funds' derivative exposures quintupled**; **6% of funds** lacked pre-stress liquidity for cumulative VM.
- CMs can apply **counterparty-specific add-ons up to 50%**; most non-banks use **one** client-clearing provider with no backup; **intraday VM gains "trapped"** at CCPs overnight.
- Four recommendations incl. limiting procyclical IM CCP→members **and** members→clients.
✦ Use for: the headline COVID payment-stress facts; CCP→CM→client pass-through; H1/H2.
Flags: none.

### ESRB (2020) — Mitigating the Procyclicality of Margins and Haircuts `[opt]` ✓full
- January 2020 (pre-COVID); **originating statement** of the credit→liquidity transformation; volatility-based margin/haircut amplifies **leverage cycles**.
- **Six APC policy options** (mandatory intraday VM pass-through; IM floors; address client-clearing procyclicality; minimum notice on haircut changes; cash buffers; extend bilateral margining to SFTs). Rejects IM ceilings/corridors.
✦ Use for: APC policy taxonomy; fire-sale externality framing.
Flags: [VERIFY] credit→liquidity sentence appears in both ESRB reports — attribute the originating statement here, the March-2020 facts to the June report. Not a pure duplicate (distinct APC taxonomy), but `[REMOVE?]` if you keep only one ESRB cite.

### Blanck / Riksbank (2025) — The Role of Margins in Centrally Cleared Derivatives Markets `[core]` ✓full
- Organising thesis: **margins reduce counterparty risk at the cost of liquidity risk**; self-reinforcing price spirals (forced sales → lower prices → more margin). March 2020 = "dash for cash."
- **§3.4: CMs pass CCP margin requirements through to clients** (≥ CCP level, plus discretionary add-ons); flags lack of transparency standards on client-margin calculation.
- IM mechanics: **MPOR (liquidation period), confidence level, lookback** drive most IM models; APC tools add a buffer above the core requirement. Waterfall: IM → defaulter DF → CCP SITG → survivor DF.
- **2022 Nordic energy crisis:** SPAN IM (= volatility × price × contract size) soared with power prices; Sweden issued **SEK 250bn** in state credit guarantees to prevent Nasdaq Clearing member defaults (no default occurred).
✦ Use for: margins/liquidity trade-off (accessible cite); CM→client pass-through (§3.4); IM-parameter grounding (MPOR/confidence/lookback) for the Model chapter.
Flags: [VERIFY] the **ABN AMRO ~$200M loss is NOT in this memo** — drop or re-source.

### Jones & Pérignon (2013) — Derivatives Clearing, Default Risk, and Insurance `[opt]` ≈abs
- CME clearing-member data: the major source of CM default risk is **proprietary (house) trading**, not customer trading; **extreme losses of large CMs cluster** (not independent) → systemic concern for DF/waterfall sizing.
- EVT tail characterisation of clearinghouse risk; discusses private insurance (which must price the clustered, non-independent tail).
✦ Use for: correlated-CM-loss evidence (supports Cover-2 sizing + crowding); house vs client risk.
Flags: [CANNOT ACCESS] full (J. Risk & Insurance paywall); abstract only. [REMOVE?] marginal now the Hawkes angle is gone.

---

## 2. Agent-Based Models

### Bookstaber, Paddrik & Tivnan (2014/2017) — An Agent-Based Model for Financial Vulnerability `[core]` ✓full (2017 JEIC version)
- Three-tier funding chain (cash providers → bank/dealers → hedge funds) with **two contagion channels**: asset-price impact **and** an endogenous **haircut/funding spiral** (haircuts rise when a dealer's liquidity ratio falls).
- Fire sales triggered by a **LevMax ≥ LevBuffer ≥ LevTarget** rule (a forced sale returns leverage to buffer) — a direct analogue of your margin-call trigger; linear price impact.
- **Overlapping portfolios** transmit stress: a fund forced to sell the shocked asset also dumps a shared unshocked asset, hitting funds that never held the shocked one ("collateral damage" = crowding).
- Strongly non-linear cascades (10% shock: 74% dampened; 20%: all runs see forced sales); **VaR/leverage-ratio/LCR understate tail risk** because they use historical, non-stressed distributions. "It is the reaction to losses, not the losses, that determines severity."
✦ Use for: the ABM precedent for your margin→fire-sale→contagion mechanics; funding + asset channels; non-Gaussian/anti-static-stress-test argument.
Flags: cite OFR WP 14-05 and/or JEIC (2017) consistently.

### Deloitte (2020) — Agent-Based Modelling for CCP Clearing Risk ("Modelling CCP Resilience") `[overview]` ✓full
- Practitioner white paper (Deloitte + Simudyne + Cloudera), prompted by the **Sept-2018 Nasdaq Clearing default** (17σ power-market move; **€107M = 2/3 of the default fund** lost).
- Architecture = **exactly your thesis's**: 1 CCP + ~60 clearing members; three modules — (1) **LOB financial-market sim** with fundamental/momentum/noise agents, fat tails + volatility clustering calibrated to futures data; (2) **margin-call framework** (IM + VM per step); (3) **default-management** with a **cover-x default fund** + sequential **waterfall** (defaulter margin + DF → mutualise to survivors pro-rata to DF contribution).
- Rationale for ABM over equation-based models: emergence, non-ergodicity, irreducibility under stress; volatility is **emergent** from the LOB (no separate SV model).
✦ Use for: the direct ABM-for-CCP precedent your architecture parallels; methodology justification for ABM; the Nasdaq-2018 fact (cite the event from a primary source too).
Flags: practitioner doc (cite as Deloitte 2020, non-peer-reviewed); "cover-x" is generic — cite **cover-2** from EMIR/regulatory source.

---

## 2.1 Financial Market Simulations

### Majewski, Ciliberti & Bouchaud (2018) — Extended Chiarella (trend + value) `[core]` ✓full
- Three agents: **trend-followers** β·tanh(γM_t) (M_t = EWMA of returns), **fundamentalists** κ(V_t−P_t) (linear, + cubic extension), **noise**; linear price impact dP=λ·D (Kyle's λ).
- **Fundamental V_t is a latent state estimated by a Kalman filter** (EM/Unscented) from prices alone — a "Kalman-filtered fundamental" as *output*, no dividend model. ← your fundamental.
- **Trend horizon fixed externally** (α=1/7 months ≈ 6-month CTA horizon) to avoid conflating trend with mean-reversion. tanh saturation → trend inverts at large signals (fundamentalists dominate).
- When trend dominates, mispricing distribution is **bimodal** (persistent over/under-valuation); calibrated on a 200-year multi-asset panel.
✦ Use for: the value+momentum+noise design; Kalman-filtered fundamental; fixing the momentum horizon.
Flags: none.

### Farmer, Patelli & Zovko (2005) — The Predictive Power of Zero Intelligence `[core]` ✓full
- ZI agents place orders at random in a continuous double auction: market orders (rate μ), limit orders (density α), cancellations (rate δ).
- **Spread law** explains **96% (R²=0.96)** of cross-sectional spread variance with one parameter; **price-diffusion law** explains **76% (R²=0.76)** — both from order-flow rates, no rationality.
- Predicts the **concave (square-root) market-impact** law; institution (the double auction) sets many regularities, not agent intelligence.
✦ Use for: ZI noise-trader baseline; spread/diffusion calibrate directly from order-flow rates; institution-over-rationality argument.
Flags: none.

### Cont, Stoikov & Talreja (2010) — A Stochastic Model for Order Book Dynamics `[core]` ✓full
- LOB as a continuous-time Markov/queueing system: limit orders at distance i arrive at λ(i) (power-law, decreasing in i), market orders at μ, **each resting order cancels independently at θ(i)** (per-order cancellation = your order-lifetime rule).
- Proven **ergodic**; closed-form (Laplace-transform) conditional probabilities (next mid move up/down, fill-before-move, "making the spread").
- Direct **calibration recipe** for the ZI layer from Level-II data (arrival counts per tick; trades per minute; cancellations / queue depth).
✦ Use for: ZI order-arrival/cancellation rules + their estimation.
Flags: cite 2010 (Operations Research); often referenced as the 2008 working paper.

### Cont (2007) — Volatility Clustering in Financial Markets: Empirical Facts and ABMs `[opt]` ✓full
- Recalls the stylised facts (heavy tails; **no linear autocorrelation beyond ~20 min**; volatility clustering = slowly-decaying |return| ACF; volume/volatility correlation).
- **Long-memory vs single-timescale ambiguity:** a superposition of a few exponentials (multiple timescales) mimics power-law |r| ACF; warns against over-claiming true long-range dependence — your documented single-timescale limit.
- Threshold ABM: **feedback + heterogeneity both required** for clustering; investor inertia gives a clustering timescale τ_c=1/q; nonlinear amplification turns ~1.6% input vol into ~20% output vol.
✦ Use for: the stylised-facts list + the long-memory caveat (justifies checking |r| ACF without claiming LRD).
Flags: [VERIFY] year — Springer chapter in *Long Memory in Economics* (Kirman & Teyssière, eds.); often cited 2005 or 2007. [REMOVE?] fits results/limitations better than lit review.

### Vytelingum et al. (2025) — Agent-Based Liquidity Risk Modelling for Financial Markets `[core]` ✓full
- ZI (limit/market/cancel; exponential placement) extended with the **Majewski Chiarella** three-trader structure; order-arrival rate modulated by the directional α-signal.
- **Reflexive fundamental** with accumulated per-trade impact f(Q)=λQ^γ (HSI: λ=0.561, γ≈0.5 — square-root law) → permanent + transient impact **emerge endogenously**.
- Uses the **Almgren–Chriss** efficient frontier to benchmark execution; cost surfaces match Bloomberg TCA; explicitly aimed at **CCP default management / fire-sale** liquidity risk. Calibrated via a **surrogate model (Lamperti 2018)** to a stylised-facts target list.
✦ Use for: the ZI+Chiarella+Almgren–Chriss liquidity framing closest to your thesis (and on a futures market, for CCP default management).
Flags: arXiv:2505.15296 (May 2025) — cite as preprint.

### Cont (2001) — Empirical Properties of Asset Returns: Stylized Facts `[core]` ≈abs
- The canonical stylised facts: **heavy tails (Hill tail index α≈2–5, finite variance, non-Gaussian)**; **absence of linear autocorrelation** beyond ~20 min; **volatility clustering**; gain/loss asymmetry; **aggregational Gaussianity** (kurtosis falls as horizon lengthens); volume/volatility correlation.
✦ Use for: the calibration targets; the kurtosis + autocorrelation tests for the market layer.
Flags: [CANNOT ACCESS] full (Quantitative Finance paywall); facts corroborated across the folder PDFs. (DOI 10.1088/1469-7688/1/2/304.)

### Chiarella (1992) — The Dynamics of Speculative Behaviour `[opt]` ≈abs
- **Fundamentalists** (mean-revert to value) vs **chartists** (trend, tanh-saturating demand); Kyle's-λ price impact. Deterministic core → **Liénard limit cycle** when chartists dominate; bifurcations to chaos.
✦ Use for: the theoretical ancestry of your fundamental + momentum agents.
Flags: [CANNOT ACCESS] full (Annals of OR paywall); reconstructed via Majewski et al.'s faithful derivation. [REMOVE?] can fold into the Majewski cite.

---

## 2.2 Design of Clearing Layer

### Thurner, Farmer & Geanakoplos (2012) — Leverage Causes Fat Tails and Clustered Volatility `[core]` ✓full
- Value-investing funds borrow with margin calls. **No leverage → ~Gaussian returns; with a leverage ceiling, margin calls force selling into falling markets → power-law tails** (γ≈3 at λ_MAX≈7.5 ≈ the US equity margin limit) **+ clustered volatility**.
- Fund demand **flips sign at the ceiling** (buys dips below; forced to sell above) — the proximate cause of crashes; all large drops co-occur with margin calls.
- A **volatility-contingent (procyclical) leverage rule increases** defaults and average volatility vs a fixed limit — individually-rational risk control is collectively destabilising.
✦ Use for: the canonical ABM result that margin/leverage *causes* your stylised facts via fire sales; H2 (procyclical risk control backfires).
Flags: none.

### Aymanns & Farmer (2015) — The Dynamics of the Leverage Cycle `[core]` ✓full
- VaR constraint → **target leverage λ̄=α/σ̂** (σ̂ = backward EMA of volatility): risk underestimated in calm → silent leverage build-up → crash.
- A **cyclicality parameter b**: b=−0.5 recovers standard (procyclical) VaR; **b>0 is countercyclical** and raises stability — but isn't a panacea; stability is **non-monotone in the estimation horizon** (an optimal δ). Fixed leverage limits below target fully stabilise.
- Explicitly contrasts Thurner et al. (hedge funds occasionally at ceiling, LTCM-like) vs here (bank always at target, GFC-like) — your CMs are VaR-constrained levered institutions.
✦ Use for: H2 theoretical scaffold (procyclical vs through-the-cycle); VaR→leverage rule for CM agents.
Flags: none.

### Almgren & Chriss (2000) — Optimal Execution of Portfolio Transactions `[core]` ✓full
- Separates **permanent impact g(v)=γv** and **temporary impact h(v)=ε·sgn+η·v**; minimises E[cost]+λ·Var → efficient frontier.
- Optimal trajectory is **hyperbolic: x_j = X·sinh(κ(T−t_j))/sinh(κT)**, κ=√(λσ²/η); trade **half-life θ=1/κ** independent of horizon T; the static schedule is time-consistent. S&P-type example: κ≈0.6/day, θ≈1.7 days.
- **L-VaR**: liquidity-adjusted VaR depends on impact coefficients → procyclical IM ignoring L-VaR understates liquidation cost in stress.
✦ Use for: the fire-sale impact functions (γ, η) + the hyperbolic liquidation schedule; calibration anchor for ES.
Flags: none.

### (also in §1.1) Haynes, McPhail & Zhu (2019); Acosta-Smith et al. (2018) — the leverage-ratio CM constraint
- See §1.1. ✦ Use here for the *design justification* of a notional leverage-ratio cap on banking CMs.

### Barker et al. (2016) — see §1 (CCP-network model) — design cousin for the clearing layer.

---

## 2.3 Calibration

### Gao et al. (2022) — XGB-Chiarella (PRIMARY method) `[core]` ✓full
- Extended-Chiarella 3-agent dynamics; **Kalman-smoother fundamental** per day; calibrate (κ,β,σ_N), fix (γ,α) for identifiability.
- Loss **D = KS + ΔV + ΔACF1 + ΔACF2** (KS replaces Hill here; weights all 1 as terms are comparable).
- **Surrogate-assisted SMM** (after Lamperti 2018): **XGBoost regressor** predicts D(θ) over a 16,384-point Sobol pool; each active-learning round adds **200 exploitation + 100 exploration** points; **label-clipping** D>1→1; converges in **<5 iterations**. Outperforms EM and GBM across 75 stocks.
✦ Use for: the primary methods cite — surrogate-SMM pipeline, the moment set, explore/exploit + clipping, ABM-beats-GBM-for-clustering.
Flags: none.

### Gao et al. (2022) — HFABM (High-Frequency ABM / flash crash) `[core]` ✓full
- Intraday (100 ms) **E-mini S&P 500** simulator; 5 agents incl a **market maker** (needed for realistic bid-ask). Loss **D = Hill + ΔV + ACF1 + ACF2**, Hill on |returns|, **inverse-block-bootstrap-variance weights** (Franke–Westerhoff).
- Two-stage calibration: **surrogate (Lamperti) → grid search**. Validation via **moment-specific p-value + Moment Coverage Ratio (MCR)** (p>0.05, MCRs often >50–90%). Kalman-smoother fundamental.
✦ Use for: Hill-target loss + bootstrap weighting; the two-stage surrogate→grid workflow; MCR/p-value validation; ES calibration target.
Flags: none.

### Gao et al. (2023) — Deeper Hedging / Chiarella–Heston `[core]` ✓full
- Adds a **Heston-style volatility trader** (demand ∝ √Σ_t) to Extended Chiarella; nests both. Same D = Hill+ΔV+ACF1+ACF2; **grid-search calibration only** (your "grid cross-check"); total stylised-facts distance **0.224** vs GBM 0.514 / Heston 0.554 / Extended-Chiarella 0.520; **GSL-div** validation.
✦ Use for: grid-search cross-check; the SV-extension logic (volatility trader fixes |return| ACF).
Flags: none.

### Lamperti, Roventini & Sani (2018) — ABM Calibration Using ML Surrogates `[core]` ✓full (this is `XGBoostCalibration.pdf`)
- The foundational surrogate algorithm: Sobol pool → label a seed set → **XGBoost** → predict over pool → add **log(budget)** new points from predicted positives → iterate. No surface assumptions; O(|X|) vs kriging O(|X|³).
- Calibration measure can be **binary (KS at 5%) or real-valued (KS p-value)**; surrogate TPR ~95%; parameter-importance comes free from CART splits; **3,750× faster** than the true ABM (Islands model).
✦ Use for: the surrogate-calibration concept; why XGBoost over kriging; KS as a calibration measure.
Flags: [DUPLICATE] `XGBoostCalibration.pdf` = this paper (JEDC 90:366–389). Cite once; distinguish from Gao's XGB-Chiarella (regression + 200/100 explore-exploit vs binary classification + log(budget) sampling).

### Franke & Westerhoff (2012) — Structural Stochastic Volatility: Estimation and Model Contest `[core]` ✓full
- **MSM** with quadratic loss J=(m−m_emp)′ **W** (m−m_emp), **W = inverse bootstrap covariance** (block bootstrap, B=5,000) — the precedent for your inverse-SD moment standardisation.
- Nine moments: ACF of raw returns (≈0), mean |return|, **Hill tail index (5% tail of |returns|)**, ACF of |returns| at lags 1/5/10/25/50/100 (smoothed).
- Introduces the **moment-specific p-value** and **Moment Coverage Ratio (MCR)** validation (both adopted by Gao). Guiding idea: noisier moments get smaller weight.
✦ Use for: block-bootstrap moment weighting; Hill as the canonical tail moment; MCR/p-value protocol; the |return| ACF clustering moment.
Flags: none.

---

## Model Design (Model/Data chapters — not the ~2k-word lit review)

### Stein & Stein (1991) — SV via arithmetic OU volatility `[model]` ✓full(secondary)
- Volatility is mean-reverting **Ornstein–Uhlenbeck** (zero leverage); closed-form price density (log-normal mixture); **power-law tail (~−3/2)** → fatter than GBM.
✦ Use for: the OU/mean-reverting volatility specification in the SV-MJD fundamental.
Flags: none (RFS paywalled; equations verified via secondary source).

### Heston (1993) — SV via CIR variance `[model]` ≈abs
- **Square-root (CIR) variance** with **leverage correlation ρ**; closed-form via characteristic functions; non-negative variance under Feller 2κθ>ξ².
✦ Use for: the Heston-type variance choice + leverage in the SV-MJD alternative fundamental.
Flags: [CANNOT ACCESS] full (RFS paywall); SDEs/formulae corroborated widely.

### Merton (1976) — Jump-diffusion `[model]` ≈abs
- Returns = Brownian diffusion + **Poisson jumps**; diversifiable (idiosyncratic) jumps carry no premium → option price = Poisson-weighted average of Black–Scholes; heavier tails/kurtosis.
✦ Use for: the Poisson jump term (overnight gaps / macro shocks) in the SV-MJD fundamental.
Flags: [CANNOT ACCESS] full (JFE paywall); results corroborated.

### Barndorff-Nielsen & Shephard (2004) — Power & bipower variation `[model]` ✓full
- **Bipower variation** Σ|y_j||y_{j+1}| → integrated variance of the **continuous** part even with jumps; **RV − (π/2)·BPV** consistently estimates **jump** quadratic variation. Feasible jump tests.
✦ Use for: the realised-measure split (continuous vs jump variation) to calibrate SV-MJD from high-frequency ES.
Flags: none.

### Mancini (2009) — Threshold jump estimator `[model]` ✓full
- **Threshold** estimator: returns with (ΔX)²≤r(h) are "no-jump" (indicator → 1_{no jump} as h→0); consistent IV + CLT, no leverage/parametric restriction; gives per-interval **jump times and sizes**.
✦ Use for: extracting per-day jump indicators/sizes from intraday ES returns (alternative/validation to BPV).
Flags: none.

### Huang & Tauchen (2005) — Relative contribution of jumps `[model]` ≈abs
- Daily jump ratio z=(RV−BPV)/RV as a jump test; **jumps ≈ 7% of equity-index total price variance**.
✦ Use for: the calibration target that jumps are a small (~7%) share of total ES variance (constrains λ, jump size).
Flags: [CANNOT ACCESS] full (OUP paywall); 7% figure from the abstract/WP.

### Lou, Polk & Skouras (2019) — A Tug of War: Overnight vs Intraday `[model]` ✓full
- Overnight and intraday returns are **systematically opposing** (e.g., momentum/reversal premia accrue **overnight**; value/profitability **intraday**); they're structurally distinct, not interchangeable.
✦ Use for: justification for **retaining overnight gaps** as a distinct component when calibrating the fundamental.
Flags: none.

---

## Items still flagged for your eyes
- [VERIFY] Paddrik, Rajan & Young (2020) — Management Science vol/issue/pages + DOI.
- [VERIFY] Galbiati & Soramäki (2013) — exact page for the "raises expected single exposure" claim (BoE WP 480).
- [VERIFY] BCBS-CPMI-IOSCO 2022 — cite **d537** (final) not d526.
- [VERIFY] Huang–Menkveld–Yu — use **27.8%→46.8%** (top-5 share) and **~30%** crowding+vol, not 28→42%.
- [VERIFY] Riksbank 2025 — **ABN AMRO $200M is not in it**; re-source or drop.
- [CANNOT ACCESS] full text: Cont (2001), Chiarella (1992), Heston (1993), Merton (1976), Huang & Tauchen (2005), Menkveld & Vuillemey (2021) body, Jones & Pérignon (2013), Borovkova & El Mouttalibi (2013) — points are from abstracts/secondary sources; confirm any quoted number.
