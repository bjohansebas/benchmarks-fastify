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
* __Run:__ Mon Oct 28 2024 02:20:24 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.0 | ✗      | 48303.2    | 20.24        | 8.61          |
| connect                  | 3.7.0    | ✗      | 46933.6    | 20.80        | 8.37          |
| fastify                  | 4.28.1   | ✓      | 46712.0    | 20.90        | 8.38          |
| polka                    | 0.5.2    | ✓      | 46681.6    | 20.92        | 8.32          |
| server-base              | 7.1.32   | ✗      | 46352.8    | 21.07        | 8.27          |
| rayo                     | 1.4.6    | ✓      | 46166.4    | 21.15        | 8.23          |
| polkadot                 | 1.0.0    | ✗      | 46032.0    | 21.23        | 8.21          |
| server-base-router       | 7.1.32   | ✓      | 45796.8    | 21.31        | 8.17          |
| micro                    | 10.0.1   | ✗      | 45399.2    | 21.52        | 8.10          |
| 0http                    | 3.5.3    | ✓      | 44482.4    | 21.98        | 7.93          |
| connect-router           | 1.3.8    | ✓      | 44041.6    | 22.18        | 7.85          |
| micro-route              | 2.5.0    | ✓      | 43002.4    | 22.75        | 7.67          |
| h3                       | 1.13.0   | ✗      | 42128.0    | 23.24        | 7.51          |
| h3-router                | 1.13.0   | ✓      | 42120.0    | 23.25        | 7.51          |
| hono                     | 4.6.7    | ✓      | 41216.0    | 23.75        | 7.35          |
| restana                  | 4.9.9    | ✓      | 38241.6    | 25.65        | 6.82          |
| koa                      | 2.15.3   | ✗      | 37411.0    | 26.22        | 6.67          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35559.8    | 27.63        | 6.34          |
| take-five                | 2.0.0    | ✓      | 35548.2    | 27.64        | 12.78         |
| restify                  | 11.1.0   | ✓      | 35483.8    | 27.68        | 6.40          |
| koa-router               | 12.0.1   | ✓      | 34102.0    | 28.83        | 6.08          |
| hapi                     | 21.3.12  | ✓      | 31774.0    | 30.97        | 5.67          |
| microrouter              | 3.1.3    | ✓      | 30226.0    | 32.57        | 5.39          |
| fastify-big-json         | 4.28.1   | ✓      | 12248.0    | 81.07        | 140.92        |
| express                  | 5.0.1    | ✓      | 9784.2     | 101.57       | 1.74          |
| express-with-middlewares | 5.0.1    | ✓      | 9348.4     | 106.35       | 3.48          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
