---
layout: category
title: "Engineering Guides"
description: "Engineering patterns for reliable iGaming APIs, wallet callbacks, data consistency, and production operations."
permalink: /engineering/
category_name: "Engineering"
articles:
  - title: "Designing Idempotent Wallet Callbacks"
    url: "/engineering/idempotent-wallet-callbacks/"
    description: "Prevent duplicate financial processing under retries and uncertain outcomes."
  - title: "Node.js, MongoDB, and Redis: Scaling API Workloads"
    url: "/engineering/nodejs-mongodb-redis/"
    description: "Measure bottlenecks and use caching, indexes, and concurrency controls responsibly."
---

Wallet callbacks and API workloads are distributed systems problems. These engineering guides focus on correctness under retries and failures, plus the measurement-first approach to scaling Node.js, MongoDB and Redis-backed platforms. Code samples are illustrative and should be validated against your own API contract and versions.
