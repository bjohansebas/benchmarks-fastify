<div align="center">
  <img src="https://github.com/fastify/graphics/raw/HEAD/fastify-landscape-outlined.svg" width="650" height="auto"/>
</div>

<div align="center">

[![CI](https://github.com/fastify/fastify/workflows/ci/badge.svg)](https://github.com/fastify/fastify/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/github/fastify/fastify/badge.svg?branch=master)](https://coveralls.io/github/fastify/fastify?branch=master)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](http://standardjs.com/)
[![NPM version](https://img.shields.io/npm/v/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![NPM downloads](https://img.shields.io/npm/dm/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify) [![Discord](https://img.shields.io/discord/725613461949906985)](https://discord.gg/fastify)

</div>
<br />

# TL;DR

* [Fastify](https://github.com/fastify/fastify) is a fast and low overhead web framework for Node.js.
* This package shows how fast it is comparatively.
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
* `compare`: Get comparative data for your benchmarks.

> You may also compare all test results, at once, in a single table; `benchmark compare -t`

> You can also extend the comparison table with percentage values based on fastest result; `benchmark compare -p`
# Benchmarks

* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v20.18.1`
* __Run:__ Mon Jan 20 2025 02:03:59 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 47614.4    | 20.51        | 8.49          |
| fastify                  | 4.29.0   | ✓      | 46384.0    | 21.04        | 8.32          |
| polkadot                 | 1.0.0    | ✗      | 46056.8    | 21.22        | 8.21          |
| connect                  | 3.7.0    | ✗      | 45925.6    | 21.27        | 8.19          |
| rayo                     | 1.4.6    | ✓      | 45668.8    | 21.40        | 8.14          |
| polka                    | 0.5.2    | ✓      | 45504.8    | 21.47        | 8.11          |
| server-base-router       | 7.1.32   | ✓      | 45348.0    | 21.55        | 8.09          |
| 0http                    | 3.5.3    | ✓      | 45276.8    | 21.59        | 8.08          |
| h3                       | 1.13.1   | ✗      | 45248.8    | 21.60        | 8.07          |
| server-base              | 7.1.32   | ✗      | 44733.6    | 21.88        | 7.98          |
| micro                    | 10.0.1   | ✗      | 44540.8    | 21.95        | 7.94          |
| h3-router                | 1.13.1   | ✓      | 43567.2    | 22.46        | 7.77          |
| connect-router           | 1.3.8    | ✓      | 43132.8    | 22.67        | 7.69          |
| micro-route              | 2.5.0    | ✓      | 42093.6    | 23.27        | 7.51          |
| hono                     | 4.6.17   | ✓      | 40569.6    | 24.14        | 6.65          |
| restana                  | 4.9.9    | ✓      | 39565.6    | 24.78        | 7.06          |
| koa                      | 2.15.3   | ✗      | 37092.8    | 26.46        | 6.61          |
| take-five                | 2.0.0    | ✓      | 35263.4    | 27.86        | 12.68         |
| restify                  | 11.1.0   | ✓      | 35249.4    | 27.86        | 6.35          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35235.4    | 27.88        | 6.28          |
| koa-router               | 12.0.1   | ✓      | 33911.4    | 28.99        | 6.05          |
| hapi                     | 21.3.12  | ✓      | 31257.0    | 31.49        | 5.57          |
| microrouter              | 3.1.3    | ✓      | 29882.4    | 32.96        | 5.33          |
| fastify-big-json         | 4.29.0   | ✓      | 11822.2    | 84.01        | 136.02        |
| express                  | 5.0.1    | ✓      | 10290.8    | 96.59        | 1.84          |
| express-with-middlewares | 5.0.1    | ✓      | 9090.8     | 109.38       | 3.38          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
