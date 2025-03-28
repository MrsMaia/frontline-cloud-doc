---
title: "Public APIs"
description: "Swagger documentation of the Gatling Enterprise public API."
lead: "Usage of the Gatling Enterprise public API"
date: 2021-03-08T12:50:24+00:00
lastmod: 2021-08-05T13:13:30+00:00
weight: 10090
---

The Gatling Enterprise API server also exposes a public API that you can use to trigger runs or fetch run results and metrics.

We also use this API for our Continuous Integration plugins and our Grafana datasource.

This API is protected with [API tokens]({{< ref "../../admin/api_tokens" >}}), which can be generated by your organization's System Admins through the `API Tokens` page.

You can access the Swagger documentation using the link `FrontLine API documentation` on the Documentation modal accessible on the navigation bar (bottom left of the screen).

How to retrieve simulations, runs and artifact IDs:

- Simulation IDs are available in the Simulations Table, to the left of the simulation name. To copy the id, click on the {{< icon clipboard >}} icon.
- Run IDs are available in the Runs Table: `Simulations > Runs history`. To copy the id, click on the {{< icon clipboard >}} icon to the right of the run number.
- Team IDs are available in the Teams Table. To copy the id, click on the {{< icon clipboard >}} icon.
- Artifact IDs are available in the Artifacts Table. To copy the id, click on the {{< icon clipboard >}} icon.

Some information before using the public API:

- You have to provide the run ID as a query parameter to fetch other run metadata (injectors, remotes, hostnames, scenarios, groups, requests)
- The `from` and `to` query parameters for the `/series` endpoint are the lower and upper timestamp bounds of the time window you want to query. You can fetch the total run time window from the `/runs` endpoint (`injectStart`, `injectEnd`).
- The returned percentiles by the API are: min, p25, p50, p75, p80, p85, p90, p95, p99, p999, p9999, max, mean and pAll.
