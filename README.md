# Bob the Bouncer — Scam Playbooks

An open, per-country database of scam **playbooks**: not blocklists (bad URLs, bad numbers — those exist), but the *knowledge* layer — how each scam works, beat by beat, in each country: the hook, the script, the one sentence that kills it, and where to report.

Built for [Bob the Bouncer](https://github.com/nickhilster/bob-the-bouncer): same Bob, local playbooks.

## Structure

```
playbooks/
  <country-code>/        # ISO 3166-1 alpha-2, e.g. in/, ca/
    <scam-id>.yaml
```

## Schema

See [SCHEMA.md](SCHEMA.md). Every entry carries:

- `hook` — the opening move (what the victim sees first)
- `script` — the beats in order
- `kill_shot` — the one sentence that kills the whole scam, plus `kill_shot_local` translations
- `safe_path` — what the victim should do, step by step
- `helplines` — local numbers and report URLs
- `sources` — every factual claim traceable to a source

## Review discipline

An accepted recollection remains a recollection. Every playbook must cite sources for its factual claims (helplines, legal facts, loss figures). `status: verified` means every claim is sourced; `status: draft` means it's a field report awaiting sources. Never mark `verified` from memory.

## Contributing

New country? New scam? Open a PR with a playbook YAML following the schema, sources attached. If you've *lived* a scam (or watched someone go through one), your field notes are welcome — mark them `status: draft` and we'll source them together.

## Why this exists

Blocklists answer "is this number bad." Playbooks answer "what is happening to me right now, and what do I do." The first is for software. The second is for people.

## Canada starter pack

- [CRA impersonation calls](playbooks/ca/cra-vishing.yaml)
- [Service Canada SIN suspension scare](playbooks/ca/service-canada-sin-suspension.yaml)
- [IRCC impersonation and deportation threats](playbooks/ca/ircc-deportation-threat.yaml)
- [Canada Post fake delivery fees](playbooks/ca/canada-post-delivery-fee.yaml)

These are Canadian versions of broader patterns. Country labels describe the institutions and reporting routes, not where the scammer is based. Use fictional examples for teaching and check official contacts before printing or recording materials.

## Licence

The repository’s original playbook text, data and schema are available under the [MIT License](LICENSE). Linked source material, third-party names and logos are not licensed by this repository.
