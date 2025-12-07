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
* __Run:__ Sun Dec 07 2025 06:03:17 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 48112.0    | 20.33        | 8.58          |
| connect                  | 3.7.0    | ✗      | 47321.6    | 20.63        | 8.44          |
| 0http                    | 4.3.0    | ✓      | 47040.0    | 20.76        | 8.39          |
| polka                    | 0.5.2    | ✓      | 46956.0    | 20.79        | 8.37          |
| fastify                  | 5.6.2    | ✓      | 46636.8    | 20.94        | 8.36          |
| micro                    | 10.0.1   | ✗      | 45888.0    | 21.29        | 8.18          |
| h3                       | 1.15.4   | ✗      | 43420.0    | 22.54        | 7.74          |
| connect-router           | 2.2.0    | ✓      | 43218.4    | 22.63        | 7.71          |
| restana                  | v5.1.0   | ✓      | 43091.2    | 22.71        | 7.68          |
| h3-router                | 1.15.4   | ✓      | 42016.8    | 23.30        | 7.49          |
| adonisjs                 | 7.7.0    | ✓      | 41433.6    | 23.64        | 7.39          |
| whatwg-node-server       | 0.10.17  | ✗      | 39487.2    | 24.82        | 7.04          |
| hono                     | 4.10.7   | ✓      | 37414.4    | 26.20        | 6.14          |
| restify                  | 11.1.0   | ✓      | 35587.4    | 27.58        | 6.41          |
| koa                      | 3.1.1    | ✗      | 34654.6    | 28.34        | 6.18          |
| koa-router               | 14.0.0   | ✓      | 32975.0    | 29.81        | 5.88          |
| hapi                     | 21.4.4   | ✓      | 32434.0    | 30.33        | 5.78          |
| microrouter              | 3.1.3    | ✓      | 30202.0    | 32.59        | 5.39          |
| srvx                     | 0.9.7    | ✗      | 20073.6    | 49.31        | 3.91          |
| fastify-big-json         | 5.6.2    | ✓      | 11799.8    | 84.20        | 135.76        |
| express                  | 5.2.1    | ✓      | 9963.0     | 99.78        | 1.78          |
| express-with-middlewares | 5.2.1    | ✓      | 8991.4     | 110.58       | 3.34          |
| trpc-router              | 11.7.2   | ✓      | 6440.5     | 154.51       | 1.42          |
