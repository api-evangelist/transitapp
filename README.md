# Transit (transitapp)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Transit (the Transit App) is a real-time public transit trip planning and departures platform covering 1,100+ cities in 37 countries. The Transit REST API delivers real-time departures, nearby routes and stops, route details, multimodal trip planning, and service alerts, plus shared-mobility availability for bikes, scooters, and carshare. The API is publicly documented at [api-doc.transitapp.com](https://api-doc.transitapp.com/) but access is key-gated - developers request a key that grants a free tier (5 requests/minute, 1,500 requests/month), and higher volumes are arranged with the partnerships team. Requests are authenticated with an `apiKey` header against `https://external.transitapp.com/v3`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/transitapp/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/transitapp/refs/heads/main/apis.yml)

## Tags

- Transit
- Public Transportation
- Real-Time
- Mobility
- Trip Planning
- Departures
- GTFS
- MaaS

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## Access

The Transit API is publicly documented but gated by an access key. Request a key via Transit's API request form linked from [transitapp.com/partners/apis](https://transitapp.com/partners/apis). The free tier allows up to 5 requests/minute and 1,500 requests/month. For higher volumes or specific use cases, contact `partners@transit.app`. All requests are authenticated with an `apiKey` request header and may set `Accept-Language` for localization.

> **Grounding note:** the `apiKey` header, the `https://external.transitapp.com/v3` base URL, and the `GET /public/nearby_stops` endpoint are confirmed from Transit's public docs and a working open-source integration. The other endpoints are modeled honestly from Transit's documented v3 API surface and GTFS/GTFS-realtime conventions - see `review.yml` for the confirmed-vs-modeled breakdown.

## APIs

### Transit Nearby Routes API

Returns the public transit routes near a latitude/longitude, each with upcoming real-time departures, direction and headsign, wheelchair accessibility, and network branding.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Nearby Routes
- Real-Time
- Departures

#### Properties

- [Documentation](https://transitapp.com/partners/apis)
- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Nearby Stops API

Returns the transit stops near a latitude/longitude within a maximum distance, each with a stable `global_stop_id` and the routes that serve it. (Confirmed endpoint.)

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Nearby Stops
- Geolocation

#### Properties

- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Stop Departures API

Returns the upcoming departures for a specific stop identified by its `global_stop_id`, grouped by route and direction, blending real-time predictions with scheduled times.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Departures
- Real-Time
- Schedules

#### Properties

- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Route Details API

Returns the detail for a specific route identified by its `global_route_id` - its itineraries/directions, the ordered list of stops, path geometry, and branding.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Route Details
- Schedules
- Geometry

#### Properties

- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Trip Planning API

Multimodal trip planning between an origin and a destination, returning ranked itineraries that combine public transit with walking, biking, and shared mobility. Built on an OpenTripPlanner-style plan surface.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Trip Planning
- Routing
- Multimodal

#### Properties

- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Service Alerts API

Returns service alerts and disruptions - delays, detours, elevator outages, and cancellations - scoped to a route, stop, or network, following the GTFS-realtime service-alert model.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Service Alerts
- Public Alerts
- Disruptions

#### Properties

- [Documentation](https://resources.transitapp.com/article/461-alerts)
- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Transit Locations API

Discovers the transit networks and coverage available near a latitude/longitude - the agencies and systems Transit has data for in that location - so a client can determine which cities and networks are supported before making routing or departures calls.

- **Human URL:** [https://api-doc.transitapp.com/](https://api-doc.transitapp.com/)
- **Base URL:** `https://external.transitapp.com/v3`

#### Tags

- Locations
- Networks
- Coverage

#### Properties

- [API Reference](https://api-doc.transitapp.com/)
- [OpenAPI](openapi/transitapp-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/transitapp.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/transitapp.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/TransitApp)
- [LinkedIn](https://www.linkedin.com/company/transit-app)
- [Website](https://transitapp.com)
- [Documentation](https://api-doc.transitapp.com/)
- [Plans](plans/transitapp-plans-pricing.yml)
- [Rate Limits](rate-limits/transitapp-rate-limits.yml)
- [Fin Ops](finops/transitapp-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
