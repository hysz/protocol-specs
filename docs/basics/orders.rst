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
        address feeRecipient;
        uint128 feeAmount;
        address taker;
        address sender;
        uint256 pool;
        uint64 expiry;
        bytes32 salt;
    }

+--------------+---------+-------------+
| Field        | Type    | Description |
+==============+=========+=============+
| makerToken   | address | column 3    |
+--------------+---------+-------------+
| takeToken    | address | column 3    |
+--------------+---------+-------------+
| makerAmount  | uint128 | column 3    |
+--------------+---------+-------------+
| takerAmount  | uint128 | column 3    |
+--------------+---------+-------------+
| feeRecipient | address | column 3    |
+--------------+---------+-------------+
| feeAmount    | uint128 | column 3    |
+--------------+---------+-------------+
| taker        | address | column 3    |
+--------------+---------+-------------+
| sender       | address | column 3    |
+--------------+---------+-------------+
| pool         | uint256 |             |
+--------------+---------+-------------+
| expiry       | uint64  |             |
+--------------+---------+-------------+
| salt         | bytes32 |             |
+--------------+---------+-------------+

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