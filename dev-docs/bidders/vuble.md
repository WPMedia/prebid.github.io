---
layout: bidder
title: Vuble
description: Prebid Vuble Bidder Adaptor
pbjs: true
biddercode: vuble
media_types: video
gdpr_supported: true
enable_download: false
pbjs_version_notes: not ported to 5.x
sidebarType: 1
---

### Note:
The Vuble adapter requires setup and approval from the Vuble team, even for existing Vuble publishers. Please reach out to your account team, or contact publishers-us@vuble.tv or publishers-fr@vuble.tv for more information.

### Bid params

{: .table .table-bordered .table-striped }
| Name         | Scope    | Description                                                                                       | Example                  | Type      |
|--------------|----------|---------------------------------------------------------------------------------------------------|--------------------------|-----------|
| `env`        | required | The environment. Must be 'net' or 'com'. This information will be given to you by the Vuble team. | `'net'`                  | `string`  |
| `pubId`      | required | Your publisher ID. This information will be given to you by the Vuble team.                       | `3`                      | `integer` |
| `zoneId`     | required | A zone ID for the SSP.                                                                            | `12345`                  | `integer` |
| `referrer`   | optional | The page's referrer. Not mandatory but recommended.                                               | `'http://www.vuble.tv/'` | `string`  |
| `floorPrice` | optional | The desired floor price. If none is given, the floor price will depend on the zone ID.            | `5.00`                   | `float`   |

### Example

```
var adUnits = [
    {
        code: 'test-vuble-instream',
        sizes: [[640, 360]],
        mediaTypes: {
            video: {
                context: 'instream'
            }
        },
        bids: [
            {
                bidder: 'vuble',
                params: {
                    env: 'net',
                    pubId: 18,
                    zoneId: '12345',
                    referrer: "http://www.vuble.tv/",
                    floorPrice: 5.00
                }
            }
        ]
    }
]
```

{: .alert.alert-info :}
Sizes set in the `adUnit` object will also apply to the Vuble bid requests.
