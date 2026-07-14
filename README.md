# CS2Cap Python SDK

Typed Python client for the [CS2Cap](https://cs2cap.com) market-data API — CS2 item prices,
buy orders, sales history, and analytics across dozens of providers.

[![PyPI](https://img.shields.io/pypi/v/cs2cap)](https://pypi.org/project/cs2cap/)

## Install

```bash
pip install cs2cap
```

## Quickstart

Set your API key in the environment. You can generate one from the Account page after
verifying your email address at [cs2cap.com](https://cs2cap.com).

```bash
export CS2C_API_KEY="sk_your_key_here"
```

Verify the install with a small catalog request:

```python
import os

import cs2cap

configuration = cs2cap.Configuration(access_token=os.environ["CS2C_API_KEY"])

with cs2cap.ApiClient(configuration) as client:
    api = cs2cap.ItemsApi(client)
    response = api.list_items(q="AK-47", rarity_name="Covert", limit=5)

    print(client.sanitize_for_serialization(response))
```

## Documentation

Full endpoint reference, guides, and tier details are at
[docs.cs2cap.com](https://docs.cs2cap.com). See the
[changelog](https://docs.cs2cap.com/changelog) for API and SDK updates.

## About this package

This SDK is generated from the public OpenAPI spec (`openapi.json`, included in this repo).
If you hit a bug in the generated client, please open an issue or PR on this repo — fixes are
applied in the generator pipeline rather than as hand-patches to the published package.
