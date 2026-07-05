# EventMobi (eventmobi)

EventMobi is an event management platform for in-person, virtual, and hybrid events - event apps, registration and ticketing, event websites, badges and check-in, and live engagement - all configured through its **Experience Manager**. EventMobi exposes a documented public **Unified API (UAPI)** that lets organizers programmatically read and manage the data behind an event: events, people (attendees, speakers, and other participants), sessions, companies (sponsors and exhibitors), and groups.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/eventmobi/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/eventmobi/refs/heads/main/apis.yml)

## Access Model (Read This First)

The EventMobi Unified API is **real and publicly documented, but access-gated** - it is not an open self-service developer API.

- **Base URL:** `https://uapi.eventmobi.com`
- **Versions:** UAPI v3 and the current **UAPI v4**.
- **Authentication:** API key. Each key is **generated inside Experience Manager**, is scoped to a single **Organizer**, and carries the **same access rights as that Organizer** within the Organization it was generated for.
- **Getting access:** You need an EventMobi **Organizer account**, which requires a paid plan (EventMobi lists per-event and per-year pricing and routes larger or custom needs to sales). There is no anonymous API signup.
- **Pagination:** List endpoints return a maximum of **1000 items per page** unless otherwise stated; sorting and filtering are supported.
- **Other documented features:** image upload to a temporary URL via `PUT`, search/filtering, field visibility by authorization level, and webhooks (server-to-endpoint HTTP callbacks).
- **Developer support:** `api@eventmobi.com`

### On endpointsModeled

The logical APIs below reflect EventMobi's documented resource model. Confirmed request patterns observed in the public docs include `GET`/`PATCH` on the events collection and nested resources such as `/events/{event_id}/images/` and `/events/{event_id}/companies/`. The full per-resource verb/path matrix was **not machine-extractable** because the developer reference is served from a gated single-page portal (HTTP 403 to automated fetches), so the exact CRUD surface per resource is **modeled** from the documented structure rather than transcribed endpoint by endpoint. No OpenAPI or Postman collection is included, to avoid fabricating an unverified endpoint surface.

## Tags

- Events
- Event Management
- Event Apps
- Attendees
- Sessions
- Registration

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### EventMobi Events API

Read and update the events an Organizer manages. Confirmed request patterns include `GET` and `PATCH` on the events collection and nested resources such as `/events/{event_id}/images/`. Full CRUD coverage is endpointsModeled.

- **Human URL:** [https://developers.eventmobi.com/latest/](https://developers.eventmobi.com/latest/)
- **Base URL:** `https://uapi.eventmobi.com`

### EventMobi People API

Manage the people associated with an event - attendees, speakers, and other participants - including profile fields and visibility (controlled by authorization level). People are organized into groups. Endpoints are nested under an event. Verb/path coverage is endpointsModeled.

- **Human URL:** [https://developers.eventmobi.com/latest/](https://developers.eventmobi.com/latest/)
- **Base URL:** `https://uapi.eventmobi.com`

### EventMobi Sessions API

Manage an event's agenda sessions - scheduling, session roles, and the speakers and content attached to each session. Endpoints are nested under an event. Verb/path coverage is endpointsModeled.

- **Human URL:** [https://developers.eventmobi.com/latest/](https://developers.eventmobi.com/latest/)
- **Base URL:** `https://uapi.eventmobi.com`

### EventMobi Companies API

Manage the companies shown in an event - sponsors, exhibitors, and vendors. Confirmed request pattern includes the nested collection `/events/{event_id}/companies/`. Full verb/path coverage is endpointsModeled.

- **Human URL:** [https://developers.eventmobi.com/latest/](https://developers.eventmobi.com/latest/)
- **Base URL:** `https://uapi.eventmobi.com`

### EventMobi Groups API

Create and manage people groups used to categorize attendees within an event; custom groups carry the `custom` type. Endpoints are nested under an event. Verb/path coverage is endpointsModeled.

- **Human URL:** [https://developers.eventmobi.com/latest/](https://developers.eventmobi.com/latest/)
- **Base URL:** `https://uapi.eventmobi.com`

## Common Properties

- [GitHub Organization](https://github.com/EventMobi)
- [LinkedIn](https://www.linkedin.com/company/eventmobi)
- [Website](https://www.eventmobi.com)
- [Documentation](https://developers.eventmobi.com/latest/)
- [Plans](plans/eventmobi-plans-pricing.yml)
- [Rate Limits](rate-limits/eventmobi-rate-limits.yml)
- [Fin Ops](finops/eventmobi-finops.yml)
- [Blog](https://www.eventmobi.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
