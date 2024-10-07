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
* __Node:__ `v20.17.0`
* __Run:__ Mon Oct 07 2024 02:14:46 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| connect                  | 3.7.0    | ✗      | 47111.2    | 20.71        | 8.40          |
| fastify                  | 4.28.1   | ✓      | 47089.6    | 20.73        | 8.44          |
| bare                     | v20.17.0 | ✗      | 47041.6    | 20.75        | 8.39          |
| polka                    | 0.5.2    | ✓      | 46474.4    | 21.01        | 8.29          |
| polkadot                 | 1.0.0    | ✗      | 46439.2    | 21.04        | 8.28          |
| 0http                    | 3.5.3    | ✓      | 45730.4    | 21.37        | 8.16          |
| rayo                     | 1.4.6    | ✓      | 45646.4    | 21.41        | 8.14          |
| server-base-router       | 7.1.32   | ✓      | 45037.6    | 21.72        | 8.03          |
| micro                    | 10.0.1   | ✗      | 44411.2    | 22.02        | 7.92          |
| server-base              | 7.1.32   | ✗      | 44356.0    | 22.04        | 7.91          |
| micro-route              | 2.5.0    | ✓      | 43212.0    | 22.63        | 7.71          |
| h3                       | 1.13.0   | ✗      | 43012.8    | 22.75        | 7.67          |
| connect-router           | 1.3.8    | ✓      | 42947.2    | 22.77        | 7.66          |
| h3-router                | 1.13.0   | ✓      | 41078.4    | 23.85        | 7.33          |
| hono                     | 4.6.3    | ✓      | 40224.8    | 24.35        | 7.17          |
| restana                  | 4.9.9    | ✓      | 39512.0    | 24.81        | 7.05          |
| koa                      | 2.15.3   | ✗      | 37075.8    | 26.47        | 6.61          |
| take-five                | 2.0.0    | ✓      | 35489.0    | 27.68        | 12.76         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35463.8    | 27.69        | 6.32          |
| restify                  | 11.1.0   | ✓      | 35013.4    | 28.05        | 6.31          |
| koa-router               | 12.0.1   | ✓      | 33718.8    | 29.15        | 6.01          |
| hapi                     | 21.3.10  | ✓      | 31420.2    | 31.32        | 5.60          |
| microrouter              | 3.1.3    | ✓      | 30370.8    | 32.41        | 5.42          |
| fastify-big-json         | 4.28.1   | ✓      | 11804.4    | 84.15        | 135.80        |
| express                  | 5.0.0    | ✓      | 10417.8    | 95.39        | 1.86          |
| express-with-middlewares | 5.0.0    | ✓      | 9259.0     | 107.38       | 3.44          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
