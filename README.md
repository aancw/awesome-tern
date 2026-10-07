<!-- Generated from list.yml by tools/awesome_tern.py. Edit list.yml, not this file. -->

# Awesome Tern

> Plugins, apps, tools and resources for [Tern](https://stencil.so/tern), Stencil's terminal.

Tern is a Rust-native terminal from [Stencil](https://stencil.so). Shells, [omp](https://omp.sh) agents and browser panes keep running in a daemon when the window closes, and come back after a reboot. One session can be open on the desktop app, on iOS and in a WebGPU browser tab at the same time; typing in one shows up in the others.

Plugins are written in Luau, and any program can draw native UI through the Tern Surface Protocol (TSP). `tern remote serve` serves a remote machine's sessions over QUIC. Tern is in closed beta; you get in through the [waitlist](https://auth.stencil.so/waitlist?app=tern).

## Contents

- [Plugins](#plugins)
  - [Command lenses](#command-lenses)
  - [Blocks](#blocks)
  - [Window and workflow](#window-and-workflow)
  - [Official examples](#official-examples)
- [Native TSP apps](#native-tsp-apps)
- [Agent integrations](#agent-integrations)
- [SDKs and protocol libraries](#sdks-and-protocol-libraries)
- [Official resources](#official-resources)
  - [Documentation](#documentation)
- [Nix and dotfiles](#nix-and-dotfiles)

## Plugins

Tern plugins are written in Luau and can be installed directly from GitHub with `tern plugin install github.com/OWNER/REPO`. See the [plugin CLI reference](https://docs.stencil.so/tern/reference/cli.html) for the available commands.

### Command lenses

A lens captures a shell command's output and shows it as a native view. A Raw toggle shows the original text.

- [tern-jj](https://github.com/resYuto/tern-jj) ★ 1 · 2026-10-04 - Displays `jj status` and `jj st` output as a read-only native card with added, modified and deleted files colored to match the Tern theme.

### Blocks

- [tern-spotify (Windows)](https://github.com/NaC-L/tern-spotify) ★ 3 · 2026-10-06 - Floating player for the Windows Spotify desktop app with cover art, playback controls, search, keyboard shortcuts and the current track in the status line.
- [tern-CDP-tidal](https://github.com/H4vC/tern-CDP-tidal) ★ 2 · 2026-10-06 - Player block for the TIDAL desktop app, driven over the Chrome DevTools protocol, with cover art, playback, seeking, volume, shuffle, repeat and line-based search.
- [tern-video-block](https://github.com/verticalrectangle/tern-video-block) ★ 2 · 2026-10-05 - Opens video files in a block with mpv sound, frame stepping and synced side-by-side playback using ffmpeg and the kitty graphics protocol.
- [tern-pokemon](https://github.com/ITSyndicate25/tern-pokemon) ★ 1 · 2026-10-07 - Ports vscode-pokemon to a block where Pokémon walk, sit and get petted on themed beach, forest and castle scenes, drawn natively with animated GIF sprites and no web view.
- [tern-spotify](https://github.com/rico-vz/tern-spotify) ★ 1 · 2026-10-04 - Player block for the Spotify desktop app with cover art, playback, seeking and volume controls on macOS, Windows and Linux.
- [tern-office-preview](https://github.com/zerx-lab/tern-office-preview) ★ 0 · 2026-10-06 - Previews Word and Excel files natively in a block using a Rust renderer, with no Office, browser or LibreOffice involved.

### Window and workflow

Window plugins add commands, keybindings, layouts, and status-line segments.

- [herdr-tern-plugin](https://github.com/gabrielmoreira/herdr-tern-plugin) ★ 2 · 2026-10-05 - Adds an Open Herdr Session command that picks an existing herdr session and attaches to it inside Tern without copying or converting workspaces.
- [tern-ide layout](https://github.com/plumj-am/nixos/blob/master/packages/tern-plugins/layout.nix) ★ 2 · 2026-10-06 - Window plugin with an IDE-style four-pane layout, set split ratios, and an omp pane, packaged with Nix inside a NixOS config.
- [tern-jj workspaces](https://github.com/plumj-am/nixos/blob/master/packages/tern-plugins/jj.nix) ★ 2 · 2026-10-06 - Creates, opens, removes, and inspects jj workspaces using Tern dialogs, tabs, and the status line, packaged with Nix inside a NixOS config.
- [tern-mizu](https://github.com/ITSyndicate25/tern-mizu) ★ 1 · 2026-10-07 - Paints the Mizu Icons VS Code file icon theme over the Files pane, with 893 icons covering 847 file names, 947 extensions and 1457 folder names.
- [tern-model-usage](https://github.com/azmifarih/tern-model-usage) ★ 1 · 2026-10-04 - Shows omp coding-plan quota for each signed-in account in the status line and opens a canvas pane with provider cards and reset countdowns.
- [font-default](https://github.com/getpipher/font-default) ★ 0 · 2026-10-06 - Makes the Reset font size command return to your configured size instead of Tern's built-in default.
- [tern-claude-usage](https://github.com/zerx-lab/tern-claude-usage) ★ 0 · 2026-10-06 - Shows Claude Pro and Max usage limits in a panel and a status-line segment, with 5-hour and 7-day windows, per-model limits, pace tracking and reset countdowns.
- [tern-close-plugin](https://github.com/yumosx/tern-close-plugin) ★ 0 · 2026-10-05 - Adds palette commands that close the other tabs and the split blocks left, right and around the focused block, each row hidden while it would close nothing.
- [tern-file-paste](https://github.com/vokativ/tern-file-paste) ★ 0 · 2026-10-06 - Uploads copied local files from macOS, Linux, and Windows to remote hosts over SSH and inserts their paths into Tern panes.
- [tern-status](https://github.com/getpipher/tern-status) ★ 0 · 2026-10-06 - Status line in the style of tmux with CPU, memory, battery, network, disk and clock segments drawn with Tern's own icons and theme tones.
- [tern-usage-monitor](https://github.com/rico-vz/tern-usage-monitor) ★ 0 · 2026-10-06 - Floating or docked panel showing usage for every omp linked account, with per-account quota bars, auto-refresh, ordering and update-time settings.

### Official examples

These examples ship with the official [SDK archive](https://docs.stencil.so/tern/tern-sdk.tar.gz). They are a good starting point if you are writing your own plugin.

- [Terraform Plans](https://docs.stencil.so/tern/examples/terraform.html) - Lens for `terraform plan` and `tofu plan` that shows badges, diagnostics and resources grouped by action.
- [Review Queue](https://docs.stencil.so/tern/examples/review-queue.html) - Block that polls `gh` every two minutes and lists pull requests waiting for your review.
- [JSON Explorer](https://docs.stencil.so/tern/examples/jsonx.html) - Opens JSON and GeoJSON files as collapsible trees and copies the jq path of a node.
- [Long-Running Commands](https://docs.stencil.so/tern/examples/longrun.html) - Shows a toast when slow commands finish, keeps a history of run times and status, and adds a status-line segment.
- [Directory Variables](https://docs.stencil.so/tern/examples/dirvars.html) - Loads approved `.tern-env` files into new shells and signals when a directory's environment changed.
- [Project Workspaces](https://docs.stencil.so/tern/examples/workspaces.html) - Builds named tabs and split panes from `.tern/workspace.json`.
- [Canvas Dashboard](https://docs.stencil.so/tern/reference/api-window.html#canvas-cx) - Window-only persistent dashboard that shows canvas ownership, keyed patches, and a Refresh action.

## Native TSP apps

Applications that draw their own user interface natively inside Tern using the Tern Surface Protocol (TSP).

- [oh-my-pi (omp)](https://github.com/can1357/oh-my-pi) ★ 34494 · 2026-10-07 - Stencil's coding agent that Tern is built around, drawing its transcript and UI natively, restoring sessions, and opening web pages as browser picture-in-picture panes.
- [Hermes for Tern](https://github.com/thefullctx/hermes-for-tern) ★ 7 · 2026-10-06 - Unofficial Tern frontend for Hermes Agent that draws the conversation, tool rows, subagents, buttons and a docked composer natively over TSP, and leaves the normal Hermes interface alone in other terminals.
- [Octet](https://github.com/skaft-software/octet/pull/485) ★ 7 · 2026-10-05 - Coding-agent shell rendering transcript cards, split diffs, pickers, and reports through TSP; Tern support is merged into the integration branch for 0.8.2 but not in the latest 0.8.1 release.
- [mantern](https://github.com/theblazehen/mantern) ★ 5 · 2026-10-05 - Drop-in `man` replacement that draws pages natively in Tern over TSP, with a synopsis card, option cards, tables, foldable sections and clickable SEE ALSO links, and falls back to the system `man` elsewhere.
- [rmon](https://github.com/pgkt04/rmon) ★ 5 · 2026-10-07 - Resource monitor for Linux and macOS with CPU, GPU, memory, network, disk and process panels and a disk benchmark, drawn natively in Tern over TSP.
- [saavy](https://github.com/saavy1/saavy_cloud) ★ 1 · 2026-10-05 - Persistent coding agent on Cloudflare with a native TSP frontend in Tern and a `pi-tui` fallback elsewhere.
- [Terngram](https://github.com/d3d0n/terngram) ★ 0 · 2026-10-05 - Unofficial keyboard-driven Telegram client built on TDLib and omp's UI toolkit, also installable as a Tern plugin.

## Agent integrations

- [omp-side](https://github.com/wolfiesch/omp-side) ★ 6 · 2026-10-04 - Adds a `/side` command to fork the conversation into a child session and open it in a side pane in Tern, cmux, tmux, WezTerm, Kitty, and Ghostty.
- [tern-mcp](https://github.com/NaC-L/tern-mcp) ★ 2 · 2026-10-03 - Python MCP server over stdio wrapping the tern CLI with 14 tools for sessions, panes, capture, process inspection, input and layout.
- [tern-control](https://github.com/wolfiesch/tern-control) ★ 1 · 2026-10-01 - An omp and Pi extension giving agents tools to find Tern sessions, read transcript digests, follow daemon events, change layout, and type into terminals.
- [omp-thinking-translator](https://github.com/Mouriya-Emma/omp-thinking-translator) ★ 0 · 2026-10-02 - An omp extension that translates visible thinking into collapsible native sections in Tern and plain ANSI output in other terminals.
- [pi-tern](https://github.com/Ghost-9/pi-tern) ★ 0 · 2026-10-07 - Makes the pi coding agent Tern-aware with the TSP handshake, native Mermaid diagrams, browser automation, pane capture and a session mirror.

## SDKs and protocol libraries

- [Tern SDK](https://docs.stencil.so/tern/tern-sdk.tar.gz) - Official archive containing Luau type definitions (`tern.d.luau`) and example plugins.
- [tern-sdk](https://github.com/stencil-hq/tern-sdk) ★ 19 · 2026-10-07 - Official repository of Surface Protocol SDKs for Rust, Python, Go and TypeScript, plus example plugins.
- [@oh-my-pi/pi-wire](https://github.com/can1357/oh-my-pi/tree/main/packages/wire) ★ 34494 · 2026-10-07 - TypeScript package implementing the TSP wire format: APC framing, component types, frame operations, handshake and events.
- [@oh-my-pi/pi-tui](https://github.com/can1357/oh-my-pi/tree/main/packages/tui) ★ 34494 · 2026-10-07 - TypeScript UI toolkit from omp for rendering transcripts, chat, dashboards, and pickers natively over TSP.
- [octet-tern](https://github.com/skaft-software/octet/tree/9e8abda1f4f210d43361b6c0a80e482097feff77/crates/octet-tern) ★ 7 · 2026-10-05 - A Rust TSP client built into Octet with wire types, APC chunking, tty flow control, and scene builders.

## Official resources

- [Tern](https://stencil.so/tern) - Stencil's product page for Tern with a feature tour.
- [Waitlist](https://auth.stencil.so/waitlist?app=tern) - Sign up for Tern's closed beta using a Stencil account.
- [Beta builds](https://build.stencil.so/tern) - CI-generated beta builds from the `main` branch, requiring sign-in.
- [Stencil on GitHub](https://github.com/stencil-hq) - Stencil's GitHub organization; Tern's source is not public.
- [@stencil_labs](https://x.com/stencil_labs) - Stencil's account on X.
- [@_can1357](https://x.com/_can1357) - Stencil founder Can Bölük on X, where he posts most Tern announcements.
- [omp Discord](https://discord.gg/4NMW9cdXZa) - The community Discord server for omp, where Tern is also discussed.

### Documentation

- [Tern plugin book](https://docs.stencil.so/tern/) - Official documentation covering host and window runtimes, lenses, blocks, native views, styling, and TSP.
- [Getting Started](https://docs.stencil.so/tern/guides/getting-started.html) - Walkthrough of building a lens and palette command, then linking, type-checking, and reloading.
- [Command Lenses](https://docs.stencil.so/tern/guides/lenses.html) - Explains how to turn command output into native views using manifest globs and host callbacks.
- [Debugging](https://docs.stencil.so/tern/guides/debugging.html) - Covers toasts, logs, Luau typing, handler budgets, and scripted window control.
- [Plugin CLI](https://docs.stencil.so/tern/reference/cli.html) - Reference for `tern plugin list`, `install`, `link`, `unlink`, `remove`, `reload`, `dir`, and `types`.
- [Tern Surface Protocol](https://docs.stencil.so/tern/protocol/index.html) - Specifies the in-band protocol where CLIs, TUIs, and agents send UI trees that Tern lays out and draws natively.

## Nix and dotfiles

Tern builds are behind a sign-in, so these Nix setups expect you to download the build yourself.

- [pelikanade/flake](https://github.com/pelikanade/flake/blob/f6f8217278a4a119c8e3a5b27b5a30ffef57cbd1/docs/tern.md) ★ 11 · 2026-10-07 - Nix packaging guide covering signed-in downloads, `requireFile`, graphics libraries, and updating.
- [plumj-am/nixos](https://github.com/plumj-am/nixos/blob/master/modules/tern.nix) ★ 2 · 2026-10-06 - NixOS module that manages Tern settings, theme, tmux-style keybindings, the `omp` launch command and plugins.
- [tdortman/dotfiles](https://github.com/tdortman/dotfiles/tree/008242f1f3ef305950a98f9878a0253477f256b0/nix) ★ 1 · 2026-10-06 - A Nix package with desktop entries, an update script finding new builds via a Stencil browser session, and a KDE Plasma Home Manager module where Meta+Return focuses Tern or starts it.

## Contributing

Suggestions are welcome as pull requests. Read the [contribution guidelines](CONTRIBUTING.md) first.
