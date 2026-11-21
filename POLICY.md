# What is listed here, and what "certified" means

Draft of 17 November 2026, revised 21 November 2026. It is short on purpose and will grow with experience.

## What a certificate says

1. This is the pack that was proposed, and it is the pack you get.
2. Its publisher answers for it.
3. We found nothing in it that instructs an agent, and no personal data or secrets.
4. Nobody changed it afterwards.

It does **not** say that the content is true, or that an agent holding the pack will always behave. We say what we checked.

## The checks

| Check | By | Refused when |
| --- | --- | --- |
| The signature is valid and every file matches the signed list | The tool | Anything was changed after signing |
| The id belongs to the account that proposes it | The tool and a person | The id names another account or a domain not proven |
| The content scan | The tool | It finds personal data, a secret, or text that tries to instruct an agent |
| The structure, the card and a stated licence | The tool and a person | The card is missing or empty, or no licence is stated |
| The pack's own tests | The tool | A test fails |
| A reading of the content | A person | The content is not the publisher's to share, is unlawful, or its name could be mistaken for another pack |

## Two states

- **Listed:** all automatic checks pass.
- **Certified:** the pack was reviewed, the curator accepted the review and signed this exact pack. A host that uses this hub's trust policy loads only packs with that second signature.

Who reviews: for a pack from another publisher, a person, before it is certified. The sample packs we published ourselves were reviewed by an AI agent, and the curator accepted that review; the checks the table gives to "a person" were done that way for them.

## Licences

Each pack states the licence of its content. Open licences are accepted. A pack whose content the publisher has no right to share is refused.

## Withdrawing a pack

If something is found after listing, the pack is named in a signed, dated list of withdrawals, and its page says why. A publisher can ask for its own pack to be withdrawn at any time.

## Asking for a pack to be taken down

Open an issue naming the pack and the reason, or write to hello@memcert.dev. Rights holders can write to the same address.

## Refusals are public

A pull request that is refused stays visible with its reason. A publisher can close its own pull request before a decision.

## Who decides

For now, one curator. Our own packs go through the same checks, and their pages say that the publisher and the curator are the same party. Their review was an AI agent's, accepted by the curator (see Two states).
