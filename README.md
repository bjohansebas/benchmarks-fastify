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
* __Run:__ Mon Dec 23 2024 02:14:14 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 46574.4    | 20.97        | 8.31          |
| fastify                  | 4.29.0   | ✓      | 46292.0    | 21.10        | 8.30          |
| connect                  | 3.7.0    | ✗      | 46208.8    | 21.13        | 8.24          |
| polka                    | 0.5.2    | ✓      | 46092.0    | 21.18        | 8.22          |
| rayo                     | 1.4.6    | ✓      | 45781.6    | 21.32        | 8.16          |
| polkadot                 | 1.0.0    | ✗      | 45448.0    | 21.51        | 8.10          |
| server-base              | 7.1.32   | ✗      | 45188.0    | 21.64        | 8.06          |
| server-base-router       | 7.1.32   | ✓      | 44882.4    | 21.79        | 8.00          |
| micro                    | 10.0.1   | ✗      | 44838.4    | 21.79        | 8.00          |
| 0http                    | 3.5.3    | ✓      | 44362.4    | 22.05        | 7.91          |
| connect-router           | 1.3.8    | ✓      | 43536.8    | 22.47        | 7.76          |
| h3                       | 1.13.0   | ✗      | 42602.4    | 22.98        | 7.60          |
| micro-route              | 2.5.0    | ✓      | 42167.2    | 23.20        | 7.52          |
| hono                     | 4.6.14   | ✓      | 40353.6    | 24.28        | 6.62          |
| h3-router                | 1.13.0   | ✓      | 39708.0    | 24.68        | 7.08          |
| restana                  | 4.9.9    | ✓      | 38010.4    | 25.81        | 6.78          |
| koa                      | 2.15.3   | ✗      | 37202.4    | 26.38        | 6.63          |
| take-five                | 2.0.0    | ✓      | 35547.0    | 27.63        | 12.78         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35306.6    | 27.82        | 6.30          |
| restify                  | 11.1.0   | ✓      | 34588.6    | 28.41        | 6.23          |
| koa-router               | 12.0.1   | ✓      | 34233.0    | 28.70        | 6.11          |
| hapi                     | 21.3.12  | ✓      | 31157.6    | 31.60        | 5.56          |
| microrouter              | 3.1.3    | ✓      | 30316.0    | 32.47        | 5.41          |
| fastify-big-json         | 4.29.0   | ✓      | 11760.6    | 84.46        | 135.32        |
| express                  | 5.0.1    | ✓      | 9908.6     | 100.31       | 1.77          |
| express-with-middlewares | 5.0.1    | ✓      | 9077.7     | 109.52       | 3.38          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
