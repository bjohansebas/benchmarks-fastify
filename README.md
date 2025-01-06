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
* __Run:__ Mon Jan 06 2025 02:16:42 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 46662.4    | 20.93        | 8.32          |
| fastify                  | 4.29.0   | ✓      | 46288.0    | 21.11        | 8.30          |
| connect                  | 3.7.0    | ✗      | 46251.2    | 21.13        | 8.25          |
| polka                    | 0.5.2    | ✓      | 45826.4    | 21.30        | 8.17          |
| rayo                     | 1.4.6    | ✓      | 45570.4    | 21.41        | 8.13          |
| server-base-router       | 7.1.32   | ✓      | 45432.8    | 21.52        | 8.10          |
| polkadot                 | 1.0.0    | ✗      | 45294.4    | 21.57        | 8.08          |
| 0http                    | 3.5.3    | ✓      | 45186.4    | 21.64        | 8.06          |
| server-base              | 7.1.32   | ✗      | 45154.4    | 21.65        | 8.05          |
| micro                    | 10.0.1   | ✗      | 44844.8    | 21.79        | 8.00          |
| connect-router           | 1.3.8    | ✓      | 42588.0    | 22.96        | 7.59          |
| h3-router                | 1.13.0   | ✓      | 42407.2    | 23.08        | 7.56          |
| micro-route              | 2.5.0    | ✓      | 42403.2    | 23.05        | 7.56          |
| h3                       | 1.13.0   | ✗      | 41362.4    | 23.69        | 7.38          |
| hono                     | 4.6.16   | ✓      | 39318.4    | 24.92        | 6.45          |
| restana                  | 4.9.9    | ✓      | 38180.0    | 25.68        | 6.81          |
| koa                      | 2.15.3   | ✗      | 36813.4    | 26.65        | 6.56          |
| take-five                | 2.0.0    | ✓      | 34821.4    | 28.24        | 12.52         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34602.4    | 28.38        | 6.17          |
| restify                  | 11.1.0   | ✓      | 34262.2    | 28.67        | 6.18          |
| koa-router               | 12.0.1   | ✓      | 34049.6    | 28.87        | 6.07          |
| hapi                     | 21.3.12  | ✓      | 32189.8    | 30.56        | 5.74          |
| microrouter              | 3.1.3    | ✓      | 30348.8    | 32.44        | 5.41          |
| fastify-big-json         | 4.29.0   | ✓      | 11905.2    | 83.43        | 136.96        |
| express                  | 5.0.1    | ✓      | 10026.4    | 99.10        | 1.79          |
| express-with-middlewares | 5.0.1    | ✓      | 9082.3     | 109.49       | 3.38          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
