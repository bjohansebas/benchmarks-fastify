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
* __Run:__ Mon Nov 25 2024 02:19:03 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.0 | ✗      | 47678.4    | 20.48        | 8.50          |
| connect                  | 3.7.0    | ✗      | 46514.4    | 20.99        | 8.30          |
| fastify                  | 4.28.1   | ✓      | 46154.4    | 21.16        | 8.28          |
| polka                    | 0.5.2    | ✓      | 46001.6    | 21.23        | 8.20          |
| server-base              | 7.1.32   | ✗      | 45906.4    | 21.28        | 8.19          |
| rayo                     | 1.4.6    | ✓      | 45815.2    | 21.32        | 8.17          |
| server-base-router       | 7.1.32   | ✓      | 45098.4    | 21.68        | 8.04          |
| micro                    | 10.0.1   | ✗      | 44808.8    | 21.81        | 7.99          |
| polkadot                 | 1.0.0    | ✗      | 44411.2    | 22.02        | 7.92          |
| 0http                    | 3.5.3    | ✓      | 43168.0    | 22.67        | 7.70          |
| connect-router           | 1.3.8    | ✓      | 43127.2    | 22.68        | 7.69          |
| micro-route              | 2.5.0    | ✓      | 41841.6    | 23.41        | 7.46          |
| h3                       | 1.13.0   | ✗      | 40798.4    | 24.01        | 7.28          |
| h3-router                | 1.13.0   | ✓      | 40380.8    | 24.27        | 7.20          |
| hono                     | 4.6.11   | ✓      | 39865.6    | 24.58        | 7.11          |
| koa                      | 2.15.3   | ✗      | 36697.4    | 26.74        | 6.54          |
| restana                  | 4.9.9    | ✓      | 35573.4    | 27.62        | 6.34          |
| take-five                | 2.0.0    | ✓      | 34969.0    | 28.09        | 12.57         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34617.8    | 28.37        | 6.17          |
| restify                  | 11.1.0   | ✓      | 33965.0    | 28.93        | 6.12          |
| koa-router               | 12.0.1   | ✓      | 33452.0    | 29.40        | 5.97          |
| hapi                     | 21.3.12  | ✓      | 30764.4    | 32.00        | 5.49          |
| microrouter              | 3.1.3    | ✓      | 29887.6    | 32.95        | 5.33          |
| fastify-big-json         | 4.28.1   | ✓      | 11955.6    | 83.06        | 137.55        |
| express                  | 5.0.1    | ✓      | 9761.5     | 101.82       | 1.74          |
| express-with-middlewares | 5.0.1    | ✓      | 9151.4     | 108.67       | 3.40          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
