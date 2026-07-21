# CardPriceLab Scheduler

This repository contains only the public scheduling configuration for the
[CardPriceLab](https://cardpricelab.com) Smart Engine.

The application source code, database schema, matching logic, valuation logic,
and operational data are not stored here.

## Security

Scheduled jobs request a short-lived GitHub Actions OIDC token for the audience
`cardpricelab-smart-engine`. The CardPriceLab backend validates the token
signature, issuer, audience, repository, branch, and event type before accepting
a request. No application secret is stored in this repository.

## Responsibility

The workflow triggers four bounded backend modes:

- `discovery`: discover newly listed marketplace inventory;
- `refresh`: check known listings and update lifecycle state;
- `catalog`: synchronize bounded catalog batches;
- `maintenance`: refresh derived operational data.

Copyright (c) 2026 dealonly0-lab. All rights reserved.
