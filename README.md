# Meta Ads, AI Agency Team

Nine AI specialists that run your Meta and Facebook ads like a senior performance
team: a data analyst, a creative analyst, a comment analyst, a media buyer, a
copywriter, two creative briefers, and a reporter, with a team lead that routes it
all. Built by Odylic Media. Free to use and remix.

Pick the path that matches your plan.

## 1. Free, works on any Claude (even the free plan)
No setup, no account connection. You paste your own data, the team analyzes it.
1. Open a new chat at claude.ai.
2. Copy everything in [`claude-ai/free-paste-pack.md`](claude-ai/free-paste-pack.md) and paste it as your first message.
3. Paste your data (an Ads Manager export, your ad copy, or an ad's comments) and ask.

You get the full analysis, copywriting, creative briefs, and reporting. You do not
get live account pulls or the buyer launching ads, those need a paid plan (option 2).

## 2. Connected, Claude Pro or Max (live account, all in Claude chat)
Claude pulls your real numbers and the buyer can launch and scale, no terminal.
1. Get a free token at [pipeboard.co/api-tokens](https://pipeboard.co/api-tokens).
2. In Claude: Settings, Connectors, Add custom connector, paste `https://meta-ads.mcp.pipeboard.co/?token=YOUR_TOKEN`.
3. In Claude: Customize, Skills, upload each skill in [`claude-ai/skills/`](claude-ai/skills) and turn it on.

Full step-by-step: [claude-ai/START-HERE-setup.md](claude-ai/START-HERE-setup.md).

## 3. Power users, Claude Code (one command)
```
/plugin marketplace add peterquads/meta-ads-team
/plugin install meta-ads-team@odylic-media
```
Bundles all 9 skills and the Meta connector in a single step.

## Which one is me?
- Free Claude plan, use option 1.
- Claude Pro or Max and you want Claude connected to your live account, use option 2.
- You already use Claude Code, use option 3.

## Safety
The media buyer can spend real money. It always proposes the changes and waits for
your yes. Nothing happens to your account without approval.

## Under the hood
The frameworks come from how Odylic Media actually runs accounts, credited in
[SOURCES.md](SOURCES.md). Built on the open-source [Meta Ads MCP](https://github.com/pipeboard-co/meta-ads-mcp). MIT licensed.
