# Meta Ads, AI Agency Team

Nine Claude skills that run on the [Meta Ads MCP](https://github.com/pipeboard-co/meta-ads-mcp)
and act like a real performance team. Installed via the `odylic-media` marketplace:

```bash
/plugin marketplace add peterquads/meta-ads-team
/plugin install meta-ads-team@odylic-media
```

## Skills (auto-discovered from `skills/`)

| Skill | Role |
|---|---|
| `meta-ads-team` | Team lead, routes work, runs the end-to-end loop |
| `meta-ads-data-analyst` | Performance, diagnoses *why* ROAS/CPA/CPM moved |
| `meta-ads-creative-analyst` | Winning patterns, fatigue, scale-vs-kill |
| `meta-ads-comment-analyst` | Objections, FAQs, social proof, sentiment |
| `meta-ads-media-buyer` | Launches, scales, pauses & reallocates (approval gates) |
| `meta-ads-copywriter` | Hooks, headlines, primary text, test variants |
| `meta-ads-static-briefer` | Designer/AI briefs for static & carousel ads |
| `meta-ads-video-briefer` | Hooks, scripts & shot lists for UGC/video |
| `meta-ads-reporter` | Client-ready daily & weekly recaps |

## Bundled MCP

`.mcp.json` ships the remote Meta Ads MCP (`meta-ads.mcp.pipeboard.co`). Get a free
token at [pipeboard.co/api-tokens](https://pipeboard.co/api-tokens) and authenticate
on first connect. Swap the URL for your own server if you self-host.

## Safety

The media buyer follows a **dry-run → explicit approval → execute → verify** protocol
on every spend-affecting change. Nothing goes live without your yes.

MIT © Odylic Media.
