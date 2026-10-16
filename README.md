# Bynor MCP server: social media management from your AI assistant

[Bynor](https://bynor.ai) runs the social media of one or more brands: it learns the brand, plans the content, creates
on-brand images and carousels, schedules and publishes posts, answers comments and measures the results, on
**Instagram, Facebook, TikTok, YouTube and LinkedIn**.

This repository holds the public pieces to use Bynor from an AI assistant: the address of the remote MCP server, a
plugin for Claude Code and one skill, `bynor`, that describes what Bynor does so an assistant can tell when it fits.

- MCP server: `https://mcp.bynor.ai/mcp` (streamable HTTP, sign-in with OAuth)
- Registry entry: [`server.json`](server.json) (`ai.bynor/bynor`)
- Skill: [`skills/bynor/SKILL.md`](skills/bynor/SKILL.md)

## What you can ask

- "Plan next month's Instagram and TikTok posts for my brand."
- "Create a carousel announcing our autumn menu, in our brand style."
- "Schedule the approved posts at the best times of the week."
- "How did last month's Reels perform compared to the month before?"
- "Show me the comments that still need an answer and draft the replies."
- "What are my competitors posting on Instagram this week?"

Areas: brand identity and context, editorial plans, visuals (images and carousels), publishing and scheduling,
analytics and PDF reports, competitors on Instagram, comments inbox, team.

## Connect

You need a Bynor account (there is a free trial) with at least one brand. When you connect you choose which brands the
assistant may see and what it may do.

| Client | How |
|---|---|
| Claude (web and desktop) | Settings → Connectors → Add custom connector → `https://mcp.bynor.ai/mcp` |
| ChatGPT | Developer mode → add an app/connector with the same address, OAuth sign-in |
| Claude Code | `claude mcp add --transport http bynor https://mcp.bynor.ai/mcp`, or this plugin: `/plugin marketplace add Bynor-S-R-L/bynor-mcp`, then `/plugin install bynor@bynor` |
| Codex | `codex mcp add bynor --url https://mcp.bynor.ai/mcp && codex mcp login bynor` |
| Other MCP clients | any client that supports remote streamable-HTTP servers with OAuth |

### Scripts and automations

For a script, a scheduled job or an automation tool, create a **personal key** in Bynor (Settings → Connected apps → Personal keys) and
send it as a bearer token to the same address, for example:

    claude mcp add --transport http bynor https://mcp.bynor.ai/mcp --header "Authorization: Bearer byn_..."

A personal key acts as you, with the permissions you pick (read, create, publish) and an expiry of 30, 90 or 365 days.
It is shown once; you can revoke it at any time.

## Permissions and safety

- **Read** sees the brands you granted. **Create** writes plans, texts and visuals and uses AI credits. **Publish**
  schedules, publishes, deletes and cancels posts and plans, and replies to comments. **Account** (apps only, never a
  personal key) sees, invites and manages the team and edits the brand identity.
- From an assistant, publishing, scheduling, deleting, replying to comments and changes to the brand identity or the
  team are proposals you confirm with a button, in a preview or in Bynor. In a verified app you can instead tell the
  assistant to go ahead, except for the team, the brand identity and TikTok posts, which always wait for your click.
- **With a personal key** (a script, with no person to click), only these run without a click, within the key's
  permissions: scheduling a post, publishing a post now, editing a scheduled post, moving scheduled posts to another
  time, replying to comments, setting up or changing automatic replies, and editing several slides of a carousel (the
  create permission: it uses AI credits). **Everything else waits for a person's click in Bynor**, with a personal key
  too: deleting cards, deleting a plan, deleting posts, deleting files from the Library, cancelling scheduled posts,
  sharing a plan with the client, redoing a plan, moving cards to another plan, opening a competitor, the team, the
  brand identity, and any TikTok post, whose privacy a person chooses.
- Every connection can be removed from Bynor (Settings → Connected apps).

## Pricing

Bynor is a subscription with a free trial. Generating images, carousels and plans uses AI credits included in the
plan; more credits can be bought. Plans and prices: [bynor.ai](https://bynor.ai).

## Privacy, terms and support

- Privacy policy: https://app.bynor.ai/legal/privacy
- Terms of service: https://app.bynor.ai/legal/terms
- Support: info@bynor.ai
