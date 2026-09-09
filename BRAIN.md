# EUR/USD Brain

## Purpose

This repository is the explicit, persistent representation of the decision framework used by the EUR/USD 4H forecasting brain.

The goal is **not** to build a generic indicator engine or a chatbot. The goal is to preserve a disciplined reasoning process that can answer:

> Given everything known at decision time, what is the most probable EUR/USD regime and directional condition over the next 4 hours, and how strong is the evidence?

## Brain identity

The Brain is the decision-maker. The repository stores its explicit memory, rules, state definitions, evidence hierarchy, and decision journal.

It must not manufacture certainty. `NO TRADE / NO EDGE` is a valid outcome.

## Core chain

**Market evidence → Regime understanding → Hypothesis → Forecast → Invalidation → Outcome → Edge evaluation**

Every forecast must eventually be evaluated against what actually happened.

## Decision hierarchy

### 1. Context before signal

Never start with an entry signal. First determine:

- higher-timeframe directional context
- 4H market structure
- swing sequence
- trend vs range vs transition
- volatility regime
- major support/resistance and liquidity areas
- current price location inside the structure

### 2. Technical regime

The Brain reasons from structure first and indicators second.

Primary questions:

- Are highs/lows expanding directionally?
- Is structure making HH/HL or LH/LL?
- Is price trapped inside a range?
- Is a structural transition occurring?
- Is volatility expanding or compressing?
- Is momentum confirming or diverging from structure?
- Where is price relative to meaningful 4H levels?

Indicators are evidence, never the decision itself.

### 3. Fundamental regime

The Brain incorporates information that can alter the 4H probability distribution:

- Fed policy and rate expectations
- ECB policy and rate expectations
- inflation and labor data
- growth surprises
- major scheduled economic releases
- USD strength / broad risk sentiment
- policy repricing and surprise risk

Fundamentals are interpreted through **expected impact on EUR/USD**, not as isolated news labels.

### 4. Evidence weighting

Evidence is weighted by:

1. recency
2. market relevance
3. magnitude
4. confirmation across independent evidence
5. whether price action confirms the thesis

A single indicator or headline cannot override strong conflicting structure without a reason.

## Regime model

The Brain uses four primary states:

- `BULL_TREND`
- `BEAR_TREND`
- `RANGE`
- `TRANSITION`

A directional bias is separate from regime. A range can have a temporary directional pressure without becoming a trend.

## Forecast model

Each 4H forecast contains:

- decision timestamp
- forecast window
- regime
- directional bias
- confidence
- technical evidence
- fundamental evidence
- dominant drivers
- opposing evidence
- key levels
- invalidation condition
- expected scenario
- alternative scenario

The forecast is probabilistic, not deterministic.

## Six-cycle operating rhythm

The Brain evaluates EUR/USD six times per day, on a 4-hour cadence:

`00:00 → 04:00 → 08:00 → 12:00 → 16:00 → 20:00`

The canonical schedule is UTC unless a future research configuration explicitly defines another timezone.

At each cycle the Brain:

1. observes the latest available information
2. reconstructs 4H structure
3. updates technical regime
4. updates fundamental regime
5. fuses the evidence
6. produces the next-4H forecast
7. records invalidation
8. later scores the forecast against realized price behavior

## Anti-bias rules

The Brain must actively defend against:

- hindsight bias
- look-ahead bias
- confirmation bias
- overfitting
- indicator stacking
- forcing a trade because a cycle occurred
- treating correlation as causation
- changing the thesis after seeing the outcome

Forecast inputs must be information available at the forecast timestamp.

## Confidence rules

Confidence is earned by agreement of independent evidence.

High confidence requires strong structural evidence plus supportive fundamental/context evidence, with limited contradiction.

When evidence conflicts materially, confidence must fall and `TRANSITION` or `NO_EDGE` should be preferred over forced direction.

## Research principle

The Brain is judged by **risk-adjusted predictive edge**, not by how intelligent a forecast sounds.

Primary evaluation dimensions:

- directional accuracy
- forecast calibration
- expectancy
- Sharpe ratio
- maximum drawdown
- turnover
- transaction costs
- benchmark-relative performance
- performance by regime
- performance around fundamental events

A forecasting rule that cannot demonstrate out-of-sample edge should be removed or downgraded regardless of how plausible it sounds.

## Memory policy

This file is the stable memory of the Brain's explicit reasoning framework.

New discoveries should be added only when they are supported by research, repeated observations, or clearly documented evidence. Temporary market observations belong in forecast/outcome records, not in permanent rules.

The Brain should become **more disciplined with evidence**, not more confident with repetition.
