# E*TRADE API - OpenAPI v3 Specification

This repository contains a comprehensive OpenAPI v3 specification for the E*TRADE API, which provides programmatic access to account data, market information, order management, and alerts for E*TRADE customers.

## Overview

The E*TRADE API allows developers to:
- Access account balances, portfolios, and transaction history
- Retrieve real-time market quotes and option chains
- Preview, place, modify, and cancel orders
- Manage user alerts and notifications
- Authenticate using OAuth 1.0a

## Files

- **openapi.yaml** - Complete OpenAPI v3 specification for the E*TRADE API

## API Coverage

The OpenAPI specification covers the following API modules:

### Authorization
- OAuth 1.0a authentication flow
- Request token, access token, renewal, and revocation endpoints

### Account Management
- List all accounts
- Get account balance
- Retrieve portfolio positions
- Access transaction history

### Market Data
- Get real-time quotes for stocks, options, ETFs, and mutual funds
- Retrieve option chains with Greeks
- Get option expiration dates
- Search for securities by symbol or company name

### Order Management
- Preview orders before placement
- Place buy, sell, and option orders
- List orders with filtering
- Get order details
- Modify existing orders
- Cancel orders

### Alerts
- List user alerts
- Get alert details
- Delete alerts

## Environments

The API supports two environments:

- **Sandbox**: `https://apisb.etrade.com` - For testing and development
- **Production**: `https://api.etrade.com` - For live trading

## Authentication

All API endpoints require OAuth 1.0a authentication. You must:

1. Register for a developer account at [E*TRADE Developer Portal](https://developer.etrade.com)
2. Obtain consumer keys (separate keys for sandbox and production)
3. Follow the OAuth 1.0a workflow to obtain access tokens
4. Include OAuth credentials in all API requests

## Using the OpenAPI Specification

### View Documentation

You can view the API documentation using various OpenAPI tools:

#### Using Swagger UI (Online)
Visit [Swagger Editor](https://editor.swagger.io/) and paste the contents of `openapi.yaml`

#### Using Redoc (Local)
```bash
npx @redocly/cli preview-docs openapi.yaml
```

#### Using Swagger UI (Docker)
```bash
docker run -p 8080:8080 -e SWAGGER_JSON=/openapi.yaml -v $(pwd)/openapi.yaml:/openapi.yaml swaggerapi/swagger-ui
```

### Generate Client Libraries

You can generate client libraries in various programming languages using the OpenAPI Generator:

```bash
# Install OpenAPI Generator
npm install -g @openapitools/openapi-generator-cli

# Generate Python client
openapi-generator-cli generate -i openapi.yaml -g python -o ./generated/python

# Generate JavaScript/TypeScript client
openapi-generator-cli generate -i openapi.yaml -g typescript-axios -o ./generated/typescript

# Generate Java client
openapi-generator-cli generate -i openapi.yaml -g java -o ./generated/java

# Generate Go client
openapi-generator-cli generate -i openapi.yaml -g go -o ./generated/go
```

### Validate the Specification

```bash
# Using Redocly CLI
npx @redocly/cli lint openapi.yaml

# Using Swagger CLI
npm install -g @apidevtools/swagger-cli
swagger-cli validate openapi.yaml
```

## API Response Formats

The API supports both JSON and XML response formats. By default, responses are in JSON format. You can specify the format using the `Accept` header:

- `Accept: application/json` - JSON format (default)
- `Accept: application/xml` - XML format

## Rate Limits

E*TRADE API has rate limits to ensure fair usage. Check the official [E*TRADE Developer Documentation](https://developer.etrade.com) for current rate limit details.

## Resources

- [E*TRADE Developer Portal](https://developer.etrade.com)
- [E*TRADE API Documentation](https://apisb.etrade.com/docs/api/account/api-account-v1.html)
- [OAuth 1.0a Specification](https://oauth.net/core/1.0a/)
- [OpenAPI Specification](https://swagger.io/specification/)

## Contributing

This OpenAPI specification is based on the official E*TRADE API documentation. If you find any discrepancies or missing endpoints, please open an issue or submit a pull request.

## License

See [LICENSE](LICENSE) file for details.

## Disclaimer

This is an unofficial OpenAPI specification for the E*TRADE API. It is not affiliated with, endorsed by, or sponsored by E*TRADE Securities LLC or E*TRADE Financial Corporation. 

For official API documentation, please visit the [E*TRADE Developer Portal](https://developer.etrade.com).

**Trading involves risk. Use this API specification and any generated code at your own risk.**