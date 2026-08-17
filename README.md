# IQ Test

A free, self-contained online IQ test. 38 items across the four cognitive domains
used by the WAIS-5: Verbal Comprehension, Fluid Reasoning, Quantitative Reasoning
and Visual Spatial.

## Scoring

Scored with a three-parameter logistic item response model (3PL) using expected
a posteriori (EAP) estimation against a standard normal population prior.

- Each item carries a difficulty parameter `b` and a guessing parameter `c = 1/k`
  for a k-option item.
- `P(theta) = c + (1 - c) / (1 + exp(-1.7 (theta - b)))`, where 1.7 is the scaling
  constant that makes the logistic ogive approximate the normal ogive.
- Item difficulties are solved so each item's marginal pass rate over the
  population matches its target rate.
- Ability is reported as `IQ = 100 + 15 * theta`, with a 95% confidence interval
  derived from the posterior standard deviation.

Difficulties are anchored to published pass rates where they exist:

| Item | Pass rate | Source |
|---|---|---|
| Wason selection task | 19% | meta-analysis of the abstract task |
| Bat and ball | 25% | Frederick, Cognitive Reflection Test (2005) |
| Widgets / machines | 30% | Frederick, Cognitive Reflection Test (2005) |

Remaining items are calibrated on the same scale relative to those anchors.

## Item sources

- Matrix completion after Raven's Progressive Matrices (1938)
- Mental rotation after Shepard & Metzler (1971)
- Paper folding from the ETS Kit of Factor-Referenced Cognitive Tests
- Wason selection task (1968)
- Cognitive Reflection Test (Frederick, 2005)

## Build

There is no build. `index.html` is a single self-contained file with no
dependencies, no network calls and no tracking. Open it or host it anywhere.

## Licence

MIT
