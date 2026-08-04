# EventMobi (eventmobi)

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
