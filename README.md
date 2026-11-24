# SocialMCP

Cursor plugin that connects your agent to [SocialMCP](https://getsocialmcp.com), a social media calendar for X and LinkedIn, through SocialMCP's hosted [Model Context Protocol](https://modelcontextprotocol.io/) server.

Ask your agent to post what you shipped today, turn a changelog into an X thread, or plan next week's posts. It writes a version for each network, checks it fits, and schedules it. Every post lands on your SocialMCP calendar, where you can review, edit or cancel it before it goes out.

## Install

1. Open **Cursor Settings → Plugins** and search for **SocialMCP**, then click **Install**.
2. Cursor opens SocialMCP's sign-in page. Sign in, then click **Allow**.

Without the plugin, add the server to `~/.cursor/mcp.json` yourself:

<!-- commands:cursor.config -->
```json
{
  "mcpServers": {
    "socialmcp": {
      "type": "http",
      "url": "https://getsocialmcp.com/mcp"
    }
  }
}
```
<!-- /commands -->

## Sign-in

Sign-in is OAuth. Cursor opens SocialMCP's sign-in page the first time it connects; there is no API key or client ID to set up. You approve Cursor once on SocialMCP's consent page, and you can disconnect it at any time on the **Agents** page of your SocialMCP dashboard.

## Before you connect

You need a SocialMCP account ([sign up](https://getsocialmcp.com/signup)) with your X account or LinkedIn profile connected. SocialMCP posts through the official X and LinkedIn APIs: you sign in to each network on its own page, and SocialMCP never sees your passwords.

## What agents can do

| Tool | What it does |
| --- | --- |
| `get_account` | Your connected accounts with their posting slots, your plan's limits and usage, your settings, and the current time in your timezone |
| `check_post` | A dry run: how the post looks on each network, character counts, and whether it fits your plan, without posting |
| `create_post` | Publish now, schedule for a time, or add the post to your next open posting slot. Threads on X, full posts on LinkedIn, images |
| `list_posts` | Posts by date range or status (scheduled, published, failed), page by page |
| `get_post` | One post with its result on each network, including live links |
| `update_post` | Edit the text or time of a post that hasn't gone out |
| `cancel_post` | Stop a scheduled post |
| `retry_post` | Post again to the networks where a post failed |
| `delete_post` | Remove a post from SocialMCP (not from the networks) |
| `upload_image` | Store an image from a URL or base64 to attach to posts |
| `set_posting_times` | Set each account's recurring posting slots |
| `update_settings` | Change your timezone, default networks and posting options |
| `connect_account` | A link to connect another X or LinkedIn account |
| `open_dashboard` | A signed-in link to your calendar or one post |

Publishing now can't be undone from SocialMCP: the post goes live on each network straight away. Scheduled posts can be edited or cancelled until they go out.

## Example prompts

- "Post what I shipped today to X and LinkedIn, tomorrow at 9am."
- "Turn the changelog in CHANGELOG.md into an X thread for Monday at 10am."
- "What do I have scheduled this week?"
- "Move my next post to Friday afternoon."

## Support

- Docs: [getsocialmcp.com/docs/mcp](https://getsocialmcp.com/docs/mcp)
- Email: [hello@getsocialmcp.com](mailto:hello@getsocialmcp.com)
- [Privacy](https://getsocialmcp.com/privacy) · [Terms](https://getsocialmcp.com/terms)

## License

[MIT](LICENSE)
