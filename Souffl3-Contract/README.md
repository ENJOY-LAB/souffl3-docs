# Souffl3 Aptos Fixed Price Market

souffl3_contract_address: 0xf6994988bd40261af9431cd6dd3fcf765569719e66322c7a05cc78a89cd366d4


## 批量挂单 batch list 


| 函数id | 入参泛型 | 入参  |
|------|--|---|
| {{souffl3_contract_address}}::FixedPriceMarket::batch_list_script | 0x1::aptos_coin::AptosCoin |  token_owner: &signer<br>creator_lists: vector\<address\><br>collection_lists: vector\<String\><br>name_lists: vector\<String\><br>property_version_lists: vector\<u64\><br>token_amount_lists: vector\<u64\><br>coin_amount_lists: vector\<u64\><br>locked_until_secs_lists: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>   |


#### 入参详情
| 参数名 | 类型 | 说明  |
|------|--|---|
| token_owner | &signer | 交易签名者 |
| creator_list | vector\<address\> | NFT creator 列表 |
| collection_list | vector\<String\> | NFT collection name 列表 |
| name_list | vector\<String\> | NFT token name 列表 |
| property_version_list | vector\<u64\> | NFT property version 列表 |
| token_amount_list | vector\<u64\> | NFT token amount 列表 |
| coin_ammout_list | vector\<u64\> | NFT 挂单价格列表 |
| locked_until_secs_list | vector\<u64\> | NFT 挂单结束时间（0 为无结束时间挂单，市场上挂单基本都是 0） |
| market_address_lists | vector\<address\> | NFT market address 列表，同 {{souffl3_contract_address}} |
| market_name_list | vector\<String\> | NFT market name 列表，传入 "souffle" 即可 |

### 批量挂单 batch list transaction 示例

https://explorer.aptoslabs.com/txn/55095677


### 批量挂单 batch ist payload 示例

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

## 批量购买 batch buy 

| 函数id | 入参泛型 | 入参  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_buy_script_V1 | 无 | sender: &signer<br>markets: vector\<String\><br>listers: vector\<address\><br>prices: vector\<u64\><br>amounts: vector\<u64\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>  |

#### 入参详情
| 参数名 | 类型 | 说明  |
|------|--|---|
| sender | &signer | 交易签名者 |
| markets | vector\<String\> | NFT 挂单是市场列表，当前有三个可选值 （"Souffl3" / "BlueMove" / "Topaz") |
| listers | vector\<address\> | NFT 挂单者列表 |
| prices | vector\<u64\> | NFT 挂单价格列表 |
| amounts | vector\<u64\> | NFT token amount 列表 |
| creators | vector\<address\> | NFT creator 列表 |
| collections | vector\<String\> | NFT collection name 列表 |
| names | vector\<String\> | NFT token name 列表 |
| property_versions | vector\<u64\> | NFT property version 列表 |
| market_address_list | vector\<address\> | NFT market address 列表，如果对应挂单市场为 "Souffl3", 数组压入一个 {{souffl3_contract_address}} 即可，其他市场无需任何处理 |
| market_name_list | vector\<String\> | NFT market name 列表，如果对应挂单市场为 "Souffl3", 数组压入 "souffle" 即可，其他市场无需处理 |

### 批量购买 batch buy transaction 示例

https://explorer.aptoslabs.com/txn/55050185


### 批量购买 batch buy payload 示例

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

## 批量取消挂单 delist

| 函数id | 入参泛型 | 入参  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_delist_script_V1 | 无 | sender: &signer<br>markets: vector\<String\><br>amounts: vector\<u64\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_lists: vector\<String\>  |


#### 入参详情
| 参数名 | 类型 | 说明  |
|------|--|---|
| sender | &signer | 交易签名者 |
| markets | vector\<String\> | NFT 挂单是市场列表，当前有三个可选值 （"Souffl3" / "BlueMove" / "Topaz") |
| amounts | vector\<u64\> | NFT token amount 列表 |
| creators | vector\<address\> | NFT creator 列表 |
| collections | vector\<String\> | NFT collection name 列表 |
| names | vector\<String\> | NFT token name 列表 |
| property_versions | vector\<u64\> | NFT property version 列表 |
| market_address_list | vector\<address\> | NFT market address 列表，如果对应挂单市场为 "Souffl3", 数组压入一个 {{souffl3_contract_address}} 即可，其他市场无需任何处理 |
| market_name_list | vector\<String\> | NFT market name 列表，如果对应挂单市场为 "Souffl3", 数组压入 "souffle" 即可，其他市场无需处理 |

### 批量取消挂单 batch delist transaction 示例

https://explorer.aptoslabs.com/txn/55014220

### 批量取消挂单 batch delist payload 示例

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

## 批量修改价格 batch_change_price


| 函数id | 入参泛型 | 入参  |
|------|--|---|
| {{souffl3_contract_address}}::Aggregator::batch_change_price_script_V1 | 无 | sender: &signer<br>markets: vector\<String\><br>creators: vector\<address\><br>collections: vector\<String\><br>names: vector\<String\><br>property_versions: vector\<u64\><br>amounts: vector\<u64\><br>prices: vector\<u64\><br>locked_until_secs_list: vector\<u64\><br>market_address_lists: vector\<address\><br>market_name_list: vector\<String\>  |

#### 入参详情
| 参数名 | 类型 | 说明  |
|------|--|---|
| sender | &signer | 交易签名者 |
| markets | vector\<String\> | NFT 挂单市场列表，当前有三个可选值 （"Souffl3" / "BlueMove" / "Topaz") |
| creators | vector\<address\> | NFT creator 列表 |
| collections | vector\<String\> | NFT collection name 列表 |
| names | vector\<String\> | NFT token name 列表 |
| property_versions | vector\<u64\> | NFT property version 列表 |
| amounts | vector\<u64\> | NFT token amount 列表 |
| prices | vector\<u64\> | NFT 挂单修改价格列表 |
| locked_until_secs_list | vector\<u64\> | NFT 挂单结束时间（0 为无结束时间挂单，市场上挂单基本都是 0） |
| market_address_list | vector\<address\> | NFT market address 列表，如果对应挂单市场为 "Souffl3", 数组压入一个 {{souffl3_contract_address}} 即可，其他市场无需任何处理 |
| market_name_list | vector\<String\> | NFT market name 列表，如果对应挂单市场为 "Souffl3", 数组压入 "souffle" 即可，其他市场无需处理 |


### 批量修改价格 batch change price transaction 示例 

https://explorer.aptoslabs.com/txn/55091778

### 批量修改价格 batch change price payload 示例

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
