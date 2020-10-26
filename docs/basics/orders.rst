###############################
Orders
###############################

There are three types of orders in 0x V4: Limit, RFQ and DEX. Limit orders are 

Limit Order
------------------

::
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

=====  =====  ======
Field  Type   Description
=====  =====  ======
makerToken  False  False
True   False  True
False  True   True
True   True   True
=====  =====  ======

RFQ Order
------------------

::
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

DEX Order
------------------

::
    struct DexOrder {
        IERC20 makerToken;
        IERC20 takerToken;
        uint128 minMakerAmount;
        uint128 takerAmount;
        address dex;
        bytes data;
    }