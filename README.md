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
* __Run:__ Mon Oct 14 2024 02:14:23 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.17.0 | ✗      | 47632.0    | 20.51        | 8.49          |
| fastify                  | 4.28.1   | ✓      | 46907.2    | 20.83        | 8.41          |
| rayo                     | 1.4.6    | ✓      | 46390.4    | 21.05        | 8.27          |
| connect                  | 3.7.0    | ✗      | 46310.4    | 21.09        | 8.26          |
| polka                    | 0.5.2    | ✓      | 45568.8    | 21.43        | 8.13          |
| polkadot                 | 1.0.0    | ✗      | 45481.6    | 21.49        | 8.11          |
| server-base              | 7.1.32   | ✗      | 45347.2    | 21.55        | 8.09          |
| 0http                    | 3.5.3    | ✓      | 44924.8    | 21.78        | 8.01          |
| server-base-router       | 7.1.32   | ✓      | 44664.8    | 21.89        | 7.97          |
| connect-router           | 1.3.8    | ✓      | 44291.2    | 22.08        | 7.90          |
| micro                    | 10.0.1   | ✗      | 43277.6    | 22.60        | 7.72          |
| h3-router                | 1.13.0   | ✓      | 41683.2    | 23.49        | 7.43          |
| micro-route              | 2.5.0    | ✓      | 41462.4    | 23.62        | 7.39          |
| h3                       | 1.13.0   | ✗      | 41189.6    | 23.78        | 7.35          |
| hono                     | 4.6.4    | ✓      | 41053.6    | 23.84        | 7.32          |
| restana                  | 4.9.9    | ✓      | 37425.0    | 26.22        | 6.67          |
| koa                      | 2.15.3   | ✗      | 36119.0    | 27.16        | 6.44          |
| take-five                | 2.0.0    | ✓      | 35649.8    | 27.55        | 12.82         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34996.2    | 28.08        | 6.24          |
| restify                  | 11.1.0   | ✓      | 34909.2    | 28.14        | 6.29          |
| koa-router               | 12.0.1   | ✓      | 33627.2    | 29.24        | 6.00          |
| hapi                     | 21.3.10  | ✓      | 31906.4    | 30.83        | 5.69          |
| microrouter              | 3.1.3    | ✓      | 29526.4    | 33.36        | 5.27          |
| fastify-big-json         | 4.28.1   | ✓      | 11942.0    | 83.16        | 137.40        |
| express                  | 5.0.1    | ✓      | 9993.2     | 99.43        | 1.78          |
| express-with-middlewares | 5.0.1    | ✓      | 9356.4     | 106.27       | 3.48          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
