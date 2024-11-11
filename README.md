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
* __Node:__ `v20.18.0`
* __Run:__ Mon Nov 11 2024 02:12:42 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| polka                    | 0.5.2    | ✓      | 47119.2    | 20.72        | 8.40          |
| fastify                  | 4.28.1   | ✓      | 47068.8    | 20.75        | 8.44          |
| bare                     | v20.18.0 | ✗      | 47008.0    | 20.78        | 8.38          |
| connect                  | 3.7.0    | ✗      | 46599.2    | 20.95        | 8.31          |
| rayo                     | 1.4.6    | ✓      | 46499.2    | 21.02        | 8.29          |
| server-base              | 7.1.32   | ✗      | 46461.6    | 21.03        | 8.29          |
| polkadot                 | 1.0.0    | ✗      | 46436.0    | 21.04        | 8.28          |
| server-base-router       | 7.1.32   | ✓      | 45641.6    | 21.39        | 8.14          |
| 0http                    | 3.5.3    | ✓      | 45098.4    | 21.67        | 8.04          |
| micro                    | 10.0.1   | ✗      | 44365.6    | 22.05        | 7.91          |
| h3                       | 1.13.0   | ✗      | 43211.2    | 22.65        | 7.71          |
| connect-router           | 1.3.8    | ✓      | 43202.4    | 22.64        | 7.70          |
| micro-route              | 2.5.0    | ✓      | 42842.4    | 22.84        | 7.64          |
| h3-router                | 1.13.0   | ✓      | 41721.6    | 23.48        | 7.44          |
| hono                     | 4.6.9    | ✓      | 39906.4    | 24.55        | 7.12          |
| restana                  | 4.9.9    | ✓      | 39234.4    | 24.98        | 7.00          |
| koa                      | 2.15.3   | ✗      | 37844.8    | 25.94        | 6.75          |
| take-five                | 2.0.0    | ✓      | 36295.4    | 27.04        | 13.05         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35505.4    | 27.69        | 6.33          |
| restify                  | 11.1.0   | ✓      | 35302.6    | 27.82        | 6.36          |
| koa-router               | 12.0.1   | ✓      | 34811.6    | 28.24        | 6.21          |
| hapi                     | 21.3.12  | ✓      | 32208.0    | 30.54        | 5.74          |
| microrouter              | 3.1.3    | ✓      | 30666.0    | 32.10        | 5.47          |
| fastify-big-json         | 4.28.1   | ✓      | 11887.2    | 83.57        | 136.76        |
| express                  | 5.0.1    | ✓      | 10034.0    | 99.08        | 1.79          |
| express-with-middlewares | 5.0.1    | ✓      | 9234.8     | 107.66       | 3.43          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
