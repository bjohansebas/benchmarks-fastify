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
* __Run:__ Mon Sep 30 2024 02:14:53 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.17.0 | ✗      | 47709.6    | 20.47        | 8.51          |
| connect                  | 3.7.0    | ✗      | 47173.6    | 20.69        | 8.41          |
| polka                    | 0.5.2    | ✓      | 46976.8    | 20.79        | 8.38          |
| rayo                     | 1.4.6    | ✓      | 46555.2    | 20.97        | 8.30          |
| server-base-router       | 7.1.32   | ✓      | 46112.0    | 21.16        | 8.22          |
| fastify                  | 4.28.1   | ✓      | 46036.0    | 21.21        | 8.25          |
| polkadot                 | 1.0.0    | ✗      | 46032.8    | 21.22        | 8.21          |
| server-base              | 7.1.32   | ✗      | 45919.2    | 21.26        | 8.19          |
| micro                    | 10.0.1   | ✗      | 45632.8    | 21.41        | 8.14          |
| 0http                    | 3.5.3    | ✓      | 45596.0    | 21.43        | 8.13          |
| connect-router           | 1.3.8    | ✓      | 43846.4    | 22.30        | 7.82          |
| micro-route              | 2.5.0    | ✓      | 43052.8    | 22.72        | 7.68          |
| h3-router                | 1.12.0   | ✓      | 40942.4    | 23.92        | 7.30          |
| hono                     | 4.6.3    | ✓      | 40732.0    | 24.06        | 7.26          |
| h3                       | 1.12.0   | ✗      | 40217.6    | 24.37        | 7.17          |
| restana                  | 4.9.9    | ✓      | 39543.2    | 24.79        | 7.05          |
| koa                      | 2.15.3   | ✗      | 37498.6    | 26.17        | 6.69          |
| take-five                | 2.0.0    | ✓      | 35444.2    | 27.70        | 12.74         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34974.6    | 28.09        | 6.24          |
| restify                  | 11.1.0   | ✓      | 34897.6    | 28.15        | 6.29          |
| koa-router               | 12.0.1   | ✓      | 33672.8    | 29.19        | 6.01          |
| hapi                     | 21.3.10  | ✓      | 32148.4    | 30.60        | 5.73          |
| microrouter              | 3.1.3    | ✓      | 30549.6    | 32.23        | 5.45          |
| fastify-big-json         | 4.28.1   | ✓      | 11483.4    | 86.53        | 132.12        |
| express                  | 5.0.0    | ✓      | 10304.4    | 96.46        | 1.84          |
| express-with-middlewares | 5.0.0    | ✓      | 9212.0     | 107.93       | 3.43          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
