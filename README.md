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
* __Run:__ Mon Nov 18 2024 02:19:23 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.0 | ✗      | 48052.0    | 20.35        | 8.57          |
| fastify                  | 4.28.1   | ✓      | 47579.2    | 20.51        | 8.53          |
| polka                    | 0.5.2    | ✓      | 46890.4    | 20.82        | 8.36          |
| connect                  | 3.7.0    | ✗      | 46882.4    | 20.82        | 8.36          |
| rayo                     | 1.4.6    | ✓      | 46597.6    | 20.96        | 8.31          |
| server-base-router       | 7.1.32   | ✓      | 46156.8    | 21.15        | 8.23          |
| server-base              | 7.1.32   | ✗      | 45526.4    | 21.45        | 8.12          |
| micro                    | 10.0.1   | ✗      | 45516.8    | 21.47        | 8.12          |
| 0http                    | 3.5.3    | ✓      | 44887.2    | 21.78        | 8.00          |
| polkadot                 | 1.0.0    | ✗      | 44371.2    | 22.04        | 7.91          |
| micro-route              | 2.5.0    | ✓      | 43346.4    | 22.57        | 7.73          |
| connect-router           | 1.3.8    | ✓      | 43328.0    | 22.58        | 7.73          |
| h3                       | 1.13.0   | ✗      | 41301.6    | 23.72        | 7.36          |
| hono                     | 4.6.10   | ✓      | 40837.6    | 23.98        | 7.28          |
| h3-router                | 1.13.0   | ✓      | 40696.8    | 24.07        | 7.26          |
| restana                  | 4.9.9    | ✓      | 39188.0    | 25.02        | 6.99          |
| koa                      | 2.15.3   | ✗      | 36835.8    | 26.65        | 6.57          |
| take-five                | 2.0.0    | ✓      | 35801.4    | 27.43        | 12.87         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34872.8    | 28.16        | 6.22          |
| restify                  | 11.1.0   | ✓      | 34473.8    | 28.50        | 6.21          |
| koa-router               | 12.0.1   | ✓      | 34253.8    | 28.68        | 6.11          |
| hapi                     | 21.3.12  | ✓      | 31837.8    | 30.90        | 5.68          |
| microrouter              | 3.1.3    | ✓      | 30003.2    | 32.82        | 5.35          |
| fastify-big-json         | 4.28.1   | ✓      | 12022.2    | 82.61        | 138.32        |
| express                  | 5.0.1    | ✓      | 9839.8     | 101.03       | 1.75          |
| express-with-middlewares | 5.0.1    | ✓      | 9180.5     | 108.26       | 3.41          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
