# Pricing Engine

This script adjusts product prices based on inventory and recent sales using a rules-based engine.

## How It Works

1. **Input**:
   - `products.csv`: Contains SKU, name, current price, cost price, and stock.
   - `sales.csv`: Contains SKU and quantity sold in the last 30 days.

2. **Pricing Rules**:
   - **Rule 1**: Low Stock + High Demand → +15% price.
   - **Rule 2**: Dead Stock → -30% price.
   - **Rule 3**: Overstocked Inventory → -10% price.
   - **Rule 4**: Ensure at least 20% margin on cost (always applied).

3. **Output**:
   - `updated_prices.csv`: With columns:
     - `sku`
     - `old_price` (with $ and two decimal places)
     - `new_price` (with $ and two decimal places)

## Example

For SKU A123:
- Old price: $649.99
- New price (after Rule 3 and Rule 4): $600.00

## How to Run

```bash
python pricing_engine.py
