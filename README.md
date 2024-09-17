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
* __Run:__ Tue Sep 17 2024 22:15:05 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.17.0 | ✗      | 48182.4    | 20.28        | 8.59          |
| fastify                  | 4.28.1   | ✓      | 47084.0    | 20.72        | 8.44          |
| connect                  | 3.7.0    | ✗      | 46741.6    | 20.90        | 8.34          |
| polka                    | 0.5.2    | ✓      | 46504.8    | 20.99        | 8.29          |
| polkadot                 | 1.0.0    | ✗      | 46436.0    | 21.04        | 8.28          |
| server-base-router       | 7.1.32   | ✓      | 46240.0    | 21.13        | 8.25          |
| server-base              | 7.1.32   | ✗      | 46095.2    | 21.18        | 8.22          |
| rayo                     | 1.4.6    | ✓      | 45798.4    | 21.33        | 8.17          |
| micro                    | 10.0.1   | ✗      | 45124.0    | 21.65        | 8.05          |
| 0http                    | 3.5.3    | ✓      | 44927.2    | 21.77        | 8.01          |
| connect-router           | 1.3.8    | ✓      | 43926.4    | 22.24        | 7.83          |
| h3-router                | 1.12.0   | ✓      | 43014.4    | 22.75        | 7.67          |
| micro-route              | 2.5.0    | ✓      | 42648.0    | 22.94        | 7.61          |
| h3                       | 1.12.0   | ✗      | 42139.2    | 23.24        | 7.51          |
| hono                     | 4.6.2    | ✓      | 40972.0    | 23.92        | 7.31          |
| restana                  | 4.9.9    | ✓      | 40433.6    | 24.23        | 7.21          |
| koa                      | 2.15.3   | ✗      | 37672.2    | 26.03        | 6.72          |
| take-five                | 2.0.0    | ✓      | 35609.4    | 27.58        | 12.80         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35035.6    | 28.05        | 6.25          |
| restify                  | 11.1.0   | ✓      | 34944.0    | 28.14        | 6.30          |
| koa-router               | 12.0.1   | ✓      | 34143.4    | 28.77        | 6.09          |
| hapi                     | 21.3.10  | ✓      | 32397.6    | 30.35        | 5.78          |
| microrouter              | 3.1.3    | ✓      | 29829.2    | 33.01        | 5.32          |
| fastify-big-json         | 4.28.1   | ✓      | 11729.4    | 84.71        | 134.95        |
| express                  | 5.0.0    | ✓      | 9702.4     | 102.48       | 1.73          |
| express-with-middlewares | 5.0.0    | ✓      | 9017.0     | 110.30       | 3.35          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
