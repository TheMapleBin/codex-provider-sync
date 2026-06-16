<div align="center">

# codex-provider-sync

### Keep Codex history visible after switching between providers

[![CI](https://github.com/TheMapleBin/codex-provider-sync/actions/workflows/ci.yml/badge.svg)](https://github.com/TheMapleBin/codex-provider-sync/actions/workflows/ci.yml)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)](https://github.com/TheMapleBin/codex-provider-sync)
[![Node](https://img.shields.io/badge/node-24%2B-brightgreen.svg)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](../LICENSE)

English | [中文](../README.md)

</div>

## What It Solves

Codex session visibility can break after switching `model_provider`.

Typical symptom:

- old sessions visible under one provider
- then disappear after switching
- CLI and Desktop disagree due to rollout + SQLite metadata mismatch

This tool synchronizes:

- `~/.codex/sessions`
- `~/.codex/archived_sessions`
- `~/.codex/state_5.sqlite`

## Install

```bash
npm install -g git+https://github.com/TheMapleBin/codex-provider-sync.git
```

Requires Node.js 24+.

## Usage

```bash
codex-provider status
codex-provider sync
codex-provider sync --provider openai
codex-provider switch apigather
```

## Safety

- Does not modify login/auth
- Does not rewrite conversation content
- Does not re-encrypt encrypted_content across providers
- Only syncs visibility metadata

## License

MIT