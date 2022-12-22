# Identifier

In APTOS, `collection_id` consists of `creator` and `collection_name`, while `token_id` consists of `creator`, `collection_name`, `token_name` and `property_version`, in order to make this struct a unique string, we bcs the struct to build the identifier.

## Collection ID

take [collection](https://souffl3.com/collection/H1zJuMZBDTB7GJXq9J2BigYR9VLNCypiMMuRmbfJXS7wmipjwzqRh4XadaoNukW) for example

```python
import base58
import six
from aptos_sdk.bcs import *
from aptos_sdk.account import *

# serialize `creator`, `collection_name` in order
ser = Serializer()
ser.struct(AccountAddress.from_hex('0x92a99e9c1f1801e619f9f1b9f5de4a86b70052be8184382e65e11d34cf4e4593'))
ser.str('Sw33t Friends')

# then use base58 to encode the bytes, to build the collection id
print(six.ensure_str(base58.b58encode(ser.output())))

# outputs
# H1zJuMZBDTB7GJXq9J2BigYR9VLNCypiMMuRmbfJXS7wmipjwzqRh4XadaoNukW
```

## Token ID

take [token](https://souffl3.com/nft/jB3vopBesQov2WnTmCPzxRrBZeCstVNif5tq2XmFF799YE3huYfDrQ48mJ5uU7mGTvapXamCRKnZ62PCVsmJQJvvcxPcRDGFpmrX1) for example

```python
import base58
import six
from aptos_sdk.bcs import *
from aptos_sdk.account import *

# serialize `creator`, `collection_name`, `token_name`, `property_version`  in order
ser = Serializer()
ser.struct(AccountAddress.from_hex('0x92a99e9c1f1801e619f9f1b9f5de4a86b70052be8184382e65e11d34cf4e4593'))
ser.str('Sw33t Friends')
ser.str('Sw33t Friends #2029')
ser.u64(1)

# then use base58 to encode the bytes, to build the collection id
print(six.ensure_str(base58.b58encode(ser.output())))

# outputs
# jB3vopBesQov2WnTmCPzxRrBZeCstVNif5tq2XmFF799YE3huYfDrQ48mJ5uU7mGTvapXamCRKnZ62PCVsmJQJvvcxPcRDGFpmrX1
```

It's also easy for us to extract the fields from an identifier, just do base58 decoding and then deserialize the bytes.
