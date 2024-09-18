# Metrics
* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v20.17.0`
* __Run:__ Wed Sep 18 2024 01:53:04 GMT+0000 (Coordinated Universal Time)
* __Method:__ `npm run metrics` (samples: 5)
* __startup:__ time elapsed to setup the application
* __listen:__ time elapsed until the http server is ready to accept requests (cold start)

| | startup(ms) | listen(ms) |
|-| -       | -      |
| 1-startup-routes-schema.cjs | 104.29 | 149.50 |
| 1-startup-routes.cjs | 107.29 | 117.76 |
| 10-startup-routes-schema.cjs | 108.38 | 163.65 |
| 10-startup-routes.cjs | 109.61 | 122.14 |
| 100-startup-routes-schema.cjs | 119.03 | 258.71 |
| 100-startup-routes.cjs | 123.83 | 145.69 |
| 1000-startup-routes-schema.cjs | 303.70 | 1057.01 |
| 1000-startup-routes.cjs | 294.48 | 412.02 |
| 10000-startup-routes-schema.cjs | 5274.67 | 12285.29 |
| 10000-startup-routes.cjs | 7139.32 | 8502.38 |
| startup-listen.cjs | 105.81 | 117.00 |
