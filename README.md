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
* __Run:__ Mon Jan 27 2025 02:11:52 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 48132.0    | 20.33        | 8.58          |
| polka                    | 0.5.2    | ✓      | 46953.6    | 20.80        | 8.37          |
| fastify                  | 4.29.0   | ✓      | 46864.0    | 20.84        | 8.40          |
| polkadot                 | 1.0.0    | ✗      | 46845.6    | 20.85        | 8.35          |
| connect                  | 3.7.0    | ✗      | 46428.0    | 21.03        | 8.28          |
| server-base              | 7.1.32   | ✗      | 46133.6    | 21.14        | 8.23          |
| rayo                     | 1.4.6    | ✓      | 46089.6    | 21.17        | 8.22          |
| server-base-router       | 7.1.32   | ✓      | 45840.0    | 21.28        | 8.18          |
| micro                    | 10.0.1   | ✗      | 45795.2    | 21.33        | 8.17          |
| 0http                    | 3.5.3    | ✓      | 45753.6    | 21.36        | 8.16          |
| h3                       | 1.14.0   | ✗      | 45119.2    | 21.67        | 8.05          |
| h3-router                | 1.14.0   | ✓      | 44440.0    | 22.01        | 7.93          |
| connect-router           | 1.3.8    | ✓      | 43857.6    | 22.28        | 7.82          |
| micro-route              | 2.5.0    | ✓      | 42905.6    | 22.78        | 7.65          |
| hono                     | 4.6.19   | ✓      | 40472.8    | 24.21        | 6.64          |
| restana                  | 4.9.9    | ✓      | 39641.6    | 24.73        | 7.07          |
| koa                      | 2.15.3   | ✗      | 38051.2    | 25.78        | 6.79          |
| restify                  | 11.1.0   | ✓      | 36038.2    | 27.23        | 6.50          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35992.6    | 27.27        | 6.42          |
| take-five                | 2.0.0    | ✓      | 35844.6    | 27.40        | 12.89         |
| koa-router               | 12.0.1   | ✓      | 35055.4    | 28.04        | 6.25          |
| hapi                     | 21.3.12  | ✓      | 32157.8    | 30.59        | 5.73          |
| microrouter              | 3.1.3    | ✓      | 30864.0    | 31.90        | 5.50          |
| fastify-big-json         | 4.29.0   | ✓      | 11876.4    | 83.62        | 136.65        |
| express                  | 5.0.1    | ✓      | 10531.6    | 94.34        | 1.88          |
| express-with-middlewares | 5.0.1    | ✓      | 9259.6     | 107.35       | 3.44          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
