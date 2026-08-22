# La Poste

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

La Poste is the French national postal service. Its developer platform, Okapi (developer.laposte.fr), exposes a suite of REST APIs covering parcel tracking, address validation, geolocation, registered letter ordering, certified document exchange, and open data access.

## Developer Portal

https://developer.laposte.fr/

## APIs

| API | Description | Auth |
|-----|-------------|------|
| Suivi v2 | Real-time tracking for tracked mail, Colissimo parcels, and Chronopost shipments | X-Okapi-Key |
| ControlAdresse v2 | Validate and normalise French postal addresses to La Poste CEDEX standard | X-Okapi-Key |
| Geolocalisation | Forward-geocode a French address to GPS coordinates | X-Okapi-Key |
| Geolocalisation Inversee | Reverse-geocode — find the five closest addresses from a GPS point | X-Okapi-Key |
| Colissimo SLS REST | Create shipping labels and customs documents; submit electronic parcel pre-advice | Login/password (business contract) |
| LReL | Order online registered letters — La Poste prints and delivers physically | OAuth2 |
| Digiposte v3 | Send certified documents to a Digiposte digital safe; retrieve authenticated documents | OAuth2 |
| dataNOVA | Open data portal — postal codes, post office locations, mailbox schedules, SIRENE | None (open) |

## Authentication

Most Okapi APIs authenticate via an `X-Okapi-Key` header. Register a free account at developer.laposte.fr, create an application, and subscribe to the desired API to obtain your key.

LReL and Digiposte APIs use OAuth2. Colissimo uses account credentials tied to a business contract.

## Rate Limits

The Okapi platform enforces a default quota of **100 calls per minute** per application key across free-tier APIs. Exceeding the quota returns HTTP 429. Business plans offer higher limits negotiated directly with La Poste.

## Resources

- API Catalog: https://developer.laposte.fr/catalog-apis
- Service Status: https://developer.laposte.fr/status/api
- FAQ / Knowledge Base: https://faq.developer.laposte.fr/
- CLI (okapi-cli): https://github.com/DeveloperLaPoste/okapi-cli
- JavaScript SDK: https://github.com/DeveloperLaPoste/okapi-sdk-js
- dataNOVA Open Data: https://datanova.laposte.fr/
- Colissimo Business: https://www.colissimo.entreprise.laposte.fr/
