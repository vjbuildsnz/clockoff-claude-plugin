# ClockOff for Claude

One plugin containing eight shared gym workflows and the ClockOff remote MCP
connection. GitHub distributes the package directly; no Anthropic directory
listing is required.

## Claude chat, Desktop and Cowork

1. Open **Customize → Plugins → Add → Add marketplace**.
2. Enter `https://github.com/vjbuildsnz/clockoff-claude-plugin`.
3. Add **ClockOff** from that source.
4. Open the plugin's **Connectors** tab. Add/connect ClockOff and complete your
   own authorised ClockOff gym sign-in.
5. Ask **Start ClockOff**, then **Who am I connected as in ClockOff?** and
   **Show my full morning brief**. Check the gym and source dates.

Alternatively, download the plugin ZIP from
https://github.com/vjbuildsnz/clockoff-claude-plugin/releases and select
**Add → Upload plugin**. The ZIP contains one `.claude-plugin/plugin.json`.
GitHub catalog installs can check for future updates; an uploaded ZIP is a copy
that must be updated through Claude's supported controls.

An account or organisation policy can restrict plugin installation. Installing
the files loads the skills; connecting the service is a separate step. Your own
ClockOff access determines which gym you can read. This package contains no
credentials or gym records and does not grant access to the publisher's gym.

## Claude Code

In a Claude Code conversation:

```text
/plugin marketplace add vjbuildsnz/clockoff-claude-plugin
/plugin install clockoff@clockoff
```

Restart the session or use `/reload-plugins` after installing. Open `/mcp` to
authenticate the plugin's ClockOff connection, then run `/clockoff:setup` or ask
**Start ClockOff**. Keep an existing matching gym connection when supported;
do not configure a second server just to load the skills.

For a folder-only test, clone the repository and run
`claude --plugin-dir /absolute/path/to/clockoff-claude-plugin`.

The included `marketplace.json` is a one-plugin index used for direct GitHub
installation. It is not a submission to Anthropic's public directory.

## Package and updates

The root contains `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json`,
`.mcp.json`, and `skills/<workflow>/SKILL.md`. The eight workflows are clockoff,
setup, gym-daily, gym-members, gym-classes, gym-followups, gym-campaigns and
gym-review. They come from the same ClockOff source used by the other clients.
Claude gets its own documented manifest/MCP adapter rather than another host's
App ID. The plugin name remains **ClockOff**; the version identifies its release.

No hooks, executables, local server, background routines, keys or customer data
are bundled. The MCP service stays hosted by ClockOff. Installing the plugin
does not start monitoring, send member messages, save/publish a campaign or
authorise spending. Draft workflows stop for review.

## First test

Check plugin loading and gym sign-in separately. A successful installation
should show eight skills and one ClockOff HTTP MCP connection. An authenticated
answer should identify your authorised gym and preserve dates/coverage. UI forms
and event subscriptions vary by client; the skills include text fallbacks and
must not claim monitoring is active without actual host/backend acceptance.

## Official instructions

- [Claude chat and Cowork plugins](https://claude.com/docs/plugins/overview)
- [Component support](https://claude.com/docs/plugins/platform-support)
- [Claude Code plugins](https://code.claude.com/docs/en/plugins/overview)
- [Direct distribution](https://code.claude.com/docs/en/plugins/publish)
