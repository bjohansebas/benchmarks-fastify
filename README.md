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
* __Run:__ Mon Sep 23 2024 02:11:48 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.17.0 | ✗      | 48136.0    | 20.30        | 8.58          |
| connect                  | 3.7.0    | ✗      | 46068.8    | 21.20        | 8.22          |
| fastify                  | 4.28.1   | ✓      | 46036.0    | 21.21        | 8.25          |
| polka                    | 0.5.2    | ✓      | 45916.0    | 21.27        | 8.19          |
| server-base-router       | 7.1.32   | ✓      | 45711.2    | 21.37        | 8.15          |
| rayo                     | 1.4.6    | ✓      | 45583.2    | 21.43        | 8.13          |
| 0http                    | 3.5.3    | ✓      | 45580.0    | 21.45        | 8.13          |
| server-base              | 7.1.32   | ✗      | 45366.4    | 21.54        | 8.09          |
| micro                    | 10.0.1   | ✗      | 45313.6    | 21.56        | 8.08          |
| polkadot                 | 1.0.0    | ✗      | 44407.2    | 22.02        | 7.92          |
| micro-route              | 2.5.0    | ✓      | 43242.4    | 22.61        | 7.71          |
| h3                       | 1.12.0   | ✗      | 43124.0    | 22.69        | 7.69          |
| connect-router           | 1.3.8    | ✓      | 42643.2    | 22.94        | 7.60          |
| h3-router                | 1.12.0   | ✓      | 41003.2    | 23.89        | 7.31          |
| hono                     | 4.6.2    | ✓      | 40625.6    | 24.10        | 7.25          |
| restana                  | 4.9.9    | ✓      | 39699.2    | 24.69        | 7.08          |
| koa                      | 2.15.3   | ✗      | 37040.6    | 26.49        | 6.61          |
| take-five                | 2.0.0    | ✓      | 35433.8    | 27.71        | 12.74         |
| restify                  | 11.1.0   | ✓      | 35110.6    | 27.98        | 6.33          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34205.4    | 28.73        | 6.10          |
| koa-router               | 12.0.1   | ✓      | 33893.0    | 29.00        | 6.04          |
| hapi                     | 21.3.10  | ✓      | 31356.8    | 31.39        | 5.59          |
| microrouter              | 3.1.3    | ✓      | 30896.0    | 31.87        | 5.51          |
| fastify-big-json         | 4.28.1   | ✓      | 11685.8    | 85.02        | 134.45        |
| express                  | 5.0.0    | ✓      | 10346.4    | 96.05        | 1.85          |
| express-with-middlewares | 5.0.0    | ✓      | 9059.6     | 109.76       | 3.37          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
