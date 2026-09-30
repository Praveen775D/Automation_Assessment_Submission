# Task 2 — n8n API Integration Workflow

## APIs used
1. Hacker News Firebase API — public, no API key required.
   - `https://hacker-news.firebaseio.com/v0/topstories.json`
   - `https://hacker-news.firebaseio.com/v0/item/{id}.json`
2. Slack — final notification destination. The Slack token is stored in n8n Credentials and is intentionally not included in the exported JSON.

## Flow
`Schedule Trigger → Get HN Top Stories → Select Top 5 → Get Story Details → IF High Score → Build Digest → Discord`

The workflow retrieves the public top-story IDs, selects five IDs, enriches each item with its story details, and routes each story through an IF condition based on `score >= 100`. The digest labels stories as `HIGH` or `NORMAL` and sends the combined result to Discord.

## Error handling
The two HTTP requests use `continueRegularOutput`/continue-on-fail behavior so an individual API failure can be inspected instead of terminating the entire execution silently. The transformation code also preserves error information. A dedicated error branch formats failures for notification.

## Credentials
Create an n8n **Slack API** credential and attach it to the two Slack nodes. Select a channel such as `#morning-brief`. Do not place the Slack token in the workflow JSON or source control.

## Test
The schedule is configured for every hour as requested by the assessment. For a manual test, use **Execute Workflow** in n8n. For a final screenshot, show:
- the complete workflow canvas; and
- one successful execution with the Discord payload/output visible.
