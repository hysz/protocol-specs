# Orders

There are three types of orders in 0x V4: Limit, RFQ and DEX. Limit orders are 

### Limit Order Struct

```javascript
struct LimitOrder {
    IERC20 makerToken;
    IERC20 takerToken;
    uint128 makerAmount;
    uint128 takerAmount;
    uint256 pool;
    bytes32 salt;
    uint64 expiry;
    address feeRecipient;
    uint128 feeAmount;
    address taker;
    address sender;
}
```

|                |Type                          |Description                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|

### RFQ Order Struct

```javascript
struct RfqOrder {
    IERC20 makerToken;
    IERC20 takerToken;
    uint128 makerAmount;
    uint128 takerAmount;
    uint256 pool;
    bytes32 salt;
    uint256 expiry;
    address txOrigin;
}
```

### DEX Order Struct

```javascript
struct DexOrder {
    IERC20 makerToken;
    IERC20 takerToken;
    uint128 minMakerAmount;
    uint128 takerAmount;
    address dex;
    bytes data;
}
```