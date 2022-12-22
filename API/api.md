## Base Info

- Endpoint(mainnet): `https://aptomus-mainnet.souffl3.com/api/v1`
- Endpoint(testnet): `https://aptomus-testnet.souffl3.com/api/v1`

## Get top collections

### Request

- Method: Get
- URL: `/topcollections?size={size}`
- Params:
    - `size: <integer>` - page size, max 100

### Response

```
{
    "data": [
        {
            "collection": "Crypto Brends Collection",
            "collection_identity": "GYKKdBYiPXQYZMyGLFEa9uWKZwdTiKakUv4XqutDWRF9TqBpguzoTm79kjcbXzWuHqFwXU64H2PCAR",
            "cover_uri": "https://static.souffl3.com/token-image/GYKKdBYiPXQYZMyGLFEa9uWKZwdTiKakUv4XqutDWRF9TqBpguzoTm79kjcbXzWuHqFwXU64H2PCAR-0.jpg",
            "creator": "0x8201c5a627691e34041e8c0c9ea068811a302a9ed471ae9ab900744a1d1dd70a",
            "description": "MINT LIVE NOW: https://www.launchmynft.io ( Crypto Brends Collection ). 133 Aptos Crypto Brends Collection",
            "floor_price": 100000000.0,
            "listed_count": 56,
            "mark": 0,
            "name": "Crypto Brends Collection",
            "prev_volume": 70500000000,
            "sales": 22,
            "supply": 80.0,
            "total_sales": 34,
            "total_supply": 133.0,
            "total_volume": 221051700000,
            "unique_owners": 7,
            "uri_parsed": true,
            "volume": 150551700000
        },
        ...
    ],
    "error": null,
    "page": 0,
    "size": 50
}

```

## Get collections

### Request

- Method: Get
- URL: `/collections/<collection_identity>`
- Params:
    - `collection_identity: <string>` - base58 encode with a bcs struct (check example)

### Response

```
{
    "collection_id": "y93BeoOA",
    "collection_identity": "GYKKdBYiPXQYZMyGLFEa9uWKZwdTiKakUv4XqutDWRF9TqBpguzoTm79kjcbXzWuHqFwXU64H2PCAR",
    "cover_uri": "https://static.souffl3.com/token-image/GYKKdBYiPXQYZMyGLFEa9uWKZwdTiKakUv4XqutDWRF9TqBpguzoTm79kjcbXzWuHqFwXU64H2PCAR-0.jpg",
    "creator": "0x8201c5a627691e34041e8c0c9ea068811a302a9ed471ae9ab900744a1d1dd70a",
    "description": "MINT LIVE NOW: https://www.launchmynft.io ( Crypto Brends Collection ). 133 Aptos Crypto Brends Collection",
    "discord": "",
    "floor_price": 195000000.0,
    "floor_price_delta_1_day": 0.95,
    "is_rare": false,
    "listed_count": 81,
    "mark": 0,
    "name": "Crypto Brends Collection",
    "owners": 8,
    "royalty": {
        "royalty_payee_address": "0x84195316f7da4c300523dd9ced81ab990d1b71251071e9586b6dfbb1c40d461e",
        "royalty_points_denominator": 10000,
        "royalty_points_numerator": 2000
    },
    "supply": 133.0,
    "total_supply": 133.0,
    "twitter": "",
    "uri_parsed": true,
    "volume": 100100000000,
    "volume_delta_1_day": -0.33555346537742353,
    "website": ""
}
```

## Get NFTs

### Request

- Method: Post
- URL: `/collections/<collection_identity>/tokens?page=<page>&size=<size>`
- Header:
    - `Content-Type: application/json`
- Params (URL):
    - `page: <integer>` - page number, default 0
    - `size: <integer>` - page size, max 100
- Params (Post Body):

```
{
    "buynow": true,   # if only display listed NFT
    "sort": 0,
    "keyword": "",
    "price_min": "",
    "price_max": "",
    "trait": {}
}
```

### Response

```
{
    "data": [
        {
            "collection": "Crypto Brends Collection",
            "collection_identity": "GYKKdBYiPXQYZMyGLFEa9uWKZwdTiKakUv4XqutDWRF9TqBpguzoTm79kjcbXzWuHqFwXU64H2PCAR",
            "collection_name": "Crypto Brends Collection",
            "creator": "0x8201c5a627691e34041e8c0c9ea068811a302a9ed471ae9ab900744a1d1dd70a",
            "description": "MINT LIVE NOW: https://www.launchmynft.io ( Crypto Brends Collection ). 133 Aptos Crypto Brends Collection",
            "holder_address": "0x7b0c0a8fe6877e2b02918571c1030f0f693bc1da892ecb416798ac97f3562d51",
            "image_uri": "https://static.souffl3.com/token-image/3r1H8C2He3nCT6YFYD6xW1o3Ktk8H1ovaoU7q9pfP3DdTyr9HQhbUoxw4DMjBwLDjQtfgg2KoXtv4nsZYBBPZmBbV7hrGYCHMLJCP7P-53344366.jpg",
            "is_listed": true,
            "market": 8,
            "maybe_fungible": false,
            "name": "Crypto Brends #52",
            "offer_price": null,
            "price": 195000000.0,
            "property_version": 0,
            "rank": 0,
            "royalty": {
                "royalty_payee_address": "0x84195316f7da4c300523dd9ced81ab990d1b71251071e9586b6dfbb1c40d461e",
                "royalty_points_denominator": 10000,
                "royalty_points_numerator": 2000
            },
            "score": 0.0,
            "seller_fee_basis_points": 0,
            "supply": 1,
            "symbol": "",
            "token_id": "36pPpK5qR48h4PqwCubEp1abpAfJTZwytVyDWFx4rb8PGcZvQ3WgKcq8aiYmBxJipdQxswf9bifTB642h4dVD6oXnmdvGkHqjGYrPNhDsbXsTQFeG7",
            "token_identity": "36pPpK5qR48h4PqwCubEp1abpAfJTZwytVyDWFx4rb8PGcZvQ3WgKcq8aiYmBxJipdQxswf9bifTB642h4dVD6oXnmdvGkHqjGYrPNhDsbXsTQFeG7",
            "total_supply": 1.0,
            "uri": "https://nftstorage.link/ipfs/bafybeib4fla663p6vrtj6dyfqdg7eb6ctqkakkcyrvq5oj4xmyk2ivfwyi/52",
            "uri_parsed": true
        },
       ...
    ],
    "error": null,
    "page": 0,
    "size": 20
}
```

## NFT Detail

### Request

- Method: Get
- URL: `/tokens/<token_identity>/detail`
- Params:
    - `token_id: <string>` - NFT identity, like collection identity

### Response

```
{
    "info": {
        "ave_holder_time": 19.3,
        "holder_count": 3,
        "last_txn_time": 1667416185090,
        "longest_hold_time": 49.8,
        "max_price": 2000000000.0,
        "min_price": 1500000000.0,
        "mint_time": 1666721500178,
        "price_history": {
            "price_list": [
                1500000000.0,
                2000000000.0
            ],
            "time_list": [
                1667416185090,
                1667194333520
            ]
        },
        "receive_time": [
            1667194333520,
            1667275729583,
            1667416185090
        ],
        "total_market_cap": 27884943130.0,
        "total_txn": 3,
        "trait": {
            "Background": [
                {
                    "proportion": 0.023402340234023402,
                    "value": "Portal"
                }
            ],
            "Clothing": [
                {
                    "proportion": 0.019159058763019158,
                    "value": "White Ripped Tee"
                }
            ],
            "Extra": [
                {
                    "proportion": 0.7730487334447731,
                    "value": "Empty"
                }
            ],
            "Eyes": [
                {
                    "proportion": 0.04616175903304616,
                    "value": "Closed"
                }
            ],
            "Headwear": [
                {
                    "proportion": 0.013244181561013244,
                    "value": "Camera"
                }
            ],
            "Mouth": [
                {
                    "proportion": 0.045776006172045774,
                    "value": "Cigar"
                }
            ],
            "Skin": [
                {
                    "proportion": 0.0774077407740774,
                    "value": "Yellow"
                }
            ]
        }
    },
    "meta": {
        "collection": "Aptos Monkeys",
        "collection_identity": "UDUJzLBsQVhQAU5XxZZcCAMgceQ7ktrDNhKGiHSSgCPrPUbbY7BgS9WSwQXULFc",
        "creator": "0xf932dcb9835e681b21d2f411ef99f4f5e577e6ac299eebee2272a39fb348f702",
        "description": "",
        "holder_address": "0xa3c198ccffbbcce5de0435a54474a96fb472a371c6136c979eb73be7f49d4a63",
        "image_uri": "https://static.souffl3.com/token-image/NzTteL9KnDKvP25BEgw9LM77rQgPkMR6E2RkuuGejY5G8ckv4UcZz3s9fEPjMPMkbWYybupeSH7xjJmkCjmZz1E4Z",
        "is_listed": true,
        "market": 8,
        "maybe_fungible": false,
        "name": "AptosMonkeys #6652",
        "offer_price": null,
        "price": 1440000000.0,
        "property_version": 0,
        "rank": 3310,
        "royalty": {
            "royalty_payee_address": "0x89e272841c2381ec63e7d8ccf6a70bd784b2a9dda6d6425aeb31657f4a5619c0",
            "royalty_points_denominator": "10000",
            "royalty_points_numerator": "500"
        },
        "score": 52.27835254926384,
        "seller_fee_basis_points": 0,
        "supply": 1,
        "symbol": "",
        "token_id": "HEdVJ4ttaafRjtCmdqS73KSAcsWMJRXj1DHbvQQxrM5tnkQJD7B4w1Dhtz3Emt7cx7AiS1e7PQS4jwkuskkhF5U7Z8JC4oK315vF",
        "token_identity": "HEdVJ4ttaafRjtCmdqS73KSAcsWMJRXj1DHbvQQxrM5tnkQJD7B4w1Dhtz3Emt7cx7AiS1e7PQS4jwkuskkhF5U7Z8JC4oK315vF",
        "total_supply": 1.0,
        "uri": "ipfs://bafybeihnochxvsv6h43qvg4snenpeasoml66nwxhuiadfzkefix7vbetyq/6652.json",
        "uri_parsed": true
    }
}
```

## Address hold NFTs

### Request

- Method: Post
- URL: `/accounts/<wallet_address>/tokens?page=<page>&size=<size>`
- Params (URL)
    - `wallet_address: <string>`
    - `page: <integer>` - page number, default 0
    - `size: <integer>` - page size, max 100
- Params (Post Body)
```
{
  "filter": "all"
}
```

### Response

```
{
    "data": [
        {
            "collection": "Sw33t Friends",
            "collection_identity": "H1zJuMZBDTB7GJXq9J2BigYR9VLNCypiMMuRmbfJXS7wmipjwzqRh4XadaoNukW",
            "creator": "0x92a99e9c1f1801e619f9f1b9f5de4a86b70052be8184382e65e11d34cf4e4593",
            "description": "3,333 cutest cats are looking for new owners. Present by Firstdrop Studio (https://firstdrop.xyz), Sw33t Friends is the very first fully on-chain dynamic NFT on Aptos. Owners can fully customize their cat\u2019s image and dress up. All components are tradable NFT.",
            "floor_price": 25000000.0,
            "image_uri": "https://static.souffl3.com/token-image/z8FEzRPZFrCmDKy3VtnSvHUCfrJQAppdNqFMED7Ze2yCyyAs2SuhJjV3EbHcyAvxRCKMNb8VsJUP32rzKggd71L9XL",
            "is_listed": false,
            "last_price": null,
            "listing_price": null,
            "market": null,
            "maybe_fungible": false,
            "name": "Sw33t Friends #2147",
            "offer_price": null,
            "price": null,
            "property_version": 1,
            "royalty": {
                "royalty_payee_address": "0xe92a3eb0f801d432abacb5f9f5af8783172725a01e1fc858cb3dff2a241f6478",
                "royalty_points_denominator": 1000,
                "royalty_points_numerator": 33
            },
            "seller_fee_basis_points": 0,
            "supply": 1,
            "symbol": "",
            "token_id": "MjNBd1Dj",
            "token_identity": "jB3vopBesQov2WnTmCPzxRrBZeCstVNif5tq2XmFF799YE3huYfDrQ48mJ5uU7mGTvapXamCRKnZ62PCVsmJQJwB7dnZAB99RKDzP",
            "total_supply": 1.0,
            "uri": "https://metadata.wav3.net/token/290187C7EAAC280539F93176DD4C1373595FCA224891DC11CD5B36E34D4E793A92A99E9C1F1801E619F9F1B9F5DE4A86B70052BE8184382E65E11D34CF4E45930D537733337420467269656E647313537733337420467269656E6473202332313437.json",
            "uri_parsed": true
        },
        ...
    ],
    "error": null,
    "page": 0,
    "size": 20
}
``` 

## Address listed NFTs
### Request

- Method: Get
- URL: `/accounts/{wallet_address}/listed_tokens?page=<page>&size=<size>`
- Params:
    - `wallet_address: <string>`
    - `page: <integer>` - page number, default 0
    - `size: <integer>` - page size, max 100

### Response

```
{
    "data": [
        {
            "collection": "Souffl3 BakeOff - Sugar",
            "collection_identity": "74LKbM7VAWNVHDTZXmvCgM19PRoSfYRFSuXWZMyp4izoe1eU7BnNhvZtTCqnZmKzAukhNaLBHv5YM",
            "creator": "0xdfad342e78a2f339287bfe7d305887e0fbb9d08d718579280914376ea4331f3b",
            "description": "Souffl3 is No.1 NFT launchpad and marketplace on APTOS.\\nOfficial Website: https://souffl3.com/\\nBake Off 2.0 is 1st and only fully on-chain SFT innovation based on MOVE. Collect, Bake and Win.",
            "floor_price": 100000.0,
            "image_uri": "https://static.souffl3.com/token-image/2W84j9YWvX85PbvxFKJZhCvKCkmxdr82SKZnMWBFpY7FepDQrZfTiXpcAfGJvFK11B8t22y2GRSP6EjVygbKnQTpesJ",
            "is_listed": true,
            "last_price": null,
            "listing_price": 5000000.0,
            "market": 7,
            "maybe_fungible": false,
            "name": "Sugar #21",
            "offer_price": null,
            "price": 5000000.0,
            "property_version": 1,
            "royalty": {
                "royalty_payee_address": "0xcc17650b15187ef35b4c96d37d6c1d34015d88807763e006c3d9fed9d578a251",
                "royalty_points_denominator": 1000,
                "royalty_points_numerator": 35
            },
            "seller_fee_basis_points": 0,
            "supply": 1,
            "symbol": "",
            "token_id": "ojRXoGzO",
            "token_identity": "27KVnZeffUCAN2CBufryGgYNB9aFuzDZK3h5NdWrgrSn8siWLGrVTizZPMyrEZPmmN8Fhw12ejeXUcvNk4pjTeezfeaZ74NzYHqhHZ",
            "total_supply": 1.0,
            "uri": "https://metadata.wav3.net/token/290187C7EAAC280539F93176DD4C1373595FCA224891DC11CD5B36E34D4E793ADFAD342E78A2F339287BFE7D305887E0FBB9D08D718579280914376EA4331F3B17536F7566666C332042616B654F6666202D20537567617209537567617220233231.json",
            "uri_parsed": true
        },
        ...
    ],
    "error": null,
    "page": 0,
    "size": 6
}
``` 
