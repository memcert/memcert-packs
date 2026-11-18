# Memcert packs

Memory packs for AI agents, each checked before it is listed.

A memory pack is one signed file of knowledge, or of behaviour, that an AI agent can load. This repository is where packs are proposed, checked in the open, and kept once they are certified.

**The shelf: [memcert.dev](https://memcert.dev).** Every pack here, with what each check found, its card, its first records, and a download.

**Status: preview.** The first packs are our own. Proposals from others open once the checking workflow has run on a real pull request.

## The packs

<!-- The curator adds a row when a pack is merged, in the order of shelf.json. -->

| Pack | Version | Licence | File |
| --- | --- | --- | --- |
| [A primer on memory packs](https://memcert.dev/packs/io.github.joslat.packs.ampackprimer/) | 0.1.1 | CC-BY-4.0 | [`io.github.joslat.packs.ampackprimer-0.1.1.ampack`](packs/joslat/io.github.joslat.packs.ampackprimer-0.1.1.ampack) |
| [The ampack specification, requirement by requirement](https://memcert.dev/packs/io.github.joslat.packs.ampackspec/) | 1.0.0 | CC-BY-4.0 | [`io.github.joslat.packs.ampackspec-1.0.0.ampack`](packs/joslat/io.github.joslat.packs.ampackspec-1.0.0.ampack) |
| [AgentMemory, ampack and AgentEval: facts and lines](https://memcert.dev/packs/io.github.joslat.packs.agentmemoryfacts/) | 1.0.0 | CC-BY-4.0 | [`io.github.joslat.packs.agentmemoryfacts-1.0.0.ampack`](packs/joslat/io.github.joslat.packs.agentmemoryfacts-1.0.0.ampack) |
| [Swiss cantons](https://memcert.dev/packs/io.github.joslat.packs.swisscantons/) | 0.1.0 | CC-BY-4.0 | [`io.github.joslat.packs.swisscantons-0.1.0.ampack`](packs/joslat/io.github.joslat.packs.swisscantons-0.1.0.ampack) |
| [Alpenglow Bakery handbook](https://memcert.dev/packs/io.github.joslat.packs.alpenglowbakery/) | 0.1.0 | CC-BY-4.0 | [`io.github.joslat.packs.alpenglowbakery-0.1.0.ampack`](packs/joslat/io.github.joslat.packs.alpenglowbakery-0.1.0.ampack) |
| [Lantern Hill dojo](https://memcert.dev/packs/io.github.joslat.packs.lanternhilldojo/) | 1.1.0 | CC-BY-4.0 | [`io.github.joslat.packs.lanternhilldojo-1.1.0.ampack`](packs/joslat/io.github.joslat.packs.lanternhilldojo-1.1.0.ampack) |
| [Martial arts](https://memcert.dev/packs/io.github.joslat.packs.martialarts/) | 1.1.0 | CC-BY-4.0 | [`io.github.joslat.packs.martialarts-1.1.0.ampack`](packs/joslat/io.github.joslat.packs.martialarts-1.1.0.ampack) |
| [Coaching techniques: the core cards](https://memcert.dev/packs/io.github.joslat.packs.coachingtechniques/) | 1.0.0 | CC-BY-4.0 | [`io.github.joslat.packs.coachingtechniques-1.0.0.ampack`](packs/joslat/io.github.joslat.packs.coachingtechniques-1.0.0.ampack) |

A pack merged here shows on memcert.dev once the site is built again.

## What is here

| Path | What it is |
| --- | --- |
| `packs/<account>/` | The certified packs, one file per version |
| `publishers/<account>.pub.pem` | Each publisher's public key |
| `trust.json` | The hub's trust policy. With it, a pack loads only if its publisher **and** the Memcert curator signed that exact content |
| `shelf.json` | The order of the packs on memcert.dev, and any pack kept off it |
| `CONTRIBUTING.md` | How to propose a pack |
| `POLICY.md` | What is checked, what "certified" means, how a pack is withdrawn |

## Use a pack

1. Get the `ampack` tool from https://github.com/joslat/agent-memory-dotnet (folder `tools/Ampack`).
2. Download a pack, from the table above or from memcert.dev, and `trust.json`.
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
