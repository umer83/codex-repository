# Shared Codex setup

My local skills, Ponytail with its hooks, and instructions for recreating my plugin setup. Snapshot: November 25, 2026.

## Install

1. Install/update Codex and sign in with your own account. Install Node.js for Ponytail's hooks.
2. With the Codex CLI available, run:

   ```sh
   codex plugin marketplace add umer83/codex-repository
   ```

3. Restart the desktop app, open its Plugins Directory, and select **Umer's Codex setup**. Install **Shared skills** and **Ponytail**. Start a new chat. A private repository requires GitHub access first.
4. Review and trust Ponytail's hooks on your machine. They cover session start, prompt submission, and subagent start. Trust approvals are intentionally not shared. Ask Codex to use Ponytail mode when needed.

If GitHub marketplace registration is unavailable in your app version, clone this repository, open its folder in Codex, and restart the app to discover its repo marketplace. Marketplace support and bundled capabilities vary by app version and account.

Ponytail is fetched from [its original MIT-licensed repository](https://github.com/DietrichGebert/ponytail), pinned to the revision recorded in my local marketplace configuration. Its scripts and hooks stay together; no hook code or trust settings are duplicated here. Review upstream changes before changing the pinned revision.

## Included skills

The **shared-skills** plugin contains 20 skills, copied with their companion files:

- automate, babysit, canvas
- codebase-reuse, codex-quota-optimizer
- create-hook, create-rule, create-skill, create-subagent
- loop, migrate-to-skills
- review, review-bugbot, review-security
- sdk, shell, split-to-prs, statusline
- update-cli-config, update-cursor-settings

These are snapshots of local workflows. Several depend on host-specific tools, Cursor-compatible paths, canvas support, review agents, or automation capabilities. Installing a skill supplies instructions; it does not install the underlying feature. Use those workflows only where the recipient's app supports them. Python 3 is optional unless using the quota optimizer's helper scripts.

## Other plugins to enable

These were enabled locally but are supplied by the app/runtime. Enable the available equivalents from your own Plugins Directory rather than copying cached executable files:

- Codex app tools (`codex-app-tools`)
- Browser (`browser`), Chrome (`chrome`)
- Computer Use (`computer-use`, `unified-computer-use`)
- Visualizations (`visualize`)
- Documents (`documents`), PDF (`pdf`)
- Spreadsheets (`spreadsheets`), Presentations (`presentations`)
- Template Creator (`template-creator`)

Connect external services with your own accounts. This repository does not provision app runtimes, MCP servers, credentials, or connector access.

The local configuration also names MCP servers `chrome-devtools`, `contentful`, `gitnexus`, and `node_repl`. Configure the ones you need separately using their providers' instructions; their configuration and environment variables were not exported.

## Optional global guidance

[guidance/AGENTS.md](guidance/AGENTS.md) contains my general reuse and focused-verification instructions. Review and merge its content into your own global `~/.codex/AGENTS.md` if desired. Do not overwrite existing instructions. Keep project rules in each project's own guidance.

## Updating

After changes are pushed here, refresh the marketplace:

```sh
codex plugin marketplace upgrade umer-codex
```

Update/reinstall the affected plugin in the app if offered, then start a new chat. The snapshot skills do not track their original local folders automatically.

## Privacy and verification

Only selected skill folders and general guidance were copied. The full Codex config, account authentication, secrets, hook trust records, chat history, memories, local project data, and plugin runtime caches are excluded. Hook trust must be established separately on each machine.

The marketplace layout, copied files, and manifests were checked locally. Installation and hook execution on a second account/machine have not been verified.

References: [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins) and [hook documentation](https://learn.chatgpt.com/docs/hooks).

