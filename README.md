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
* __Run:__ Mon Dec 09 2024 02:24:27 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| polkadot                 | 1.0.0    | ✗      | 52975.2    | 18.38        | 9.45          |
| bare                     | v20.18.1 | ✗      | 46444.8    | 21.02        | 8.28          |
| fastify                  | 4.29.0   | ✓      | 46096.0    | 21.18        | 8.26          |
| connect                  | 3.7.0    | ✗      | 45210.4    | 21.61        | 8.06          |
| polka                    | 0.5.2    | ✓      | 45108.0    | 21.68        | 8.04          |
| server-base-router       | 7.1.32   | ✓      | 45076.0    | 21.69        | 8.04          |
| server-base              | 7.1.32   | ✗      | 44892.8    | 21.78        | 8.01          |
| 0http                    | 3.5.3    | ✓      | 44770.4    | 21.85        | 7.98          |
| rayo                     | 1.4.6    | ✓      | 44455.2    | 22.00        | 7.93          |
| micro                    | 10.0.1   | ✗      | 44326.4    | 22.06        | 7.90          |
| micro-route              | 2.5.0    | ✓      | 42240.8    | 23.16        | 7.53          |
| connect-router           | 1.3.8    | ✓      | 42091.2    | 23.27        | 7.51          |
| h3                       | 1.13.0   | ✗      | 41524.0    | 23.58        | 7.41          |
| h3-router                | 1.13.0   | ✓      | 41104.8    | 23.83        | 7.33          |
| hono                     | 4.6.13   | ✓      | 40362.4    | 24.26        | 7.20          |
| restana                  | 4.9.9    | ✓      | 38301.4    | 25.61        | 6.83          |
| koa                      | 2.15.3   | ✗      | 36980.8    | 26.54        | 6.59          |
| take-five                | 2.0.0    | ✓      | 34795.4    | 28.23        | 12.51         |
| restify                  | 11.1.0   | ✓      | 34743.8    | 28.27        | 6.26          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34322.8    | 28.62        | 6.12          |
| koa-router               | 12.0.1   | ✓      | 33972.4    | 28.94        | 6.06          |
| hapi                     | 21.3.12  | ✓      | 31191.6    | 31.56        | 5.56          |
| microrouter              | 3.1.3    | ✓      | 30084.8    | 32.73        | 5.37          |
| fastify-big-json         | 4.29.0   | ✓      | 11735.6    | 84.63        | 135.04        |
| express                  | 5.0.1    | ✓      | 9787.2     | 101.56       | 1.75          |
| express-with-middlewares | 5.0.1    | ✓      | 8962.4     | 110.94       | 3.33          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
