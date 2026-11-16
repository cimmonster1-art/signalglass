# SignalGlass — submission draft
Target: #BuildHybridAI 2026 · Web/Chrome · New project begun 17 November 2026 (Brisbane).

## Elevator pitch
A handover that keeps conflicting reports visible, ties human decisions to their evidence, and reopens them when new information arrives—with optional, cited hybrid AI drafts.

## Inspiration
Volunteer event teams receive partial, contradictory reports from different people. A polished summary can conceal the most important fact: nobody has resolved the disagreement. SignalGlass makes uncertainty and the evidence behind a decision part of the handover itself.

## What it does
Synthetic festival reports form an evidence constellation. Replay reveals when a disagreement appeared. A coordinator can choose a source and record a reason, but that decision is valid only for the exact report set reviewed. A new report reopens it. A deterministic handover preserves the original sources and times.

The optional AI draft uses only the visible records and human decision reasons. It cannot change the evidence or decide which source is correct. Topic coverage and citation IDs are validated; unresolved labels come from application state. A conservative certainty-word guard rejects some overconfident phrasing. These checks do not establish factual entailment.

## How we built it
A new standalone HTML/CSS/JavaScript application with SVG visualization and in-memory state. Firebase AI Logic SDK 13 invokes Gemini using ONLY_ON_DEVICE by default or PREFER_ON_DEVICE after explicit consent to Google cloud fallback. Production App Check uses a domain-restricted score-based reCAPTCHA Enterprise key, with enforcement retained. The response's actual inferenceSource is shown verbatim.

Google's libraries are dependencies, and OpenAI Codex assisted with research, design, implementation and testing. No code from ScopeKit, Substrate or Heliora was reused. The source was initially developed under the portfolio repository and packaged as the same project in its standalone Apache-2.0 repository.

## Challenges and learning
AI initially called reported agreement verified. We tightened source attribution and added a conservative rejection guard; we do not claim this eliminates hallucination. Validation also needed case-normalized topic names without relaxing report-ID checks.

The available in-chat browser cannot run the local LanguageModel API. Device-only testing showed an explicit unsupported result, preserving the deterministic workspace. Consented tests returned real cloud outputs with inferenceSource in_cloud. We have not verified successful on-device execution or offline reload and do not claim either in the demo.

## Accomplishments
The complete report-to-decision-to-reopened-decision flow was tested. AI cloud results were generated through enforced App Check, with no billing upgrade. The captioned live-state walkthrough performs the workflow in the actual app and renders its live counters and results; it is a guided visualization, not a desktop screen recording. It uses synthetic data only.

## What's next
Validate on a compatible Chrome device with its local model, improve semantic evaluation and import round-trip coverage, and test with real volunteer coordinators after appropriate consent.

## Built with
JavaScript, HTML5, CSS3, SVG, Firebase AI Logic, Firebase App Check, Gemini, reCAPTCHA Enterprise, GitHub Pages, OpenAI Codex.

## Links
Demo: https://cimmonster1-art.github.io/signalglass/
Source: https://github.com/cimmonster1-art/signalglass
Recorder: https://cimmonster1-art.github.io/signalglass/demo.html
Public YouTube URL: pending upload approval and verification.

## Judge instructions
No login or payment. Load the six-report festival scenario. Choose R01 and record a reason. Add a new West gate report and observe the decision reopen. Move replay to inspect earlier evidence. For AI, click Draft with AI to try device-only. On a browser without the local model, observe the explicit error. With synthetic data only, check Allow Google cloud fallback and generate again. Successful outputs show the actual inference source. Free-tier quota or App Check may limit cloud availability. Use a supported Chrome version and the official Firebase hybrid setup instructions for on-device testing. Public Firebase web configuration is a client identifier; no private Gemini server key or debug token is published.

## Status
Draft only. Registration, public video and final submission not yet completed.
