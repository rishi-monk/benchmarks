<div align="center"> <a href="https://fastify.dev/">
    <img
      src="https://github.com/fastify/graphics/raw/HEAD/fastify-landscape-outlined.svg"
      width="650"
      height="auto"
    />
  </a>
</div>

<div align="center">

[![CI](https://github.com/fastify/fastify/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/ci.yml)
[![Package Manager
CI](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml)
[![Web
site](https://github.com/fastify/fastify/actions/workflows/website.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/website.yml)
[![neostandard javascript style](https://img.shields.io/badge/code_style-neostandard-brightgreen?style=flat)](https://github.com/neostandard/neostandard)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/7585/badge)](https://bestpractices.coreinfrastructure.org/projects/7585)

</div>

<div align="center">

[![NPM
version](https://img.shields.io/npm/v/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![NPM
downloads](https://img.shields.io/npm/dm/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![Security Responsible
Disclosure](https://img.shields.io/badge/Security-Responsible%20Disclosure-yellow.svg)](https://github.com/fastify/fastify/blob/main/SECURITY.md)
[![Discord](https://img.shields.io/discord/725613461949906985)](https://discord.gg/fastify)
[![Contribute with Gitpod](https://img.shields.io/badge/Contribute%20with-Gitpod-908a85?logo=gitpod&color=blue)](https://gitpod.io/#https://github.com/fastify/fastify)
![Open Collective backers and sponsors](https://img.shields.io/opencollective/all/fastify)

</div>

<br />

# TL;DR

* [Fastify](https://github.com/fastify/fastify) is a fast and low overhead web framework for Node.js.
* This package shows how fast it is compared to other JS frameworks: these benchmarks do not pretend to represent a real-world scenario, but they give a **good indication of the framework overhead**.
* The benchmarks are run automatically on GitHub actions, which means they run on virtual hardware that can suffer from the "noisy neighbor" effect; this means that the results can vary.
* For metrics (cold-start) see [metrics.md](./METRICS.md)

# Requirements

To be included in this list, the framework should captivate users' interest. We have identified the following minimal requirements:
- **Ensure active usage**: a minimum of 500 downloads per week
- **Maintain an active repository** with at least one event (comment, issue, PR) in the last month
- The framework must use the **Node.js** HTTP module

# Usage

Clone this repo. Then

```
node ./benchmark [arguments (optional)]
```

#### Arguments

* `-h`: Help on how to use the tool.
* `bench`:  Benchmark one or more modules.
* `compare`: Get comparative data for your benchmarks.

> Create benchmark before comparing; `benchmark bench`

> You may also compare all test results, at once, in a single table; `benchmark compare -t`

> You can also extend the comparison table with percentage values based on fastest result; `benchmark compare -p`
# Benchmarks

* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Thu Jan 01 2026 01:38:57 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| fastify                  | 5.6.2    | ✓      | 46768.0    | 20.88        | 8.39          |
| node-http                | v20.19.6 | ✗      | 46496.0    | 21.00        | 8.29          |
| polka                    | 0.5.2    | ✓      | 46037.6    | 21.21        | 8.21          |
| connect                  | 3.7.0    | ✗      | 45495.2    | 21.48        | 8.11          |
| 0http                    | 4.3.0    | ✓      | 44544.8    | 21.96        | 7.94          |
| micro                    | 10.0.1   | ✗      | 44392.0    | 22.03        | 7.92          |
| connect-router           | 2.2.0    | ✓      | 43128.0    | 22.68        | 7.69          |
| h3                       | 1.15.4   | ✗      | 42779.2    | 22.88        | 7.63          |
| adonisjs                 | 7.7.0    | ✓      | 41448.8    | 23.62        | 7.39          |
| restana                  | v5.1.0   | ✓      | 40862.4    | 23.98        | 7.29          |
| h3-router                | 1.15.4   | ✓      | 40421.6    | 24.25        | 7.21          |
| whatwg-node-server       | 0.10.17  | ✗      | 38434.4    | 25.52        | 6.85          |
| hono                     | 4.11.3   | ✓      | 36523.0    | 26.88        | 5.99          |
| restify                  | 11.1.0   | ✓      | 35825.0    | 27.41        | 6.46          |
| koa                      | 3.1.1    | ✗      | 34541.4    | 28.45        | 6.16          |
| koa-router               | 14.0.0   | ✓      | 31211.6    | 31.53        | 5.57          |
| hapi                     | 21.4.4   | ✓      | 30442.4    | 32.34        | 5.43          |
| microrouter              | 3.1.3    | ✓      | 29724.0    | 33.13        | 5.30          |
| srvx                     | 0.9.8    | ✗      | 19646.0    | 50.39        | 3.82          |
| fastify-big-json         | 5.6.2    | ✓      | 11558.8    | 85.95        | 132.99        |
| express                  | 5.2.1    | ✓      | 9790.5     | 101.53       | 1.75          |
| express-with-middlewares | 5.2.1    | ✓      | 8972.8     | 110.85       | 3.34          |
| trpc-router              | 11.8.1   | ✓      | 5820.1     | 170.97       | 1.28          |
