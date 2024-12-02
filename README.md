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
* __Run:__ Mon Dec 02 2024 02:22:39 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| bare                     | v20.18.1 | ✗      | 47850.4    | 20.41        | 8.53          |
| polka                    | 0.5.2    | ✓      | 46892.8    | 20.81        | 8.36          |
| fastify                  | 4.28.1   | ✓      | 46496.8    | 21.00        | 8.34          |
| rayo                     | 1.4.6    | ✓      | 46093.6    | 21.19        | 8.22          |
| polkadot                 | 1.0.0    | ✗      | 45588.0    | 21.44        | 8.13          |
| server-base-router       | 7.1.32   | ✓      | 45356.0    | 21.54        | 8.09          |
| server-base              | 7.1.32   | ✗      | 45329.6    | 21.55        | 8.08          |
| micro                    | 10.0.1   | ✗      | 45108.0    | 21.66        | 8.04          |
| connect                  | 3.7.0    | ✗      | 45039.2    | 21.71        | 8.03          |
| connect-router           | 1.3.8    | ✓      | 42294.4    | 23.14        | 7.54          |
| micro-route              | 2.5.0    | ✓      | 42206.4    | 23.19        | 7.53          |
| 0http                    | 3.5.3    | ✓      | 42172.0    | 23.21        | 7.52          |
| h3                       | 1.13.0   | ✗      | 41800.8    | 23.43        | 7.45          |
| h3-router                | 1.13.0   | ✓      | 41320.8    | 23.70        | 7.37          |
| hono                     | 4.6.12   | ✓      | 40885.6    | 23.96        | 7.29          |
| restana                  | 4.9.9    | ✓      | 38203.0    | 25.67        | 6.81          |
| koa                      | 2.15.3   | ✗      | 37854.6    | 25.91        | 6.75          |
| take-five                | 2.0.0    | ✓      | 35637.8    | 27.55        | 12.81         |
| koa-isomorphic-router    | 1.0.1    | ✓      | 34980.0    | 28.09        | 6.24          |
| restify                  | 11.1.0   | ✓      | 34730.6    | 28.28        | 6.26          |
| koa-router               | 12.0.1   | ✓      | 33880.8    | 29.02        | 6.04          |
| hapi                     | 21.3.12  | ✓      | 31664.8    | 31.07        | 5.65          |
| microrouter              | 3.1.3    | ✓      | 30865.2    | 31.88        | 5.50          |
| fastify-big-json         | 4.28.1   | ✓      | 11358.2    | 87.50        | 130.69        |
| express                  | 5.0.1    | ✓      | 9759.9     | 101.84       | 1.74          |
| express-with-middlewares | 5.0.1    | ✓      | 8901.6     | 111.69       | 3.31          |
| trpc-router              | 10.45.2  | ✓      | N/A        | N/A          | N/A           |
