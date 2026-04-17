# Adspirer Plugin for Claude Code and Cowork

Cross-platform ad management plugin for Claude. Create, analyze, and optimize campaigns across **Google Ads, Meta Ads, LinkedIn Ads, and TikTok Ads** via natural language.

> **Note:** Active development happens in the main repo at [amekala/ads-mcp](https://github.com/amekala/ads-mcp). This repo is kept as a stable, minimal plugin source. For the latest tools and skills, install from `amekala/ads-mcp`.

## Installation

```bash
/plugin install adspirer-mcp-plugin
```

Or browse for it in `/plugin > Discover` within Claude Code.

## What It Does

**150+ tools** across 4 ad platforms:

| Platform | Key Capabilities |
|----------|-----------------|
| Google Ads | Keyword research, Search / PMax / YouTube / Demand Gen campaigns, wasted spend analysis, asset and extension management |
| Meta Ads | Image / video / carousel / DCO campaigns, creative fatigue detection, audience insights, lead forms |
| LinkedIn Ads | Image / video / carousel / text campaigns, engagement metrics, conversion rules, creative management |
| TikTok Ads | In-feed image and video campaigns, asset discovery and validation |
| Cross-platform | Conversion tracking audit, connection status, usage and quota visibility |

## Plugin Components

### Slash Commands

- `/campaign-performance [platform] [time_period]` -- Analyze campaign performance across any connected platform
- `/keyword-research [business or keywords]` -- Research Google Ads keywords with real CPC data

### Skills

- **ad-campaign-best-practices** -- Campaign creation workflows, budget guidelines, platform-specific strategies, and safety rules

### MCP Server

Connects to the Adspirer remote MCP server at `https://mcp.adspirer.com/mcp` via OAuth 2.1 with PKCE.

## Example Usage

**Performance Analysis:**
```
/campaign-performance google_ads last 30 days
```

**Keyword Research:**
```
/keyword-research emergency plumbing business in Chicago
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
- [MCP Server Repo](https://github.com/amekala/ads-mcp)
- [Privacy Policy](https://github.com/amekala/ads-mcp/blob/main/PRIVACY.md)
- [Terms of Service](https://github.com/amekala/ads-mcp/blob/main/TERMS.md)
- [Support](mailto:abhi@adspirer.com)
