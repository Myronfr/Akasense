

AkaSense

Akamai v3 Sensor Solver – Autonomous, Deterministic, Self-Healing
Version 0.0.1 — MIT License — Research Use Only

⸻

Background

AkaSense was developed independently over 2  months, starting in early 2025, with no prior access to reference implementations, documentation, or existing toolchains. The implementation is the result of continuous reverse engineering of Akamai’s sensor_data challenge architecture — particularly the v3 deployment class.

The goal of this solver is not circumvention through heuristic matching, but consistent, state-aware resolution of obfuscated JavaScript payloads, including full decryption, runtime flattening, and adaptive VM evaluation under changing conditions.

⸻

On the v3 Sensor Model

Akamai’s v3 sensor system is a multi-layered anti-automation mechanism, delivered via highly obfuscated JavaScript. Key characteristics include:
	•	Dynamically generated sensor_data payloads tied to JA3/JA4 fingerprint anchors
	•	Encrypted instruction graphs with transient VM dispatchers
	•	Per-request mutation of blob structures, XOR layers, function names, and variable order
	•	Conditional PoW segments and time-based validation triggers
	•	Obfuscation applied at both syntax (token) and behavior (flow) level
	•	Server-side integrity binding via cookie, TLS, header, and entropy chaining

The payload is specifically engineered to collapse under analysis. Each instantiation varies across time, IP, entropy index, and TLS properties.

⸻

About the Solver

AkaSense is a deterministic, fully autonomous sensor resolution engine. It does not depend on external fingerprint simulators, browser context, or DOM environments. It is built from scratch in Rust, and executes in a controlled CLI environment with zero external dependencies.

The solver is built to respond to:
	•	Obfuscated control flow (VM flattened or dispatcher-staged)
	•	Variable runtime structure (instruction layout, math chains, PoW embeds)
	•	Payload layer changes (nested or delayed execution, staged challenges)
	•	TLS header/cookie entropy variation (origin, referer, sec-fetch chains)

⸻

Capabilities
	•	Decrypts and resolves Akamai v3 sensor_data payloads in real time
	•	Solves custom JavaScript VM chains with inline bytecode or dispatcher shims
	•	Self-adapts to sensor structural changes (naming, layout, cipher shifts)
	•	Defeats behavioral traps including idle-timers, scope poisoning, and math branching
	•	Neutralizes fingerprint anchors (JA3/JA4, header set, cookie sequences)
	•	Supports >10,000 decryptions per minute in controlled CPU contexts
	•	No runtime browser context required
	•	Output is compatible with Akamai PoW and validation endpoints

⸻

Scope of Use

AkaSense is released under the MIT License for academic, educational, and research purposes only.

It is not intended for use in production environments, scraper deployments, or platform-targeted automation. No support or guarantees are provided outside controlled offline testing contexts.

⸻

License

MIT © 2025 – MyronFr
See LICENSE for details.

