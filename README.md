[JAVASCRIPT__BADGE]: https://img.shields.io/badge/Javascript-000?style=for-the-badge&logo=javascript
[TYPESCRIPT__BADGE]: https://img.shields.io/badge/typescript-D4FAFF?style=for-the-badge&logo=typescript
[EXPRESS__BADGE]: https://img.shields.io/badge/express-005CFE?style=for-the-badge&logo=express

<h1 align="center" style="font-weight: bold;">🍽️ API Restaurant</h1>

![express][EXPRESS__BADGE]
![typescript][TYPESCRIPT__BADGE]
![javascript][JAVASCRIPT__BADGE]

<p align="center">
 <a href="#started">Getting Started</a> • 
  <a href="#routes">API Endpoints</a> •
  <a href="#tech-stack">Tech Stack</a>
</p>

<p align="center">
  <b>A RESTful API for restaurants to manage products, tables, and customer orders. Built with Node.js and Express.</b>
</p>

<h2 id="started">🚀 Getting started</h2>

Follow the steps below to run the project locally.

<h3>Prerequisites</h3>

Make sure you have the following installed:

- [NodeJS](https://github.com/)
- [Git](https://github.com)

<h3>Cloning</h3>

How to clone your project

```bash
git clone https://github.com/IagoAugust/API-Restaurant.git
```

<h3>Installing dependencies and starting the server</h3>

```bash
cd API-Restaurant
npm install
npm run dev
``````


<h2 id="routes">📍 API Endpoints</h2>

<h3>🛒 Products</h3>

| route               | description                                          
|----------------------|-----------------------------------------------------
| <kbd>GET /products</kbd>     | Retrieve all products. [response details](#get-products-detail)
| <kbd>POST /products</kbd>     | Create a new product. [request details](#post-products-detail)
| <kbd>PUT /products/:id</kbd>     | Update a product by ID. [request details](#put-products-detail)
| <kbd>DELETE /products/:id</kbd>     | Delete a product by ID. [response details](#delete-products-detail)


<h3 id="get-products-detail">GET /products </h3>

**RESPONSE**
```json
{
  "id": 1,
	"name": "Soda Orange",
	"price": 20,
	"created_at": "2025-07-06 00:00:00",
	"updated_at": "2025-07-06 00:00:00"
}
```

<h3 id="post-products-detail">POST /products</h3>

**REQUEST**
```json
{
	"name": "Soda Orange",
	"price": 15.00
}
```

**RESPONSE**
```json
201 Created
```

<h3 id="put-products-detail">PUT /products/:id</h3>

**REQUEST**
```json
{
  "name": "Soda Cola",
  "price": "20.00"
}
```

**RESPONSE**
```json
200 OK
```

<h3 id="delete-products-detail">DELETE /products/:id</h3>

**RESPONSE**
```json
200 OK
```



<h3>🪑 Tables</h3>

| route               | description                                          
|----------------------|-----------------------------------------------------
| <kbd>GET /tables</kbd>     | Retrieve all tables. [response details](#get-tables-detail)

<h3 id="get-tables-detail">GET /products</h3>

**RESPONSE**
```json
{
  "id": 1,
	"table_number": 1,
	"created_at": "2025-07-06 00:00:00",
	"updated_at": "2025-07-06 00:00:00"
}
```

<h3>⏱️ Tables Sessions</h3>

| route               | description                                          
|----------------------|-----------------------------------------------------
| <kbd>GET /tables-sessions</kbd>     | Retrieve all table sessions. [response details](#get-tables-sessions-detail)
| <kbd>POST /tables-sessions</kbd>     | Open a table session. [request details](#post-tables-sessions-detail)
| <kbd>PATCH /tables-sessions/:id</kbd>     | Close a table session. [request details](#patch-tables-sessions-detail)

<h3 id="get-tables-sessions-detail">GET /tables-sessions</h3>

**RESPONSE**
```json
{
  "id": 1,
	"table_id": 1,
	"opened_at": "2025-07-06 00:00:00",
	"closed_at": "null"
}
```

<h3 id="post-tables-sessions-detail">POST /tables-sessions</h3>

**REQUEST**
```json
{
	"table_id": 2
}
```

**RESPONSE**
```json
201 Created
```

<h3 id="patch-tables-sessions-detail">PATCH /tables-sessions/:id</h3>

**RESPONSE**
```json
200 OK
```

<h3>🧾 Orders</h3>

| route               | description                                          
|----------------------|-----------------------------------------------------
| <kbd>GET /orders/table-session/:id</kbd>     | Retrieve all orders from a table session. [response details](#get-orders-detail)
| <kbd>GET /orders/table-session/:id/total</kbd>     | Get the total bill for a table session. [response details](#get-orders-total-detail)
| <kbd>POST /orders</kbd>     | Create a new order. [request details](#post-orders-detail)

<h3 id="get-orders-detail" >GET /orders/table-session/:id</h3>

**RESPONSE**
```json
{
	"id": 2,
	"table_session_id": 2,
	"product_id": 40,
	"name": "Soda Cola",
	"price": 10,
	"quantity": 2,
	"Total": 20,
	"created_at": "2025-07-12 00:00:00",
	"updated_at": "2025-07-12 00:00:00"
}
```

<h3 id="get-orders-total-detail">GET /orders/table-session/:id/total</h3>

**RESPONSE**
```json
{
	"total": 20,
	"quantity": 1
}
```

<h3 id="post-orders-detail">POST /orders</h3>

**REQUEST**
```json
{
	"table_session_id": 2,
	"product_id": 40,
	"quantity": 2
}
```

**RESPONSE**
```json
201 Created
```


<h2 id="tech-stack">Tech Stack</h2>

- Node.js
- Express.js
- TypeScript
- Knex
- Zod
