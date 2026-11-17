# Propose a pack

A proposal is a pull request to this repository. Every automatic check runs in the open, and a person decides.

## What you need

1. The `ampack` tool, built from https://github.com/joslat/agent-memory-dotnet (folder `tools/Ampack`).
2. A GitHub account. Your pack's id starts with `io.github.<your account>.`, in lower case.

## Steps

1. **Start a pack.**

   ```
   ampack init my-pack --id io.github.<your account>.packs.<name> --kind knowledge --owner "<your name>"
   ```

2. **Fill it in.** Records in `records/`, and in `card.json`: who made it, what it is for, its limits, and `whenToUse`. State the licence of the content in `pack.json` (`licence`).
3. **Add a few tests** in `evals/tests.json`: a question, and the record that must come back.
4. **Make a key, once.** Keep the private key to yourself.

   ```
   ampack keygen --out my-keys --name "<your account>" --prefix io.github.<your account> --role publisher --policy my-trust.json
   ```

5. **Build and sign.**

   ```
   ampack build my-pack --out io.github.<your account>.packs.<name>-0.1.0.ampack --key my-keys/<your account>.key.pem
   ```

6. **Check it yourself first.** These are the same checks that run here.

   ```
   ampack lint <file>.ampack --policy my-trust.json --safety
   ampack scan <file>.ampack --policy my-trust.json
   ampack test <file>.ampack --policy my-trust.json
   ```

7. **Open the pull request** with exactly two things:
   - the pack file, at `packs/<your account>/<file>.ampack`
   - with your first pack only: your public key, at `publishers/<your account>.pub.pem`

   The pull request must come from the account named in the pack's id.

## What happens next

1. Automatic checks run on the pull request: the signature, that the id belongs to your account, the content scan, the structure, your tests.
2. A person reads the pack, its card and its licence.
3. It is accepted or refused. A refusal says why. Fix it and propose a new version; a signed pack is never edited.
4. An accepted pack is signed a second time by the curator and appears on the site as certified.

## A new version

A new version is a new file with a higher version number. It goes through the same steps.

## Changing your key

Open a pull request from the same account that replaces `publishers/<your account>.pub.pem`. Packs signed with the old key stay valid unless the key is withdrawn.

## What is refused

See `POLICY.md`.
