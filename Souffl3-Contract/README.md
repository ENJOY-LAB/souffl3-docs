# Souffl3 Aptos Fixed Price Market

souffl3_contract_address: 0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4


## batch list 


| function id | generics type | parameters  |
|------|--|---|
| {{souffl3_contract_address}}::FixedPriceMarket::batch_list_script | 0x1::aptos_coin::AptosCoin |  token_owner: &signer<br>creator_lists: vector\<address\><br>collection_lists: vector\<String\><br>name_lists: vector\<String\><br>property_version_lists: vector\<u64\><br>token_amount_lists: vector\<u64\><br>coin_amount_lists: vector\<u64\><br>locked_until_secs_lists: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>   |


#### parameters detail
| parameter name | type | detail  |
|------|--|---|
| token_owner | &signer | transaction signer |
| creator_list | vector\<address\> | NFT creator list |
| collection_list | vector\<String\> | NFT collection name list |
| name_list | vector\<String\> | NFT token name list |
| property_version_list | vector\<u64\> | NFT property version list |
| token_amount_list | vector\<u64\> | NFT token amount list |
| coin_ammout_list | vector\<u64\> | NFT listing price list |
| locked_until_secs_list | vector\<u64\> | NFT listing end time list（0 indicate not be ended） |
| market_address_lists | vector\<address\> | NFT market address list，use {{souffl3_contract_address}} |
| market_name_list | vector\<String\> | NFT market name list， use "souffle" |

### batch list transaction example

https://explorer.aptoslabs.com/txn/55095677


### batch ist payload example

```
{
  "function": "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4::FixedPriceMarket::batch_list_script",
  "type_arguments": [
    "0x1::aptos_coin::AptosCoin"
  ],
  "arguments": [
    [
      "0xf51d0def60d022111012fca89cd8abdb5623db94b8d09037372e4b4c6747dc9e",
      "0xdfad342e78a2f339287bfe7d305887e0fbb9d08d718579280914376ea4331f3b",
    ],
    [
      "Souffl3 BakeOff - Flour",
      "Souffl3 BakeOff - Sugar",
    ],
    [
      "Flour #14423",
      "Sugar #16253",
    ],
    [
      "1",
      "1",
    ],
    [
      "1",
      "1",
    ],
    [
      "100000",
      "100000",
    ],
    [
      "0",
      "0",
    ],
    [
      "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4",
      "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4",
    ],
    [
      "souffle",
      "souffle",
    ]
  ],
  "type": "entry_function_payload"
}
```

##  batch buy 

| function id | generics type | parameters  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_buy_script_V1 | - | sender: &signer<br>markets: vector\<String\><br>listers: vector\<address\><br>prices: vector\<u64\><br>amounts: vector\<u64\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>  |

#### parameters detail
| parameter name | type | detail  |
|------|--|---|
| sender | &signer | transaction signer |
| markets | vector\<String\> | NFT list market，support（"Souffl3" / "BlueMove" / "Topaz") currently |
| listers | vector\<address\> | NFT lister list |
| prices | vector\<u64\> | NFT listing price list |
| amounts | vector\<u64\> | NFT token amount list |
| creators | vector\<address\> | NFT creator list |
| collections | vector\<String\> | NFT collection name list |
| names | vector\<String\> | NFT token name list |
| property_versions | vector\<u64\> | NFT property version list |
| market_address_list | vector\<address\> | NFT market address list，if listing market is "Souffl3", just push back {{souffl3_contract_address}} ，other markets don't need to do that |
| market_name_list | vector\<String\> | NFT market name list，if listing market is "Souffl3", push back "souffle" into vector，other markets don't need to do that |

### batch buy transaction example

https://explorer.aptoslabs.com/txn/55050185


### batch buy payload example

```
{
  "function": "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4::Aggregator::batch_buy_script_V1",
  "type_arguments": [],
  "arguments": [
    [
      "Souffl3"
    ],
    [],
    [
      "280000000"
    ],
    [
      "1"
    ],
    [
      "0xe7fbaab107f818f91111bde00f31308981fde6236a788bf2c4bbc28d72e97cbb"
    ],
    [
      "Aptos Farmlands"
    ],
    [
      "Farm Land #45"
    ],
    [
      "0"
    ],
    [
      "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4"
    ],
    [
      "souffle"
    ]
  ],
  "type": "entry_function_payload"
}

```

## batch delist

| function id | generics type | parameters  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_delist_script_V1 | - | sender: &signer<br>markets: vector\<String\><br>amounts: vector\<u64\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>  |


#### parameters detail
| parameter name | type | detail  |
|------|--|---|
| sender | &signer | transaction signer |
| markets | vector\<String\> | NFT listing market，support（"Souffl3" / "BlueMove" / "Topaz") currently |
| amounts | vector\<u64\> | NFT token amount list |
| creators | vector\<address\> | NFT creator list |
| collections | vector\<String\> | NFT collection name list |
| names | vector\<String\> | NFT token name list |
| property_versions | vector\<u64\> | NFT property version list |
| market_address_list | vector\<address\> | NFT market address list，if listing market is "Souffl3", just push back {{souffl3_contract_address}} ，other markets don't need to do that |
| market_name_list | vector\<String\> | NFT market name list，if listing market is "Souffl3", push back "souffle" into vector，other markets don't need to do that |

### batch delist transaction example

https://explorer.aptoslabs.com/txn/55014220

### batch delist payload example

```
{
  "function": "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4::Aggregator::batch_delist_script_V1",
  "type_arguments": [],
  "arguments": [
    [
      "Souffl3"
    ],
    [
      "1"
    ],
    [
      "0x829290d9fc84d4da0db3f9274d7a4bf098630055f996da415c60fc9ebd0ea982"
    ],
    [
      "P-GANG"
    ],
    [
      "P-GANG #123"
    ],
    [
      "0"
    ],
    [
      "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4"
    ],
    [
      "souffle"
    ]
  ],
  "type": "entry_function_payload"
}
```

## batch_change_price


| function id | generics type | parameters  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_change_price_script_V1 | - | sender: &signer<br>markets: vector\<String\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>amounts: vector\<u64\><br>prices: vector\<u64\><br>locked_until_secs_list: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_list: vector\<String\>  |

#### parameters detail
| parameter name | type | detail |
|------|--|---|
| sender | &signer | transaction signer |
| markets | vector\<String\> | NFT listing market，support（"Souffl3" / "BlueMove" / "Topaz") currently |
| creators | vector\<address\> | NFT creator list |
| collections | vector\<String\> | NFT collection name list |
| names | vector\<String\> | NFT token name list |
| property_versions | vector\<u64\> | NFT property version list |
| amounts | vector\<u64\> | NFT token amount list |
| prices | vector\<u64\> | NFT changing price list |
| locked_until_secs_list | vector\<u64\> | NFT listing end time list（0 indicate not be ended）|
| market_address_list | vector\<address\> | NFT market address list，if listing market is "Souffl3", just push back {{souffl3_contract_address}} ，other markets don't need to do that |
| market_name_list | vector\<String\> | NFT market name list，if listing market is "Souffl3", push back "souffle" into vector，other markets don't need to do that |


### batch change price transaction example 

https://explorer.aptoslabs.com/txn/55091778

### batch change price payload example

```
{
  "function": "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4::Aggregator::batch_change_price_script_V1",
  "type_arguments": [],
  "arguments": [
    [
      "Souffl3"
    ],
    [
      "0x1a79b04bd7c2096ca358351d6e80e4b877d3cdc102af7955addb51dac4dc63eb"
    ],
    [
      "Oishii Moechann"
    ],
    [
      "Oishii Moechann #2803"
    ],
    [
      "1"
    ],
    [
      "1"
    ],
    [
      "45000000"
    ],
    [
      "0"
    ],
    [
      "0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4"
    ],
    [
      "souffle"
    ]
  ],
  "type": "entry_function_payload"
}
```
