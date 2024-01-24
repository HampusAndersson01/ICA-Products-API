# ICA Products API Documentation

## Overview

The ICA Products API provides access to information about various products available in ICA stores. The API allows you to retrieve details such as product name, price, availability, images, and offers.

## Base URL

`https://handlaprivatkund.ica.se/stores/{storeId}`

**Note:** The **{storeId}** parameter is the store ID of the ICA store you want to retrieve products from. You can find the store ID in the URL of the store's website. For example, the store ID for the ICA Kvantum store in Kungens Kurva is `1004394`.

### Authentication

No authentication is required to use the API.

## Table of Contents

- [Products](#products)
  - [`GET` /api/v5/products](#get-apiv5products)
  - [`GET` /api/v5/products/search](#get-apiv5productssearch)
  - [Product Details](#product-details)

# Endpoints

## Products

### `GET` api/v5/products

#### Parameters

- `limit` (optional): The number of products to retrieve per request. Default is `50`.
- `offset` (optional): The offset for paginating through the product list. Default is `0`.

```bash
curl -X GET "https://handlaprivatkund.ica.se/{storeId}/api/v5/products?limit=50&offset=0"
```

```json
{
  "entities": {
    "product": {
      "20b74fbf-9ea9-41d5-9572-1e389aa0ca29": {
        "productId": "20b74fbf-9ea9-41d5-9572-1e389aa0ca29",
        "retailerProductId": "1023753",
        "name": "Lingongrova 500g Pågen",
        "available": true,
        "maxQuantityReached": false,
        "imagePaths": [
          "https://handlaprivatkund.ica.se/images-v3/bf7a00ca-390e-4769-865f-dc369586872e/8ec8d787-5e2c-4037-8e1c-8bdd921bf869"
        ],
        "price": {
          "current": {
            "amount": "24.90",
            "currency": "SEK"
          },
          "unit": {
            "label": "fop.price.per.kg",
            "current": {
              "amount": "49.80",
              "currency": "SEK"
            }
          }
        }
        // ... (more product details)
      }
      // ... (more products)
    }
  }
}
```

### `GET` api/v5/products/search

#### Parameters

- `limit` (optional): The number of products to retrieve per request. Default is `50`.
- `offset` (optional): The offset for paginating through the search result list. Default is `0`.
- `term` (required): The search term to find products.

```bash
curl -X GET "https://handlaprivatkund.ica.se/{storeId}/api/v5/products/search?limit=50&offset=0&term=ost"
```

```json
{
  "entities": {
    "product": {
      "3368fadc-9c30-4e70-9c62-005b0b671589": {
        "productId": "3368fadc-9c30-4e70-9c62-005b0b671589",
        "retailerProductId": "2022192",
        "name": "Ost Herrgård 28% Skivad 700g ICA",
        "available": true,
        "maxQuantityReached": false,
        "imagePaths": [
          "https://handlaprivatkund.ica.se/images-v3/bf7a00ca-390e-4769-865f-dc369586872e/027e7e09-ad08-4b27-a070-46943f4a1da6"
        ],
        "alternatives": [],
        "price": {
          "current": {
            "amount": "76.90",
            "currency": "SEK"
          },
          "unit": {
            "label": "fop.price.per.kg",
            "current": {
              "amount": "109.86",
              "currency": "SEK"
            }
          }
        }
        // ... (more product details)
      }
      // ... (more products)
    }
  }
}
```

### Product Details

The product details include various attributes such as:

- `productId`: Unique identifier for the product.
- `name`: The name of the product.
- `available`: Indicates whether the product is currently available.
- `price`: The current price of the product.
- `imagePaths`: URLs to images of the product.
- `offers`: Details about any special offers associated with the product.
