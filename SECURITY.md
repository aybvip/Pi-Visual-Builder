# Security Policy

## There is no executable code in this repository yet

This repository is a **design specification and a set of static HTML mockups**. It contains no application code, no runtime, no dependencies and no deployed service, so there is **no attack surface** to report on today.

If a genuine security issue is found in something that *does* ship here (for example the static mockup pages), open a GitHub Issue describing it.

## When an implementation exists

Once code is added to this repository, report vulnerabilities **privately** using the **Report a vulnerability** button on the GitHub Security tab. Do not open a public Issue for a vulnerability.

Until that button is configured, contact the maintainer through the contact listed on <https://github.com/aybvip>.

## Proposed security considerations

> The properties below describe the **intended design** in this specification. None of them is implemented or verified yet, and none should be relied upon.

### Plugin security (proposed)
- Plugins are sandboxed — cannot access other plugin state
- External network requests require explicit permission in the manifest
- No direct DOM manipulation (use framework APIs only)
- Obfuscated code is rejected during review

### Data security (proposed)
- Privacy rules enforced at runtime
- PiDCTP on-chain state treated as immutable — the visual builder cannot alter it
- API keys stored encrypted and never exposed to client-side code

### AI agent security (proposed)
- AI actions require user confirmation before execution
- AI cannot modify privacy rules without explicit approval
- AI-generated code is reviewed before deployment
- Rate limiting prevents abuse

## Scope

### In scope
- Anything that ships from this repository's own source tree

### Out of scope
- Pi Network core protocol — report to the Pi team
- Pi Browser — report to the Pi team
- Pi Network Platform API — report upstream
- Third-party services referenced in the specification — report upstream
