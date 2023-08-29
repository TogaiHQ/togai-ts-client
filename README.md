# Togai Client

![npm](https://img.shields.io/npm/v/togai-client)

[Togai](https://www.togai.com/) is an end to end pricing infrastructure that enable you with metering, aggregating, pricing and billing for your application.

This is an official Typescript client library for using [Togai APIs](https://docs.togai.com/reference).

## Installation

To install the library, run:
```bash
npm install togai-client
```

## Usage

To get started with the library, you need to create a api token from your Togai Account

```typescript
import { Configuration, CustomersApi, CreateCustomerRequest } from 'togai-client';

const API_TOKEN = "YOUR_API_TOKEN";
const BASE_PATH = "https://sandbox-api.togai.com"

const configuration = new Configuration({
    basePath: BASE_PATH,
    accessToken: API_TOKEN,
});
const createCustomerRequest:CreateCustomerRequest = {
    name: "customer1",
    id: "1",
    address: {line1: "house 221B", line2: "Baker Street", city: "London", state: "London", country: "GB"},
    primaryEmail: "email@togai.com"
} 
const customersApi = new CustomersApi(configuration);
const customer = (await customersApi.createCustomer(createCustomerRequest)).data;
console.log("Customer created", customer);
```

You can get a detailed step-by-step guide for a sample ingestion and metering at [examples](examples).
