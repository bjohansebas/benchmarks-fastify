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
* __Run:__ Mon Nov 04 2024 02:15:00 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| polka                    | 0.5.2    | ✓      | 47384.8    | 20.59        | 8.45          |
| fastify                  | 4.28.1   | ✓      | 46658.4    | 20.93        | 8.37          |
| bare                     | v20.18.0 | ✗      | 46410.4    | 21.04        | 8.28          |
| polkadot                 | 1.0.0    | ✗      | 46245.6    | 21.12        | 8.25          |
| rayo                     | 1.4.6    | ✓      | 46111.2    | 21.17        | 8.22          |
| server-base-router       | 7.1.32   | ✓      | 45879.2    | 21.28        | 8.18          |
| connect                  | 3.7.0    | ✗      | 45592.0    | 21.44        | 8.13          |
| server-base              | 7.1.32   | ✗      | 45496.8    | 21.47        | 8.11          |
| micro                    | 10.0.1   | ✗      | 45078.4    | 21.67        | 8.04          |
| connect-router           | 1.3.8    | ✓      | 43248.8    | 22.62        | 7.71          |
| 0http                    | 3.5.3    | ✓      | 43128.8    | 22.69        | 7.69          |
| micro-route              | 2.5.0    | ✓      | 42952.8    | 22.78        | 7.66          |
| h3                       | 1.13.0   | ✗      | 42596.8    | 22.98        | 7.60          |
| h3-router                | 1.13.0   | ✓      | 40995.2    | 23.90        | 7.31          |
| hono                     | 4.6.8    | ✓      | 40258.4    | 24.33        | 7.18          |
| restana                  | 4.9.9    | ✓      | 38362.4    | 25.57        | 6.84          |
| koa                      | 2.15.3   | ✗      | 37233.4    | 26.36        | 6.64          |
| take-five                | 2.0.0    | ✓      | 36028.2    | 27.23        | 12.95         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 35017.4    | 28.07        | 6.24          |
| restify                  | 11.1.0   | ✓      | 34969.8    | 28.10        | 6.30          |
| koa-router               | 12.0.1   | ✓      | 34152.2    | 28.77        | 6.09          |
| hapi                     | 21.3.12  | ✓      | 30998.0    | 31.74        | 5.53          |
| microrouter              | 3.1.3    | ✓      | 30491.6    | 32.29        | 5.44          |
| fastify-big-json         | 4.28.1   | ✓      | 11928.4    | 83.28        | 137.24        |
| express                  | 5.0.1    | ✓      | 9825.0     | 101.15       | 1.75          |
| express-with-middlewares | 5.0.1    | ✓      | 9197.0     | 108.11       | 3.42          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
