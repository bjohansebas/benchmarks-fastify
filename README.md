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
* __Run:__ Mon Oct 21 2024 02:14:40 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| fastify                  | 4.28.1   | ✓      | 47335.2    | 20.60        | 8.49          |
| connect                  | 3.7.0    | ✗      | 47185.6    | 20.67        | 8.41          |
| polka                    | 0.5.2    | ✓      | 46796.8    | 20.87        | 8.35          |
| bare                     | v20.18.0 | ✗      | 46620.8    | 20.95        | 8.31          |
| rayo                     | 1.4.6    | ✓      | 46585.6    | 20.97        | 8.31          |
| server-base-router       | 7.1.32   | ✓      | 46397.6    | 21.05        | 8.28          |
| polkadot                 | 1.0.0    | ✗      | 45829.6    | 21.32        | 8.17          |
| server-base              | 7.1.32   | ✗      | 45772.8    | 21.33        | 8.16          |
| micro                    | 10.0.1   | ✗      | 45745.6    | 21.36        | 8.16          |
| 0http                    | 3.5.3    | ✓      | 45355.2    | 21.55        | 8.09          |
| h3                       | 1.13.0   | ✗      | 42950.4    | 22.79        | 7.66          |
| micro-route              | 2.5.0    | ✓      | 42080.8    | 23.27        | 7.50          |
| connect-router           | 1.3.8    | ✓      | 41931.2    | 23.35        | 7.48          |
| h3-router                | 1.13.0   | ✓      | 41350.4    | 23.69        | 7.37          |
| hono                     | 4.6.5    | ✓      | 40381.6    | 24.25        | 7.20          |
| restana                  | 4.9.9    | ✓      | 39207.4    | 25.01        | 6.99          |
| koa                      | 2.15.3   | ✗      | 37019.4    | 26.50        | 6.60          |
| take-five                | 2.0.0    | ✓      | 35816.8    | 27.41        | 12.88         |
| restify                  | 11.1.0   | ✓      | 35461.8    | 27.70        | 6.39          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34949.4    | 28.11        | 6.23          |
| koa-router               | 12.0.1   | ✓      | 34340.4    | 28.61        | 6.12          |
| hapi                     | 21.3.10  | ✓      | 31561.0    | 31.17        | 5.63          |
| microrouter              | 3.1.3    | ✓      | 29810.8    | 33.04        | 5.32          |
| fastify-big-json         | 4.28.1   | ✓      | 12033.0    | 82.53        | 138.45        |
| express                  | 5.0.1    | ✓      | 9711.0     | 102.35       | 1.73          |
| express-with-middlewares | 5.0.1    | ✓      | 9131.1     | 108.88       | 3.40          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
