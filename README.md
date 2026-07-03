# Transit (transitapp)

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
