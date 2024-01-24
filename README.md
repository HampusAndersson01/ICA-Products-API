# ICA Products API Documentation _WIP_

Welcome to the ICA Products API documentation! This API provides access to information about various products available in ICA stores. You can retrieve details such as product name, price, availability, images, and offers.

## Getting Started

To use the API, you need to know the store ID of the ICA store you want to retrieve products from. You can find the store ID in the URL of the store's website. For example, the store ID for the ICA Kvantum store in Kungens Kurva is `1004394`.

**Base URL**

The base URL for the API is `https://handlaprivatkund.ica.se/stores/{storeId}`.

**Authentication**

No authentication is required to use the API.

## Support the Developer

If you find these docs helpful, consider buying me a coffee to support further development:

<a href="https://www.buymeacoffee.com/cN8Q57HaKt" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" style="height: 60px !important;width: 217px !important;" ></a>

## API Reference

Explore the API endpoints to retrieve information about products:

- [Get Products](api-reference.md#**get-apiv5products**): Retrieve a list of products from the specified ICA store.
- [Search Products](api-reference.md#**get-apiv5productssearch**): Search for products based on a given term.

For detailed information on request parameters and example usage, refer to the [API Reference](api-reference.md).

## Example Usage

### Get Products

```bash
curl -X GET "https://handlaprivatkund.ica.se/{storeId}/api/v5/products?limit=50&offset=0"
```

### Search Products

```bash
curl -X GET "https://handlaprivatkund.ica.se/{storeId}/api/v5/products/search?limit=50&offset=0&term=ost"
```

## Contributing

Feel free to contribute to the development of this API documentation.
