# Membership

The common membership vocabulary -- the members of an association, club or gym, the memberships they hold, the membership types and levels on offer and the chapters they belong to -- distilled from the APIs that already exist. Dues invoices belong to billing. Part of [Schema Commons](https://github.com/api-commons/schema-commons),
published by the [API Commons](https://apicommons.org).

Built from the providers tagged Membership, Associations, Membership Management, Association Management, Clubs, Gyms, Member Management in [APIs.io](https://apis.io) that
publish their own OpenAPI. Only harvested contracts count -- nothing API Evangelist
generated. Every number below is a count of providers.

## What the market already agrees on

<!-- commons:summary -->
| Concept | Expose it | Readable schema | Core properties (share) | Collection named |
| --- | ---: | ---: | --- | --- |
| member | 9 | 8 | id 100%, email 62%, status 62% | members 8, member 2 |

Cohort: 26 providers with harvested OpenAPI, 9 crosswalks. Of the providers exposing a member: 44% create, 89% list, 89% fetch, 33% update, 33% delete. Generated 2026-11-11 by build.py.
<!-- /commons:summary -->

Shares are of the providers with a readable resource schema for that concept. The
extended tier and the long tail of every concept are in [profile.yml](profile.yml).

## What the measurement shows

- A member agrees on id, email and status across association, club and gym platforms -- and that is all membership publishes in common (26 providers, 9 mapped). Memberships, levels and chapters are kept inside the products.

## Artifacts

- [openapi.yml](openapi.yml) -- OpenAPI 3.1 of the shared operations. No one serves it; it
  is the shape to map to. Lints clean against the
  [naming ruleset](https://github.com/api-commons/schema-commons/blob/main/ruleset/schema-commons-naming.yaml).
- [schema/](schema) -- JSON Schema 2020-12 per concept; each property carries
  `x-commons-tier`, `x-commons-share`, `x-commons-providers` and the spellings seen.
- [crosswalk/](crosswalk) -- one per provider, common name -> their name, with the harvested
  spec and operations each mapping was read from.
- [adopters.yml](adopters.yml) -- who exposes which concept, linked to their APIs.io page.
- [concepts.yml](concepts.yml) -- the only hand-written input: concepts, path segments and
  their qualifiers, aliases, reviewed exclusions, merged duplicates, and the decisions below.
- [census/](census) -- the cohort and the raw census the profile is built from.

## Decisions

These are calls, not measurements, recorded so they can be revisited as the method matures.

- Members are `/members`, the market's word: inside this cohort it means only one thing (HR excluded it as workspace members, identity counts it as users).
- Dues are billing's invoices; events are the events context's.
- Memberships, membership types and chapters were measured and dropped.

## Rebuild

```bash
../schema-commons/scripts/run.sh .
```

## License

Artifacts CC BY-NC-SA 4.0 ([LICENSE](LICENSE)); code Apache 2.0 ([LICENSE-CODE](LICENSE-CODE)).
