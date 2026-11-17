# Memcert packs

Memory packs for AI agents, each checked before it is listed.

A memory pack is one signed file of knowledge, or of behaviour, that an AI agent can load. This repository is where packs are proposed, checked in the open, and kept once they are certified.

**Status: preview.** The first packs are our own. Proposals from others open once the checking workflow has run on a real pull request.

## What is here

| Path | What it is |
| --- | --- |
| `packs\<account>\` | The certified packs, one file per version |
| `publishers\<account>.pub.pem` | Each publisher's public key |
| `trust.json` | The hub's trust policy. With it, a pack loads only if its publisher **and** the Memcert curator signed that exact content |
| `CONTRIBUTING.md` | How to propose a pack |
| `POLICY.md` | What is checked, what "certified" means, how a pack is withdrawn |

## Use a pack

1. Get the `ampack` tool from https://github.com/joslat/agent-memory-dotnet (folder `tools/Ampack`).
2. Download a pack from `packs\` and `trust.json`.
3. Check it, then give it to your agent:

```
ampack verify <pack>.ampack --policy trust.json --explain
ampack serve  <pack>.ampack --policy trust.json
```

`serve` offers the pack to any MCP client.

## What a certificate says

1. This is the pack that was proposed, and it is the pack you get.
2. Its publisher answers for it.
3. We found nothing in it that instructs an agent, and no personal data or secrets.
4. Nobody changed it afterwards.

It does not say that the content is true, or that an agent holding the pack will always behave. See `POLICY.md`.

## Licences

Each pack states the licence of its content in the pack itself. The rules, the workflow and the other files of this repository are under Apache-2.0 (`LICENSE.md`).
