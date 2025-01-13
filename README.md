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
* __Run:__ Mon Jan 13 2025 02:17:15 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 47220.0    | 20.68        | 8.42          |
| fastify                  | 4.29.0   | ✓      | 46922.4    | 20.81        | 8.41          |
| polka                    | 0.5.2    | ✓      | 46250.4    | 21.11        | 8.25          |
| server-base-router       | 7.1.32   | ✓      | 45996.8    | 21.23        | 8.20          |
| connect                  | 3.7.0    | ✗      | 45683.2    | 21.38        | 8.15          |
| server-base              | 7.1.32   | ✗      | 45209.6    | 21.62        | 8.06          |
| micro                    | 10.0.1   | ✗      | 45196.8    | 21.62        | 8.06          |
| rayo                     | 1.4.6    | ✓      | 45174.4    | 21.63        | 8.06          |
| polkadot                 | 1.0.0    | ✗      | 44511.2    | 21.97        | 7.94          |
| connect-router           | 1.3.8    | ✓      | 43207.2    | 22.64        | 7.71          |
| 0http                    | 3.5.3    | ✓      | 42864.0    | 22.84        | 7.64          |
| h3-router                | 1.13.1   | ✓      | 41800.8    | 23.43        | 7.45          |
| micro-route              | 2.5.0    | ✓      | 41573.6    | 23.56        | 7.41          |
| h3                       | 1.13.1   | ✗      | 41445.6    | 23.63        | 7.39          |
| hono                     | 4.6.16   | ✓      | 38780.8    | 25.29        | 6.36          |
| restana                  | 4.9.9    | ✓      | 38054.4    | 25.78        | 6.79          |
| koa                      | 2.15.3   | ✗      | 37027.8    | 26.50        | 6.60          |
| restify                  | 11.1.0   | ✓      | 35573.0    | 27.60        | 6.41          |
| take-five                | 2.0.0    | ✓      | 35024.6    | 28.04        | 12.59         |
| koa-router               | 12.0.1   | ✓      | 34388.0    | 28.58        | 6.13          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 33630.0    | 29.24        | 6.00          |
| hapi                     | 21.3.12  | ✓      | 31587.4    | 31.15        | 5.63          |
| microrouter              | 3.1.3    | ✓      | 30017.6    | 32.81        | 5.35          |
| fastify-big-json         | 4.29.0   | ✓      | 12078.4    | 82.24        | 138.96        |
| express                  | 5.0.1    | ✓      | 10146.6    | 97.93        | 1.81          |
| express-with-middlewares | 5.0.1    | ✓      | 9337.4     | 106.48       | 3.47          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
