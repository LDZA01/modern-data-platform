# Source data outline

## Status

This is the source brief for later phases, not a database schema or an implemented Gold model. No source files or tables exist in Phase 0. Types, nullability, key validation, relationships, and timestamp conventions will be agreed before generating and loading data.

## Initial entities

| Entity | Intended source-row meaning | Requested fields |
| --- | --- | --- |
| `customers` | A customer record. | `customer_id`, `name`, `email`, `country`, `signup_date` |
| `products` | A product record. | `product_id`, `product_name`, `category`, `price` |
| `orders` | An order record. | `order_id`, `customer_id`, `order_timestamp`, `order_status`, `total_amount` |
| `order_items` | A line within an order; unique line identity needs discussion. | `order_id`, `product_id`, `quantity`, `unit_price` |
| `payments` | A payment record associated with an order. | `payment_id`, `order_id`, `payment_method`, `payment_status`, `payment_timestamp`, `amount` |

These describe expected business records. Later raw files may repeat records or contain malformed fields, so this outline is not a guarantee of raw uniqueness or validity.

## Relationships to investigate

A customer can place orders. An order can contain multiple items, and each item references a product. A payment references an order. We will decide whether multiple payment attempts, partial payments, cancellations, and refunds belong in the initial scenario before encoding validation rules.

## Questions for the relevant phases

- Could the same product appear on two separate lines of one order? If so, do `order_id` and `product_id` identify a line uniquely?
- Does a product's current price equal the historical price paid on an order line?
- Which timestamp format and timezone will the source use, and how will a source timezone be known?
- What currency do amounts represent, and what precision is required?
- What identifies an updated record rather than a duplicate arrival?
- Which order and payment statuses contribute to each business metric?

These are design exercises to attempt together, not assumptions already enforced by code.

## Future Gold modeling

Potential model names from the brief include `fact_sales`, `fact_orders`, `dim_customer`, `dim_product`, and `dim_date`. They remain candidates. In Phase 5, we will learn facts, dimensions, business keys, surrogate keys, star schemas, and Slowly Changing Dimensions before designing them.

Before creating every table, write a sentence beginning **"One row represents..."**, then define its keys, relationships, and business meaning. That sentence establishes its grain and helps prevent double-counting.
