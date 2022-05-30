# beliikan
Tugas Mata Kuliah Pengembangan Aplikasi Berbasis Web

# Module
1. Authentication ✅
2. Product ✅
3. Category ✅
4. History
5. Transaction ✅
6. Detail Transaction ✅
7. Shipping
8. Payments

# Authentication
## Register
Request :
  - Method : POST
  - Endpoint : `api/register`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :
 
  ```json 
{
    "name" : "string",
    "phone" : "string",
    "address" : "string",
    "email" : "string",
    "password" : "string"
}
```
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : 
      "user": {
          "email": "string",
          "userable_type": "string",
          "userable_id": "integer",
          "updated_at": "string",
          "created_at": "string",
          "id": "integer"
      }
}
```

## Login
Request :
  - Method : POST
  - Endpoint : `api/login`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :
 
  ```json 
{
    "email" : "string",
    "password" : "string"
}
```
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
      "access_token": "string",
      "token_type": "string",
      "user": {
          "id_seller": "integer",
          "name": "string",
          "phone": "string",
          "email": "string",
          "address": "string",
          "user_type": "string"
      }
}
```
## Logout
Request :
  - Method : POST
  - Endpoint : `api/login`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      - Authorization : json web token
      
  - Body :
 
  ```json 
{
    "token" : "string"
}
```
Response :

```json 
{
    "code" : "number",
    "status" : {
      "success": true,
      "message": "User has been logged out"
    }
    "data" : null
}
```

# Product
## Create Product
Request :
  - Method : POST
  - Endpoint : `/api/product`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      - Authorization : json web token
      
  - Body :
 
  ```json 
{
    "name" : "string",
    "price" : "long",
    "description" : "text"
    "stock" : "integer"
    "img_url" : "string"
}
```
Respons :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "name" : "string",
         "price" : "long",
         "description" : "text"
         "stock" : "integer"
         "img_url" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## Get Product
Request :
  - Method : GET
  - Endpoint : `/api/product/{id}`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :
  
Respons :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "name" : "string",
         "price" : "long",
         "description" : "text"
         "stock" : "integer"
         "img_url" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## Update Product
Request :
  - Method : PUT
  - Endpoint : `/api/product/{id}`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :

  ```json 
{
    "name" : "string",
    "price" : "long",
    "description" : "text"
    "stock" : "integer"
    "img_url" : "string"
}
```

Respons :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "name" : "string",
         "price" : "long",
         "description" : "text"
         "stock" : "integer"
         "img_url" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```

## list Product
Request :
  - Method : GET
  - Endpoint : `/api/products`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :

  ```json 
{
    "name" : "string",
    "price" : "long",
    "description" : "text"
    "stock" : "integer"
    "img_url" : "string"
}
```

Respons :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : [
      {
         "name" : "string",
         "price" : "long",
         "description" : "text"
         "stock" : "integer"
         "img_url" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     },
     {
         "name" : "string",
         "price" : "long",
         "description" : "text"
         "stock" : "integer"
         "img_url" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
     ]
}
```

## Delete Product

Request :
- Method : DELETE
- Endpoint : `/api/products/{id}`
- Header :
    - Accept: application/json

Response :

```json 
{
    "code" : "number",
    "status" : "string"
}
```
# transactions
## create transactions
Request :
  - Method : POST
  - Endpoint : `/api/transactions`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :
 
  ```json 
{
    "invoice_number" : "string",
    "user_id" : "integer",
    "name" : "string",
    "address" : "string",
    "email" : "string",
    "no_telp" : "string",
    "payment_gateway" : "string",
    "shipping" : "integer",
    "total_price" : "string",
    "status" : "string",
}
```
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "invoice_number" : "string",
         "user_id" : "integer",
         "name" : "string",
         "address" : "string",
         "email" : "string",
         "no_telp" : "string",
         "payment_gateway" : "string",
         "shipping" : "integer",
         "total_price" : "string",
         "status" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## Get transactions
Request :
  - Method : GET
  - Endpoint : `/api/transactions/{id}`
  - Header : 
      - Accept: application/json
      
  - Body :
  
Response :
```json 
{
   "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "invoice_number" : "string",
         "user_id" : "integer",
         "name" : "string",
         "address" : "string",
         "email" : "string",
         "no_telp" : "string",
         "payment_gateway" : "string",
         "shipping" : "integer",
         "total_price" : "string",
         "status" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## Update transactions
Request :
  - Method : PUT
  - Endpoint : `/api/transactions/{id}`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :

  ```json 
{
    "invoice_number" : "string",
    "user_id" : "integer",
    "name" : "string",
    "address" : "string",
    "email" : "string",
    "no_telp" : "string",
    "payment_gateway" : "string",
    "shipping" : "integer",
    "total_price" : "string",
    "status" : "string",
```

Response :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "invoice_number" : "string",
         "user_id" : "integer",
         "name" : "string",
         "address" : "string",
         "email" : "string",
         "no_telp" : "string",
         "payment_gateway" : "string",
         "shipping" : "integer",
         "total_price" : "string",
         "status" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## List transactions
Request :
  - Method : GET
  - Endpoint : `/api/transactions`
  - Header : 
      - Accept: application/json
      
  - Body :

Respons :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : [
      {
         "id" : "integer",
         "invoice_number" : "string",
         "user_id" : "integer",
         "name" : "string",
         "address" : "string",
         "email" : "string",
         "no_telp" : "string",
         "payment_gateway" : "string",
         "shipping" : "integer",
         "total_price" : "string",
         "status" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     },
     {
         "id" : "integer",
         "invoice_number" : "string",
         "user_id" : "integer",
         "name" : "string",
         "address" : "string",
         "email" : "string",
         "no_telp" : "string",
         "payment_gateway" : "string",
         "shipping" : "integer",
         "total_price" : "string",
         "status" : "string",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
     ]
}
```
## Delete transactions

Request :
- Method : DELETE
- Endpoint : `/api/transactions/{id}`
- Header :
    - Accept: application/json

Response :

```json 
{
    "code" : "number",
    "status" : "string"
}
```

# detail transactions
## Create detail transactions
Request :
  - Method : POST
  - Endpoint : `/api/detail_transactions`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :
 
  ```json 
{
    "user_id" : "integer",
    "product_id" : "integer",
    "name" : "string",
    "category" : "string",
    "transaction_id" : "integer",
    "qty" : "integer",
}
```
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "user_id" : "integer",
         "product_id" : "integer",
         "name" : "string",
         "category" : "string",
         "transaction_id" : "integer",
         "qty" : "integer"
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```

## Get detail_transactions
Request :
  - Method : GET
  - Endpoint : `/api/detail_transactions/{id}`
  - Header : 
      - Accept: application/json
      
  - Body :
  
Response :
```json 
{
   "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "user_id" : "integer",
         "product_id" : "integer",
         "name" : "string",
         "category" : "string",
         "transaction_id" : "integer",
         "qty" : "integer",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```
## Update detail_transactions
Request :
  - Method : PUT
  - Endpoint : `/api/detail_transactions/{id}`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
  - Body :

  ```json 
{
    "user_id" : "integer",
    "product_id" : "integer",
    "name" : "string",
    "category" : "string",
    "transaction_id" : "integer",
    "qty" : "integer",
```

Response :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
         "id" : "integer",
         "user_id" : "integer",
         "product_id" : "integer",
         "name" : "string",
         "category" : "string",
         "transaction_id" : "integer",
         "qty" : "integer",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
}
```

## List detail_transactions
Request :
  - Method : GET
  - Endpoint : `/api/detail_transactions`
  - Header : 
      - Accept: application/json
      
  - Body :

Respons :
```json 
{
    "code" : "number",
    "status" : "string",
    "data" : [
      {
         "id" : "integer",
         "user_id" : "integer",
         "product_id" : "integer",
         "name" : "string",
         "category" : "string",
         "transaction_id" : "integer",
         "qty" : "integer",
         "createdAt" : "date",
         "updatedAt" : "date"
     },
     {
         "id" : "integer",
         "user_id" : "integer",
         "product_id" : "integer",
         "name" : "string",
         "category" : "string",
         "transaction_id" : "integer",
         "qty" : "integer",
         "createdAt" : "date",
         "updatedAt" : "date"
     }
     ]
}
```
## Delete detail_transactions

Request :
- Method : DELETE
- Endpoint : `/api/detail_transactions/{id}`
- Header :
    - Accept: application/json

Response :

```json 
{
    "code" : "number",
    "status" : "string"
}
```
# Category
## create category

Request :
  - Method : POST
  - Endpoint : `/api/category`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      - Authorization : json web token
      
  - Body :
 
  ```json 
{
    "name" : "string"
}
```
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : {
      "name": "string",
      "updated_at": "string",
      "created_at": "string",
      "id": "integer"
    }
}
```

## list category

Request :
  - Method : get
  - Endpoint : `/api/category`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : [
      {
        "name": "string",
        "updated_at": "string",
        "created_at": "string",
        "id": "integer"
      }
    ]
}
```

## delete category

Request :
  - Method : DELETE
  - Endpoint : `/api/category/{id}`
  - Header : 
      - Content-Type: application/json
      - Accept: application/json
      - Authorization
      
Response :

```json 
{
    "code" : "number",
    "status" : "string",
    "data" : []
}
```
