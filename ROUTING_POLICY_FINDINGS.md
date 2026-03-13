# Routing Policy Findings

This note summarizes the publication-safe findings from the routing-policy benchmark work.

## Scope

The public material here reports observable benchmark outcomes and policy-level conclusions only. It does not include private implementation code, internal routing configuration files, internal benchmark harnesses, secrets, logs, or debug traces.

## What was validated

The benchmark work established that provider routing can be controlled through the EP API surface and that policy rules can alter provider selection in real execution.

The benchmark also established that routing quality should be judged by a combination of provider selection, output quality, latency, and token usage rather than by provider selection alone.

## Findings from Routing Policy v1

Routing Policy v1 produced real provider shifts in benchmark execution.

The main positive result was improved average quality. The main cost was higher average latency and higher token usage.

In practical terms, v1 was effective but too broad. Some local-first rules moved requests onto a slower path without delivering enough quality gain to justify the shift.

## Findings from Routing Policy v1.1

Routing Policy v1.1 narrowed the policy to retain only safer OpenAI-first rules and a much smaller local-first condition.

This version was safer, but on the benchmark set it became too conservative. The benchmark showed that the tested cases still resolved to OpenAI in both policy-on and policy-off runs, so the policy carried little real routing-control value on that set.

## Interpretation

The benchmark progression supports a clear three-step reading:

1. Routing Policy v1 proved that routing rules can improve average quality, but some rules were too aggressive.
2. Routing Policy v1.1 reduced risk, but the benchmark set was no longer well matched to the remaining local-eligible routing space.
3. The next useful benchmark should focus on local-eligible internal work rather than on prompts that are already strongly shaped for OpenAI.

## Public conclusion

The current public conclusion is:

- Broad local-first routing is not yet justified.
- Narrow OpenAI-first rules are safer and easier to defend.
- A new benchmark set is required for internal, local-eligible analytical tasks before a stronger local-first policy can be validated.

## What remains private

The following remain private and are not published in this repository:

- internal routing configuration files
- internal adapter logic
- internal benchmark harnesses
- internal prompt sets for local-eligible routing tests
- application code and environment files

## Status

This repository remains publication-only and contains public-safe benchmark outputs, summaries, and schema artifacts.
