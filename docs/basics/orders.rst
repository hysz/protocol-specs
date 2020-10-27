###############################
Orders
###############################

There are three types of orders in 0x V4: Limit, RFQ and DEX. Limit orders are 

Limit Order
-----------

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


+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| Field        | Type    | Description                                                                                                                           |
+==============+=========+=======================================================================================================================================+
| makerToken   | address | The ERC20 token the maker is selling and the maker is selling / taker is buying.                                                      |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| takerToken   | address | The ERC20 token the taker is selling and the taker is selling / maker is buying.                                                      |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| makerAmount  | uint128 | The amount of makerToken being sold by the maker.                                                                                     |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| takerAmount  | uint128 | The amount of takerToken being sold by the taker.                                                                                     |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| feeRecipient | address | Recipient of maker token or taker token fees (if non-zero).                                                                           |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| feeAmount    | uint128 | Amount of takerToken paid by the taker to the feeRecipient.                                                                           |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| taker        | address | Taker address. Set to zero to allow any taker.                                                                                        |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| sender       | address | The address that calls the Exchange (``msg.sender``)                                                                                  |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| pool         | uint256 | The staking pool to attribute the 0x protocol fee from this order. Set to zero to attribute to the default pool, not owned by anyone. |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| expiry       | uint64  | The Unix Timestamp in seconds when this order expires.                                                                                |
+--------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
| salt         | bytes32 | Arbitrary number to facilitate uniqueness of the order's hash.                                                                        |



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