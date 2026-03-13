# Local Eligible Benchmark Plan

This note defines the public-safe plan for the next routing benchmark cycle.

## Purpose

The next benchmark will test the part of the routing space where a local backend may be a realistic candidate. The goal is not to expose internal routing logic, internal prompts, or implementation code. The goal is to establish whether a local-first policy can be justified for a narrow class of internal analytical work.

## Why a new benchmark is needed

Earlier routing-policy work produced two important outcomes.

Routing Policy v1 showed that policy rules could change provider selection and improve average quality, but some local-first rules were too broad and could move requests onto a slower path without enough gain.

Routing Policy v1.1 narrowed the rules and became safer, but on the benchmark set it became too conservative. The tested prompts still resolved to OpenAI in both policy-on and policy-off runs, so that set no longer measured the real local-eligible routing space.

A new benchmark is therefore required.

## Scope of the next benchmark

The next benchmark will focus on internal analytical tasks that are more suitable for local-first evaluation.

Publicly describable task categories include:

- internal analysis
- working draft
- private note
- raw analysis
- cost-sensitive analytical work
- internal comparison
- internal memo
- non-public exploratory writing

These categories describe the benchmark surface at a high level only. They do not disclose private prompt wording or internal routing thresholds.

## What the benchmark will measure

The next benchmark should continue to measure:

- provider selection
- output quality
- latency
- token usage
- response stability
- policy-on versus policy-off behavior

The benchmark should also measure whether a narrower local-first policy produces real provider shifts in cases where local routing is actually plausible.

## Public evaluation standard

A local-first rule should only be considered validated if it meets all of the following conditions on a local-eligible benchmark set:

1. It creates real provider shifts.
2. It preserves acceptable output quality.
3. It does not create unjustified latency penalties.
4. It does not expose private implementation details.
5. It can be explained publicly at the policy level without revealing internal mechanisms.

## What remains private

The following will remain private:

- exact internal prompt sets
- internal routing thresholds
- internal benchmark harnesses
- internal adapter logic
- internal routing configuration files
- application code and environment files

## Public goal

The public goal of the next benchmark cycle is simple:

To determine whether a narrow local-first policy can be justified for internal, local-eligible analytical work without weakening quality or introducing unacceptable delay.

## Status

This plan is publication-only. It describes benchmark direction and evaluation scope, not private implementation.
