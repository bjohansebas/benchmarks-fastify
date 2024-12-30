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
* __Run:__ Mon Dec 30 2024 02:15:03 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 47002.4    | 20.77        | 8.38          |
| polka                    | 0.5.2    | ✓      | 46732.8    | 20.90        | 8.33          |
| connect                  | 3.7.0    | ✗      | 46308.0    | 21.10        | 8.26          |
| fastify                  | 4.29.0   | ✓      | 45799.2    | 21.32        | 8.21          |
| 0http                    | 3.5.3    | ✓      | 45562.4    | 21.45        | 8.13          |
| polkadot                 | 1.0.0    | ✗      | 45464.0    | 21.50        | 8.11          |
| server-base              | 7.1.32   | ✗      | 44914.4    | 21.79        | 8.01          |
| server-base-router       | 7.1.32   | ✓      | 44735.2    | 21.88        | 7.98          |
| rayo                     | 1.4.6    | ✓      | 44682.4    | 21.88        | 7.97          |
| micro                    | 10.0.1   | ✗      | 44479.2    | 21.98        | 7.93          |
| connect-router           | 1.3.8    | ✓      | 43102.4    | 22.69        | 7.69          |
| h3                       | 1.13.0   | ✗      | 42111.2    | 23.25        | 7.51          |
| h3-router                | 1.13.0   | ✓      | 41413.6    | 23.65        | 7.39          |
| micro-route              | 2.5.0    | ✓      | 40502.6    | 24.19        | 7.22          |
| hono                     | 4.6.15   | ✓      | 39617.6    | 24.73        | 6.50          |
| restana                  | 4.9.9    | ✓      | 39290.4    | 24.95        | 7.01          |
| koa                      | 2.15.3   | ✗      | 37180.0    | 26.40        | 6.63          |
| take-five                | 2.0.0    | ✓      | 35428.2    | 27.72        | 12.74         |
| restify                  | 11.1.0   | ✓      | 35051.8    | 28.03        | 6.32          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34756.0    | 28.27        | 6.20          |
| koa-router               | 12.0.1   | ✓      | 33778.6    | 29.11        | 6.02          |
| hapi                     | 21.3.12  | ✓      | 30236.0    | 32.57        | 5.39          |
| microrouter              | 3.1.3    | ✓      | 29968.0    | 32.86        | 5.34          |
| fastify-big-json         | 4.29.0   | ✓      | 11922.4    | 83.30        | 137.18        |
| express                  | 5.0.1    | ✓      | 9489.4     | 104.77       | 1.69          |
| express-with-middlewares | 5.0.1    | ✓      | 8610.6     | 115.49       | 3.20          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
