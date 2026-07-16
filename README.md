# Adspirer Plugin for Claude Code and Cowork

Cross-platform ad management plugin for Claude. Create, analyze, and optimize campaigns across **Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, Amazon Ads, and ChatGPT Ads** via natural language.

> **Note:** Active development happens in the main repo at [amekala/ads-mcp](https://github.com/amekala/ads-mcp). This repo is the stable plugin source for the Claude plugin directory; its skills, commands, and agent are synced from the main repo.

## Installation

```bash
/plugin install adspirer-ads-agent@claude-community
```

Or browse for it in `/plugin > Discover` within Claude Code (search "ads" or "adspirer").

## What It Does

**400+ tools** across 6 ad platforms:

| Platform | Key Capabilities |
|----------|-----------------|
| Google Ads | Keyword research with live CPC data, Search / PMax / YouTube / Demand Gen campaigns, wasted spend analysis, asset and extension management |
| Meta Ads | Image / video / carousel / Reels / DCO campaigns, creative fatigue detection, audience insights, lead forms |
| LinkedIn Ads | Image / video / carousel / text campaigns, engagement metrics, conversion rules, creative management |
| TikTok Ads | In-feed image and video campaigns, asset discovery and validation |
| Amazon Ads | Sponsored Products / Brands / Display campaigns, keyword and negative-keyword management, budget usage |
| ChatGPT Ads | Campaign management for the ChatGPT ads surface |
| Cross-platform | Conversion tracking audit, connection status, monitoring, usage and quota visibility |

## Plugin Components

### Slash Commands

- `/setup` — connect ad accounts, scan the current folder for brand docs, and write a CLAUDE.md workspace file
- `/performance-review [platform] [time period]` — analyze campaign performance across any connected platform
- `/wasted-spend` — find spend going to non-converting keywords, placements, and audiences
- `/write-ad-copy` — generate platform-compliant ad copy from your brand context
- `/refresh-brand-context` — re-scan brand docs and refresh the workspace file

### Skills & Agent

Thirteen skills, loaded on demand. Two set the ground rules and the rest specialize:

**Foundational**

- **adspirer-agent** — how a paid media agent behaves. Campaigns are created paused, nothing spends without your approval.
- **adspirer-mcp** — the tool-call contract: the router two-step, per-platform account ids, budget units, quota.

**Per platform** — `adspirer-google-ads`, `adspirer-meta-ads`, `adspirer-tiktok-ads`,
`adspirer-linkedin-ads`, `adspirer-amazon-ads`, `adspirer-chatgpt-ads`

**Cross-platform workflows** — `adspirer-launch`, `adspirer-performance-review`,
`adspirer-optimize`, `adspirer-creative`

**Product questions** — `adspirer-docs`

Plus **adspirer-setup** to bootstrap a brand workspace, and **performance-marketing-agent**, a
brand-aware agent with persistent memory across sessions.

Some skills carry `references/` — the TikTok objective/pixel validity matrix, Meta creative specs,
Google campaign types and bidding thresholds — which load only when the agent needs them.

> Skills are generated from [`amekala/ads-mcp`](https://github.com/amekala/ads-mcp) under
> `shared/skills/`. Edit them there, not here.

### MCP Server

Connects to the Adspirer remote MCP server at `https://mcp.adspirer.com/mcp` via OAuth 2.1 with PKCE.

## Data & Privacy Disclosure

- **No hooks**: this plugin registers no lifecycle hooks and observes nothing outside explicit tool calls.
- **No telemetry**: the plugin ships no analytics or tracking code; the only network destination is Adspirer's own API (`mcp.adspirer.com`), reached through the MCP connection you authorize.
- **Guarded writes**: new campaigns are always created **paused** for human review; no tool deletes campaigns or changes budgets without explicit confirmation.
- **Account required**: a free Adspirer account ([sign up](https://www.adspirer.com)) connects your ad platform accounts via each platform's official API.

## Example Usage

**Performance Analysis:**
```
/performance-review google_ads last 30 days
```

**Keyword Research (conversational):**
```
Research keywords for an emergency plumbing business in Chicago
```

**Campaign Creation (conversational):**
```
Create a Google Performance Max campaign for luxury watches
targeting New York with a $50/day budget
```

**Multi-Platform Strategy:**
```
I want to advertise my SaaS product across Google and LinkedIn.
Research keywords for Google Ads and create a LinkedIn sponsored
content campaign targeting marketing directors.
```

## Authentication

On first use, you'll complete an OAuth 2.1 flow to connect your Adspirer account and ad platform accounts. Requires an Adspirer account ([sign up](https://www.adspirer.com)).

## Links

- [Website](https://www.adspirer.com)
- [Docs](https://www.adspirer.com/docs/ai-clients/claude-code)
- [MCP Server Repo](https://github.com/amekala/ads-mcp)
- [Privacy Policy](https://www.adspirer.com/privacy)
- [Terms of Service](https://www.adspirer.com/terms)
- [Support](mailto:abhi@adspirer.com)
