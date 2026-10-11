<p align="center">
  <img src="assets/nastech-official-plugins-banner.jpg" alt="Nastech Official Plugins, built and maintained by Nastech Research" width="100%">
</p>

<h1 align="center">Nastech Official Plugins ☤</h1>

<p align="center">
  <b>The official plugins for <a href="https://github.com/NastechResearch/nastech-agent">Nastech Agent</a>, built and maintained by <a href="https://nastechresearch.com">Nastech Research</a>.</b><br>
  One repo, every first-party plugin, installed in one line from the Nastech plugin catalog.
</p>

<p align="center">
  <a href="https://nastech-agent.nastechresearch.com/docs/plugins"><img src="https://img.shields.io/badge/Plugin_Catalog-browse-FFDE1A?style=for-the-badge&labelColor=0B0C0E" alt="Plugin Catalog"></a>
  <a href="https://nastech-agent.nastechresearch.com/docs/"><img src="https://img.shields.io/badge/Docs-nastech--agent-E5DEC9?style=for-the-badge&labelColor=0B0C0E" alt="Docs"></a>
  <a href="https://github.com/NastechResearch/nastech-official-plugins/actions/workflows/tests.yml"><img src="https://img.shields.io/github/actions/workflow/status/NastechResearch/nastech-official-plugins/tests.yml?branch=main&style=for-the-badge&label=tests&labelColor=0B0C0E&color=103CE7" alt="Tests"></a>
  <a href="https://discord.gg/NastechResearch"><img src="https://img.shields.io/badge/Discord-join-E62B28?style=for-the-badge&logo=discord&logoColor=white&labelColor=0B0C0E" alt="Discord"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-E5DEC9?style=for-the-badge&labelColor=0B0C0E" alt="MIT"></a>
</p>

---

## What is Nastech Agent?

[Nastech Agent](https://github.com/NastechResearch/nastech-agent) is the self-improving AI agent from Nastech Research. It writes skills from experience and keeps improving them as it works, remembers what matters across sessions, and runs where you are: the terminal, the Nastech Desktop app, Telegram, Discord, Slack, WhatsApp, Signal and more, all through one gateway. You can bring any model (Nastech Portal, OpenRouter, Anthropic, OpenAI, your own endpoint) and run it on a laptop, a $5 VPS or serverless infrastructure.

```bash
curl -fsSL https://raw.githubusercontent.com/NastechResearch/nastech-agent/main/scripts/install.sh | bash
```

## A lean core, with plugins at the edges

The Nastech core keeps the parts every user needs: the agent loop, memory, skills, the gateway, model routing and the tool runtime. Everything specific to one product, one vendor or one hobby belongs in a **plugin**, which you install when you want it and which ships on its own schedule.

That gives you:

- **Smaller, faster installs.** You don't download a Spotify client to run a coding agent.
- **Fixes without waiting for a release.** A plugin ships a fix as soon as it's reviewed. It doesn't wait for the next Nastech version.
- **A clear owner for each integration.** Vendor plugins live with the vendors who build them, community plugins with their authors, and Nastech's own plugins live here.

## The plugin catalog

The [**Nastech plugin catalog**](https://nastech-agent.nastechresearch.com/docs/plugins) is the reviewed index of everything you can install: model providers, memory providers, messaging platforms, Desktop extensions, voice, web and automation tools. It has hundreds of entries from Nastech, vendors and the community. Each entry is **pinned to a reviewed commit**, so what you install is exactly what was reviewed, and an update moves you only when a new pin passes review.

```bash
nastech plugins search            # browse the catalog
nastech plugins info spotify      # what it does, what it needs, which commit
nastech plugins install spotify   # install at the reviewed pin
nastech plugins update spotify    # follow the catalog to the next reviewed pin
```

Nastech Desktop has the same catalog under **Capabilities → Plugins**.

Catalog entries come in two tiers:

| Tier | Who maintains it | Where it lives |
|---|---|---|
| **official** | Nastech Research | **This repo**, one directory per plugin |
| **community** | Vendors and independent authors | Their own repos, reviewed when they enter the catalog |

## The plugins

<table>
<tr>
<td width="50%" valign="top">
<a href="homeassistant/"><img src="assets/homeassistant.jpg" alt="Home Assistant plugin"></a>
<h3><a href="homeassistant/">Home Assistant</a></h3>
<code>nastech plugins install homeassistant</code>
<p>A gateway platform plus four tools. Nastech watches your Home Assistant event bus, reacts to the state changes you care about, controls devices over the REST API, and replies as Home Assistant notifications. Cron jobs can deliver straight to your phone with <code>deliver=homeassistant</code>.</p>
<p><code>ha_list_entities</code> · <code>ha_get_state</code> · <code>ha_list_services</code> · <code>ha_call_service</code></p>
</td>
<td width="50%" valign="top">
<a href="spotify/"><img src="assets/spotify.jpg" alt="Spotify plugin"></a>
<h3><a href="spotify/">Spotify</a></h3>
<code>nastech plugins install spotify</code>
<p>Seven tools over the Spotify Web API: playback, Spotify Connect devices, the queue, search, playlists, albums and your library, plus <code>nastech spotify login</code> for a loopback PKCE login with your own Spotify developer app. Playback control needs Premium.</p>
<p><code>spotify_playback</code> · <code>spotify_devices</code> · <code>spotify_queue</code> · <code>spotify_search</code> · <code>spotify_playlists</code> · <code>spotify_albums</code> · <code>spotify_library</code></p>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="claude-subscription-directsdk/"><img src="assets/claude-subscription-directsdk.jpg" alt="Claude Subscription DirectSDK plugin"></a>
<h3><a href="claude-subscription-directsdk/">Claude Subscription DirectSDK</a> <sup>experimental</sup></h3>
<code>nastech plugins install claude-subscription-directsdk</code>
<p>A model provider that runs Nastech turns on your Claude Pro or Max subscription through the official Claude Code CLI, with no separate API key or per-token bill. Nastech keeps its own agent loop, tools, approvals and compaction; the plugin drives the logged-in <code>claude</code> binary as a request-scoped model client, and refuses cleanly with an install hint when Claude Code is missing.</p>
<p>Pick it in <code>nastech model</code> → <b>Claude Subscription DirectSDK (Experimental)</b></p>
</td>
<td width="50%" valign="top">
<a href="telegram-business/"><img src="assets/telegram-business.jpg" alt="Telegram Business Mode plugin"></a>
<h3><a href="telegram-business/">Telegram Business Mode</a></h3>
<code>nastech plugins install nastech-telegram-business</code>
<p>Turns Nastech into an observe-with-approval secretary for your Telegram Business account. It drafts replies to your customers, and nothing is sent until you approve it.</p>
<p>Gateway platform add-on · owner approval on every reply</p>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="memory-wiki/"><img src="assets/memory-wiki.jpg" alt="Memory Wiki plugin"></a>
<h3><a href="memory-wiki/">Memory Wiki</a></h3>
<code>nastech plugins install nastech-memory-wiki</code>
<p>A dashboard and Desktop tab that turns your local session history into browsable subject pages and daily logs, plus a read-only audit panel for <code>MEMORY.md</code> and <code>USER.md</code>.</p>
<p>Dashboard tab · reads local history, writes nothing</p>
</td>
<td width="50%" valign="top">
<a href="blender/"><img src="assets/blender.jpg" alt="Blender plugin"></a>
<h3><a href="blender/">Blender</a></h3>
<code>nastech plugins install blender</code>
<p>The official Blender Lab MCP server over stdio, pinned to upstream, with a Blender workflow skill, so Nastech can read and change your Blender scene. Needs Blender 5.1+ with its MCP add-on, Git and uv. Its tools run Python inside Blender, so use trusted workflows.</p>
<p>MCP server + skill · Windows, macOS, Linux</p>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="snyk/"><img src="assets/snyk.jpg" alt="Snyk plugin"></a>
<h3><a href="snyk/">Snyk</a></h3>
<code>nastech plugins install snyk</code>
<p>Scan code (SAST), dependencies, container images, IaC and SBOMs through Snyk's first-party MCP server, with the snyk-security-scan workflow skill. Needs Node.js/npm and a free Snyk account.</p>
<p>MCP server + skill · browser login via <code>snyk_auth</code></p>
</td>
<td width="50%" valign="top">
<a href="touchdesigner/"><img src="assets/touchdesigner.jpg" alt="TouchDesigner plugin"></a>
<h3><a href="touchdesigner/">TouchDesigner</a></h3>
<code>nastech plugins install touchdesigner</code>
<p>Drive a live TouchDesigner session through 404.zero's free twozero MCP server, which runs inside TouchDesigner itself, with the touchdesigner-mcp workflow skill and 20+ reference files (operators, GLSL, audio-reactive, instancing) bundled.</p>
<p>MCP server + skill · TouchDesigner on macOS or Windows</p>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="accent-picker/"><img src="assets/accent-picker.jpg" alt="Accent Picker plugin"></a>
<h3><a href="accent-picker/">Accent Picker</a> <sup>desktop</sup></h3>
<code>nastech plugins install accent-picker</code>
<p>An OKLCH colour wheel in the Nastech Desktop status bar. Drag it and the whole theme retints live, so theme authors can try accents in place. The colour is scratch state and never persisted.</p>
<p>Desktop plugin · status bar + palette commands</p>
</td>
<td width="50%" valign="top">
<h3>More on the way</h3>
<p>Official plugins move in here as they leave Nastech core or join from their own repos. Browse everything else, from Nastech, vendors and the community, in the <a href="https://nastech-agent.nastechresearch.com/docs/plugins">plugin catalog</a>.</p>
</td>
</tr>
</table>


### Already used one of these?

Every plugin here used to live somewhere else: Home Assistant and Spotify were built into Nastech core and then briefly had their own repos, and the rest each had a standalone `NastechResearch/nastech-*` repo. **You don't need to do anything.**

- **You used the built-in Home Assistant or Spotify:** `nastech update`, or the first start after updating, installs the plugin from the catalog with your existing config, env vars and login.
- **You installed it from the catalog:** the catalog now points here, so `nastech plugins update <name>` moves your install to this repo and keeps your files.
- **You installed it by URL** (for example `nastech plugins install NastechResearch/nastech-homeassistant`): reinstall once from the catalog with `nastech plugins install <name> --force` to follow future updates. The old repos are archived and get no new fixes.

## Repository layout

```
nastech-official-plugins/
├── assets/                         # README and catalog art
├── homeassistant/                  # one self-contained plugin per directory
│   ├── plugin.yaml                 #   manifest: name, tools, env vars, Nastech version
│   ├── __init__.py                 #   register(ctx)
│   ├── pyproject.toml              #   plugin dependencies
│   └── tests/                      #   the plugin's own suite
├── blender/                        # portable plugins: plugin.json + mcp.json + skills/
├── accent-picker/                  # Desktop plugins: plugin.yaml + desktop/plugin.js
└── ...
```

Each directory is a complete Nastech plugin. The catalog installs one by `repo` + `subdir` at a pinned commit, and Nastech fetches only that directory (a blobless sparse clone), so installing Spotify never downloads Home Assistant.

## Development

Every plugin is tested against **current Nastech core on Linux, macOS and Windows**, on every push and pull request. A nightly run catches core changes that break a plugin before users see them.

```bash
git clone https://github.com/NastechResearch/nastech-agent
git clone https://github.com/NastechResearch/nastech-official-plugins
cd nastech-official-plugins/spotify
NASTECH_AGENT_REPO=../../nastech-agent PYTHONPATH=../../nastech-agent python -m pytest -q
```

To try your local checkout in a real Nastech, install the directory: `nastech plugins install ./spotify --force`.

**Releasing:** merge to `main`, then open a PR on [nastech-agent](https://github.com/NastechResearch/nastech-agent) that bumps the plugin's `sha:` in `plugin-catalog/<name>.yaml`. The catalog pin is the release; every installed copy moves on its next `nastech plugins update`.

**Issues:** open them here and name the plugin in the title (`[spotify] ...`). Bugs in Nastech core belong on [nastech-agent](https://github.com/NastechResearch/nastech-agent/issues).

## Build your own

Plugins are plain Python with a `plugin.yaml`. Start with the [plugin guide](https://nastech-agent.nastechresearch.com/docs/developer-guide/plugins/) and the [example plugins](https://github.com/NastechResearch/nastech-example-plugins), then [submit yours to the catalog](https://github.com/NastechResearch/nastech-agent/tree/main/plugin-catalog).

---

<p align="center">
  <sub>MIT licensed · Built by <a href="https://nastechresearch.com">Nastech Research</a> · ☤</sub>
</p>
