# La Poste

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
