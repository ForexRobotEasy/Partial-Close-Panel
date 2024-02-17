# Partial Close Panel ReadMe File

This ReadMe file provides a brief overview of the code for the Partial Close Panel, developed by the Forex Robot Easy Team. This code is designed to enable partial closing of open orders based on specified percentage levels. Please note that ForexRobotEasy is not the official developer of this product, but we are providing a sample code that can work as described in the product.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy website](https://forexroboteasy.com/forex-robot-review/partial-close-panel-review-forex-software-results-unveiled/). 

## Global Variables

- `PartialCloseLevel1`: Percentage level for partial close 1 (default: 30)
- `PartialCloseLevel2`: Percentage level for partial close 2 (default: 50)
- `PartialCloseLevel3`: Percentage level for partial close 3 (default: 70)

## Expert Functions

### OnInit()

This function is called during expert initialization. You can add any necessary initialization code here.

### OnDeinit(const int reason)

This function is called during expert deinitialization. You can add any necessary deinitialization code here.

### OnTick()

This function is called on every tick. It includes the main logic for the partial close functionality.

- First, it retrieves the current account equity using `AccountInfoDouble(ACCOUNT_EQITY)`.
- Then, it retrieves all open orders using `OrdersTotal()`.
- Next, it loops through each open order and performs the following actions:
  - Retrieves the order ticket using `OrderGetTicket(i)`.
  - Retrieves the order type using `OrderType()`.
  - Retrieves the order profit using `OrderProfit()`.
  - Calculates the profit percentage as `(profit / equity) * 100`.
  - Checks if the order profit is above `PartialCloseLevel1`, `PartialCloseLevel2`, or `PartialCloseLevel3`.
  - If the profit is above any of these levels, it partially closes the order using `OrderClose(ticket, OrderLots(), OrderClosePrice(), 0, CLR_NONE)`.

Please note that this code is a sample and may need to be customized to fit your specific trading requirements.

For more information about the official developer of this product, please visit MQL5.

---

Please note that ForexRobotEasy is not the official developer of this product. We only provide sample code that can work as described in the product. For more information and to find the official developer of this product, please visit MQL5.
