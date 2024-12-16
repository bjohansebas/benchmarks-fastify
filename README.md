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
* __Run:__ Mon Dec 16 2024 02:24:23 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 47104.8    | 20.71        | 8.40          |
| connect                  | 3.7.0    | ✗      | 46416.0    | 21.04        | 8.28          |
| polka                    | 0.5.2    | ✓      | 46100.0    | 21.18        | 8.22          |
| rayo                     | 1.4.6    | ✓      | 45692.8    | 21.37        | 8.15          |
| fastify                  | 4.29.0   | ✓      | 45664.8    | 21.39        | 8.19          |
| 0http                    | 3.5.3    | ✓      | 45460.0    | 21.50        | 8.11          |
| polkadot                 | 1.0.0    | ✗      | 45423.2    | 21.53        | 8.10          |
| micro                    | 10.0.1   | ✗      | 45225.6    | 21.60        | 8.07          |
| server-base-router       | 7.1.32   | ✓      | 44876.0    | 21.79        | 8.00          |
| server-base              | 7.1.32   | ✗      | 44753.6    | 21.86        | 7.98          |
| connect-router           | 1.3.8    | ✓      | 44112.8    | 22.17        | 7.87          |
| micro-route              | 2.5.0    | ✓      | 42632.0    | 22.94        | 7.60          |
| h3                       | 1.13.0   | ✗      | 42100.8    | 23.26        | 7.51          |
| h3-router                | 1.13.0   | ✓      | 40253.6    | 24.34        | 7.18          |
| restana                  | 4.9.9    | ✓      | 39654.4    | 24.72        | 7.07          |
| hono                     | 4.6.14   | ✓      | 38896.8    | 25.21        | 6.38          |
| koa                      | 2.15.3   | ✗      | 36389.0    | 26.97        | 6.49          |
| take-five                | 2.0.0    | ✓      | 35377.8    | 27.76        | 12.72         |
| restify                  | 11.1.0   | ✓      | 34562.6    | 28.42        | 6.23          |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34059.0    | 28.85        | 6.07          |
| koa-router               | 12.0.1   | ✓      | 33566.4    | 29.29        | 5.99          |
| hapi                     | 21.3.12  | ✓      | 31239.0    | 31.51        | 5.57          |
| microrouter              | 3.1.3    | ✓      | 29573.2    | 33.31        | 5.27          |
| fastify-big-json         | 4.29.0   | ✓      | 11759.8    | 84.47        | 135.31        |
| express                  | 5.0.1    | ✓      | 9815.9     | 101.28       | 1.75          |
| express-with-middlewares | 5.0.1    | ✓      | 9028.3     | 110.12       | 3.36          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
