# Rails Engine

The Rails Engine API allows you to query metadata and perform business analytics on merchants, invoices, invoice items, items, customers, and transactions. The return format for all endpoints is JSON.

## Base URL

All URLs referenced in this documentation have the following base:


<a href="http://localhost:3000">http://localhost:3000</a>


## Getting Started
<b><i>This section will help you get started with our API.</i></b>

### Prerequisites

You're going to need:
  * Ruby, version 2.3.1 or newer
  * Bundler

### Getting Set Up

1. Fork this repository on Github.

2. Clone your forked repository (not our original one) to your hard drive with

```
git clone https://github.com/mimilettd/rails_engine
```
3. `cd rails_engine`

4. Run `bundle`

5. Create, migrate, and seed your database:

```
rake db:create
rake db:migrate
rake import
```

6. Run `rspec` to confirm passing tests.

7. Initialize server locally by running `rails s`

## Request URLs

<b><i>Merchant Record Endpoints</i></b>

```
GET /api/v1/merchants.json
GET /api/v1/merchants/1.json
GET /api/v1/merchants/find_all
GET /api/v1/merchants/find?
GET /api/v1/merchants/random.json
```

<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `name`, `created_at`, `updated_at`.

Sample Response for `/api/v1/merchants/find_all?name=Cummings-Thiel`:

```
[{"id":4,"name":"Cummings-Thiel"}]
```

<b><i>Merchant Relationship Endpoints</i></b>

```
GET /api/v1/merchants/:id/items
GET /api/v1/merchants/:id/invoices
```

<b><i>Merchant Business Intelligence Endpoints</i></b>

```
GET /api/v1/merchants/most_revenue?quantity=x
GET /api/v1/merchants/most_items?quantity=x
GET /api/v1/merchants/revenue?date=x
GET /api/v1/merchants/:id/revenue
GET /api/v1/merchants/:id/revenue?date=x
GET /api/v1/merchants/:id/favorite_customer
GET /api/v1/merchants/:id/customers_with_pending_invoices
```

<b><i>Transactions Record Endpoints</i></b>

```
GET /api/v1/transactions.json
GET /api/v1/transactions/1.json
GET /api/v1/transactions/find_all?
GET /api/v1/transactions/find?
GET /api/v1/transactions/random.json
```
<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `invoice_id`, `credit_card_number`, `result`, `created_at`, `updated_at`.

<b><i>Transactions Relationship Endpoints</i></b>

```
GET /api/v1/transactions/:id/invoice
```

<b><i>Customer Record Endpoints</i></b>

```
GET /api/v1/customers.json
GET /api/v1/customers/1.json
GET /api/v1/customers/find_all
GET /api/v1/customers/find?
GET /api/v1/customers/random.json
```

<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `first_name`, `last_name`, `created_at`, `updated_at`.

<b><i>Customer Relationship Endpoints</i></b>

```
GET /api/v1/customers/:id/invoices
GET /api/v1/customers/:id/transactions
```

<b><i>Customer Business Intelligence Endpoints</i></b>

```
GET /api/v1/customers/:id/favorite_merchant
```

<b><i>Invoice Record Endpoints</i></b>

```
GET /api/v1/invoices.json
GET /api/v1/invoices/1.json
GET /api/v1/invoices/find_all
GET /api/v1/invoices/find?
GET /api/v1/invoices/random.json
```

<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `customer_id`, `merchant_id`, `status`, `created_at`, `updated_at`.

<b><i>Invoice Relationship Endpoints</i></b>

```
GET /api/v1/invoices/:id/transactions
GET /api/v1/invoices/:id/invoice_items
GET /api/v1/invoices/:id/items
GET /api/v1/invoices/:id/customer
GET /api/v1/invoices/:id/merchant
```

<b><i>Transaction Record Endpoints</i></b>

```
GET /api/v1/transactions.json
GET /api/v1/transactions/1.json
GET /api/v1/transactions/find_all
GET /api/v1/transactions/find?
GET /api/v1/transactions/random.json
```

<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `invoice_id`, `credit_card_number`, `result`, `created_at`, `updated_at`.

<b><i>Transaction Relationship Endpoints</i></b>

```
GET /api/v1/transactions/:id/invoice
```

<b><i>Transaction Record Endpoints</i></b>

```
GET /api/v1/transactions.json
GET /api/v1/transactions/1.json
GET /api/v1/transactions/find_all
GET /api/v1/transactions/find?
GET /api/v1/transactions/random.json
```

<b><i>Customer Record Endpoints</i></b>

```
GET /api/v1/customers.json
GET /api/v1/customers/1.json
GET /api/v1/customers/find_all
GET /api/v1/customers/find?
GET /api/v1/customers/random.json
```

<b>Note:</b> For `find_all` and `find`, you can use the following search params: `id`, `first_name`, `last_name`, `created_at`, `updated_at`.

<b><i>Customer Relationship Endpoints</i></b>

```
GET /api/v1/customers/:id/invoices
GET /api/v1/customers/:id/transactions
```

<b><i>Customer Business Intelligence Endpoints</i></b>

```
GET /api/v1/customers/:id/favorite_merchant
```

## Additional Information

This is the first paired project of Module 3 at the Turing School. More information on this project can be found <a href="http://backend.turing.io/module3/projects/rails_engine">here</a>.
