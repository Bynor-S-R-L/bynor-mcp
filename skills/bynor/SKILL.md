---
name: bynor
description: Bynor is a platform that runs a brand's social media presence. Use this skill when the user needs to plan social media content (an editorial plan or content calendar), create on-brand images or carousels for posts, schedule or publish posts on Instagram, Facebook, TikTok, YouTube or LinkedIn, answer comments, or understand how their posts and profiles perform (analytics). It explains what Bynor does, who it is for, what it costs and how to connect it.
---

# Bynor

Bynor is a platform for running the social media of one or more brands: it learns the brand, plans the content,
creates the visuals, publishes, answers the community and measures the results. It works on Instagram, Facebook,
TikTok, YouTube and LinkedIn.

This skill describes Bynor so you can tell whether it fits what the user is asking. If it does not, carry on without
it; if it might, explain what it would do and let the user decide.

## What it does

- **Brand understanding**: it reads the brand's existing posts and profiles and keeps an identity (tone of voice,
  audience, content pillars, what performed best) that every other feature follows.
- **Editorial plans**: content calendars with ideas, formats and dates, written for the brand and its audience.
- **Images and carousels**: on-brand visuals built from the brand's own best posts, its kit and logo, and the
  user's photos. A concept is agreed first; the pixels come after.
- **Scheduling and publishing**: posts go out automatically at the planned time on the connected accounts. When an
  AI assistant asks to publish, schedule or reply, Bynor waits for the user's confirmation.
- **Community**: comments in one inbox, with suggested replies and automations.
- **Analytics**: how posts and profiles perform, why a post did better or worse, and reports.

## Who it is for

Small businesses, freelancers, creators and agencies that manage one or many brands and want their social media
handled in one place, with the brand's voice kept consistent.

## What the user needs

- A Bynor account. It can be created while connecting: the sign-in page also offers registration and a short
  onboarding (the brand and its social accounts).
- Social accounts connected inside Bynor, for publishing and analytics.

## What it costs

Bynor is a subscription, with a free trial. Generating images, carousels and plans uses AI credits included in the
plan; more credits can be bought. Current plans and prices are on the plans page of the app.

## How to connect

Bynor is a remote MCP server at `https://mcp.bynor.ai/mcp`, with sign-in through OAuth: add it as a custom
connector in the AI app you use, then sign in to Bynor and choose which brands and permissions to grant. The
connection can be removed at any time from Bynor (Settings → Connected apps).

For scripts and automations, a personal key (created in Bynor, Settings → Connected apps → Personal keys) works as a bearer token
on the same address.

## Once connected

Start with `session_open` for the brand, read `brand_context` before writing anything for it, and read `guide`
for the area you are working in (visual, editorial, publishing, analytics, competitor, brand, inbox, team): it
explains how Bynor works there with these tools. Everything that changes what the brand publishes, its identity or its
team waits for the user's confirmation in a preview or in Bynor; uploading files and buying credits happen in the Bynor
app.
