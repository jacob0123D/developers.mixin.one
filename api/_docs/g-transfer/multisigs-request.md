---
title: Multisigs Request
category: Transfer
order: 31
---

Before you can operate a raw transaction, it should be created a multisigs request first. There are two actions support `sign and unlock`.  
1. A `sign` multisigs request can be `cancel` and `sign`  
2. A `unlock` multisigs request can be `unlock` only, it uses to unlock a `signed` transaction.

###### POST /multisigs/requests

| action | OPTION, String: unlock, sign |
| raw | OPTION, String|

```
// cURL Example
curl -i -XPOST -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzUxMiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1MzMxMTk4MzMsImlhdCI6MTUyNTM0MzgzMywianRpIjoiNTk0ZTBhNmQtMWI2OC00NzQ4LTg2ZWYtYjM5MzQyMTY5ZGQ3Iiwic2lkIjoiYTM0YzA3YTktNzU1ZC00YjU0LTk0YzUtZTQ1ZTlhMmRkNDNlIiwic2lnIjoiMDJhYTE2MTNjMjVlOTNiMGI2OTE1MmUyNTYxOGIyMDQwMGFhYTYyYWIzNGYxYWM2NWJjYzQ2NmY0YjI0ZTM2MCIsInVpZCI6IjA2YWVkMWUzLWJkNzctNGE1OS05OTFhLTViYjVhZTZmYmIwOSJ9.O73fS4WJJG8sFy3heqZoBGTvkQH8iIswsmm6ZK-yRZZXPRQ_miqjB12Wyc-IzFiUqT_63MeH4PspQZ3I9DEie252eiaRluoLzIWPDeq0Wjsp_MtkX4J0nIluAGtQFLNAf8r6pJaT_qqleUieM4DyndIxlkHtloico0Zqp7b3Q3c" "https://api.mixin.one/multisigs/requests --data '{"action": "sign", "raw": "298281....4952f95768b7d1a925c4189b912c343dbb000180e"}'
```

```
// Sample Response
{  
  "data":{  
    "type":"multisig_request",
    "request_id":"ab56be4c-5b20-41c6-a9c3-244f9a433f35",
    "user_id":"ab56be4c-5b20-41c6-a9c3-244f9a433f35",
    "asset_id":"43d61dcd-e413-450d-80b8-101d5e903357",
    "amount":"10",
    "threshold":"2",
    "senders": ["ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35"],
    "receivers": ["ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35"],
    "signers": ["ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35", "ab56be4c-5b20-41c6-a9c3-244f9a433f35"],
    "memo":"hello",
    "action":"sign",
    "state": "spent",
    "transaction_hash": "298281....4952f95768b7d1a925c4189b912c343dbb000180e",
    "raw_transaction": "298281....4952f95768b7d1a925c4189b912c343dbb000180e",
    "created_at":"2018-05-03T10:08:34.859542588Z",
    "code_id":"ab56be4c-5b20-41c6-a9c3-244f9a433f35",
  }
}
```
