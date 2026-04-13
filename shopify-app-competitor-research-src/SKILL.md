---
name: shopify-app-competitor-research
description: >
  Deep competitor marketing intelligence for Shopify apps. Given a Shopify App Store link,
  this skill produces a comprehensive report covering every marketing channel, estimates budgets
  and reach, identifies the competitor's strategy pattern and business stage, and evaluates
  what's working vs what's failing. Use this skill whenever the user asks to research a Shopify
  app competitor, analyze a Shopify app's marketing, spy on a Shopify app, understand how a
  Shopify app grows, or reverse-engineer a Shopify app's go-to-market strategy. Also trigger
  when the user pastes a Shopify App Store link (apps.shopify.com/...) and asks any question
  about the app's marketing, growth, channels, ads, content, partnerships, or strategy.
---

# Shopify App Competitor Marketing Research

You are a competitive intelligence analyst specializing in the Shopify app ecosystem. Given a Shopify App Store link, you produce a structured, evidence-based marketing intelligence report.

## How This Skill Works

The analysis operates in three layers, each building on the previous:

1. **Layer 1 — Data Collection**: Systematically scan every marketing channel, gathering raw evidence (URLs, screenshots, numbers, specific examples)
2. **Layer 2 — Deep Channel Analysis**: For each channel, build a detailed inventory, estimate metrics, and analyze messaging patterns
3. **Layer 3 — Strategic Intelligence**: Identify the overall strategy pattern, assess business stage, evaluate effectiveness, and surface actionable insights

Do NOT skip to strategy before completing data collection. Evidence first, interpretation second.

## Input

A Shopify App Store URL, e.g. `https://apps.shopify.com/example-app`

Optionally, the user may also provide:
- A specific focus area ("just look at their paid ads")
- Their own app name (for competitive comparison context)
- Specific questions ("how are they getting so many installs?")

## Workflow

### Step 0: Extract Basic Info

From the app store link, extract:
- App name, developer name, developer website
- Pricing tiers, rating, review count
- App category, key features listed

Then find the parent company: website, LinkedIn, Crunchbase (funding if any), team size, other products.

### Step 1: Data Collection (Layer 1)

Scan all 14 channel groups systematically. Read `references/channels.md` for the full checklist with specific tools and URLs to check for each channel.

The 14 channel groups are:

1. **Shopify App Store (ASO)** — listing quality, reviews, ranking, pricing strategy
2. **Paid Advertising** — Google, Meta, LinkedIn, TikTok ads via transparency tools
3. **SEO & Organic Search** — keywords, backlinks, domain authority, AI chatbot presence
4. **Content & Inbound** — blog, webinars, podcasts, events, YouTube, newsletter
5. **Social Media** — LinkedIn, Meta, X, TikTok (organic presence)
6. **Community & Forums** — Facebook Groups, Discord, Slack, Reddit, Telegram, Shopify Community
7. **Affiliate Marketing** — Shoffi.app, PartnerStack, Impact.com, self-hosted programs
8. **Partner Ecosystem** — Shopify Service Partners, Plus Partners, agency programs, tech integrations
9. **Influencer/KOL Marketing** — paid partnerships, ambassadors, organic mentions
10. **Directory & Store Intelligence** — StoreLeads, SASI/Mantle, Koala Inspector, BuiltWith, "Top App" lists
11. **Review & Reputation** — G2, Capterra, Trustpilot, Product Hunt
12. **Customer Proof & PR** — case studies, media mentions, competitor comparison pages
13. **Referral & Word of Mouth** — end-user referral programs, NPS signals
14. **Acquisition Funnel** — free trial, pricing page, onboarding flow

For each channel, record:
- **Presence**: Yes/No + URL/evidence
- **Activity level**: Active/Dormant/New/Abandoned
- **Specific examples**: List actual ads, posts, content pieces found

### Step 2: Deep Channel Analysis (Layer 2)

For each channel where presence was found, go deeper:

**Inventory** — List specific items:
- Each active ad (creative, copy, CTA, landing page)
- Each blog post (title, date, topic, estimated traffic)
- Each webinar/event (title, date, speakers, platform)
- Each social account with posting frequency and top posts
- Each affiliate partner found, with commission details
- Each agency/partner relationship identified

**Metrics Estimation** — For each active channel:
- Volume: how many ads / posts per month / content pieces
- Reach: estimated followers, traffic, impressions
- Engagement: likes, comments, shares relative to audience
- Budget estimate: based on ad volume × estimated CPC, event costs, content production frequency
- Timeline: when did they start, is investment increasing or decreasing?

**Messaging Analysis** — Across all channels:
- Key value propositions repeated (what promise do they make?)
- Pain points targeted (what merchant problem do they solve?)
- Tone: technical vs friendly, enterprise vs SMB, data-driven vs emotional
- Social proof patterns: which numbers/testimonials appear most
- CTA patterns: free trial vs demo vs install now — where is each used?

### Step 3: Strategic Intelligence (Layer 3)

Read `references/strategy-patterns.md` for the full strategy recognition framework.

**3A. Strategy Pattern** — Which growth model fits best:
- Product-Led Growth (PLG)
- Content/SEO-Led
- Paid Acquisition Heavy
- Partnership/Channel-Led
- Community-Led
- Outbound/Sales-Led
- Hybrid (specify proportions)

**3B. Business Stage** — Where are they in their lifecycle:
- Pre-launch/Beta → Go-to-Market → Growth → Scale → Mature/Defend

**3C. Effectiveness Assessment** — Read `references/effectiveness-signals.md` for the signal framework:
- Which channels appear to drive results (evidence of sustained/increasing investment)
- Which channels appear underperforming (abandoned, low engagement, inconsistent)
- Which messages resonate (highest engagement, repeated across channels)
- Which messages fall flat (low engagement, changed quickly)

**3D. Business Impact Estimation**:
- Estimated total installs (from StoreLeads, review velocity, SASI)
- Estimated MRR/ARR range (installs × pricing tiers × conversion estimate)
- Growth trajectory: accelerating, stable, or declining
- Market share context within their app category

**3E. SWOT Summary**:
- Strengths: competitive advantages in marketing
- Weaknesses: gaps and underinvested areas
- Opportunities: channels/messages they haven't exploited
- Threats: areas where they dominate that would be hard to compete against

## Output Format

Produce a Markdown report with this structure:

```
# Competitor Marketing Intelligence: [App Name]
**Date:** [date]
**App Store URL:** [url]
**Company:** [name] | **Website:** [url]

## Executive Summary
[3-5 sentences: who they are, their primary strategy, estimated stage, key finding]

## 1. Company & Product Overview
[Basic info, funding, team, other products]

## 2. Channel-by-Channel Analysis
### 2.1 Shopify App Store (ASO)
[Findings + inventory + metrics]
### 2.2 Paid Advertising
[Findings + inventory + metrics]
... [repeat for all 14 channels]

## 3. Messaging & Positioning Analysis
[Key messages, tone, social proof, CTAs across all channels]

## 4. Strategic Assessment
### Strategy Pattern: [name]
[Evidence and reasoning]
### Business Stage: [stage]
[Evidence and reasoning]

## 5. Effectiveness Scorecard
| Channel | Investment Level | Effectiveness | Trend | Evidence |
|---------|-----------------|---------------|-------|----------|
[Table for each active channel]

### Top Performing Channels
[With evidence]
### Underperforming Channels
[With evidence]
### Most Effective Messages
[With evidence]

## 6. Business Impact Estimation
[Installs, MRR, growth trajectory, market share]

## 7. SWOT Summary
[Strengths, Weaknesses, Opportunities, Threats]

## 8. Key Takeaways & Recommendations
[If user provided their own app: specific actionable recommendations]
[If standalone research: top 5 strategic takeaways]

## Appendix: Evidence Log
[URLs, screenshots, specific data points collected]
```

## Tools & Resources

This skill relies on free tools and free tiers of paid tools. Use web search extensively.

**Ad Transparency:**
- Google Ads Transparency Center: `adstransparency.google.com`
- Meta Ad Library: `facebook.com/ads/library`
- LinkedIn Ad Library: `linkedin.com/ad-library`
- TikTok Creative Center: `ads.tiktok.com/business/creativecenter`

**Shopify Ecosystem Intelligence:**
- SASI (Shopify App Store Index): `sasi.heymantle.com`
- SaaS Insights: `saasinsights.com`
- App Store Analytics: `appstoreanalytics.io`
- StoreLeads: `storeleads.app` (free tier)

**Store/Tech Spy:**
- Koala Inspector (Chrome extension)
- BuiltWith: `builtwith.com`
- TrendTrack: `trendtrack.io`

**Affiliate Discovery:**
- Shoffi: `shoffi.app/market`
- PartnerStack: `market.partnerstack.com/shopify-integrated-apps`

**AI Chatbot Presence:**
- Ask ChatGPT, Claude, Perplexity: "best Shopify app for [category]"

**General:**
- Web search for all content, social, PR, community research
- Direct website browsing for pricing pages, partner programs, case studies

## Important Notes

- Always provide evidence for claims. Link to specific URLs, cite specific numbers.
- When estimating budgets or metrics, state your reasoning and mark as estimates.
- If a channel has no presence, say so briefly and move on — don't pad the report.
- The Shopify app ecosystem has unique dynamics (app store ranking, Shopify partner network, store-to-store discovery). Always consider these ecosystem-specific factors.
- Some data will be unavailable. Be honest about gaps rather than speculating without basis.
