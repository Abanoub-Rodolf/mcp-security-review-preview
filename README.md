# MCP Security Review Preview

A free one-skill security preflight for MCP configurations. It runs the open-source `mcp-scan` scanner, stores the unredacted evidence outside the repository with owner-only permissions, validates the report shape, and prints only severity counts.

This is a deliberately limited preview of the paid [MCP Security Review Kit](https://rodolf.gumroad.com/l/mcp-security-review-kit). The full kit contains seven Claude Code skills covering secrets, permission scope, supply chain, transport and egress, prompt injection, privacy, remediation, and a written findings report.

## Install

```bash
mkdir -p ~/.claude/skills
cp -R skills/mcp-security-preflight ~/.claude/skills/
```

Start a new Claude Code session, then ask:

```text
Run the MCP security preflight on the configuration I am reviewing.
```

## Safety boundary

MCP configuration and scanner output can contain credentials, local paths, URLs, and untrusted server metadata. This skill keeps raw evidence out of model-facing stdout. Review the evidence directory only in a trusted local viewer.

## What this preview does not include

- finding-by-finding remediation recipes;
- runtime tool-schema capture or prompt-injection review;
- supply-chain publisher and vulnerability verification;
- privacy and data-flow analysis;
- a prioritized written report.

Those are part of the [full $29 kit](https://rodolf.gumroad.com/l/mcp-security-review-kit).

Built by [Abanoub Rodolf Boctor](https://thynkq.com/about) at [ThynkQ](https://thynkq.com). The automated scanner is [mcp-scan](https://www.npmjs.com/package/mcp-scan), maintained by the same author.

## License

MIT. See [LICENSE](LICENSE).
