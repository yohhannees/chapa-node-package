Thank you for the update! Here's the revised `README.md` with the correct package name `chapa-sdk`:

```markdown
# Chapa SDK

The Chapa SDK is a simple and customizable payment gateway solution that can be easily integrated into your application. It allows you to handle payment processing seamlessly.

## Installation

To install the package, use the following npm command:

```bash
npm install chapa-sdk
```

## Usage

Once installed, you can start using the Chapa SDK in your project.

### Example

```javascript
const ChapaSDK = require('chapa-sdk');

// Initialize the payment gateway
const payment = new ChapaSDK({
  apiKey: 'your-api-key',
  secretKey: 'your-secret-key',
});

// Example of creating a payment
payment.createPayment({
  amount: 100, // Amount in the smallest currency unit (e.g., cents)
  currency: 'USD',
  paymentMethod: 'credit_card',
  customerDetails: {
    name: 'John Doe',
    email: 'john@example.com',
  },
})
  .then(response => {
    console.log('Payment created successfully:', response);
  })
  .catch(error => {
    console.error('Error creating payment:', error);
  });
```

### Methods

#### `createPayment(paymentData)`
Creates a new payment request.

- **Parameters**:
  - `paymentData`: An object containing the following properties:
    - `amount`: The payment amount (in the smallest unit of the currency, e.g., cents).
    - `currency`: The currency for the payment (e.g., `USD`).
    - `paymentMethod`: The payment method (e.g., `credit_card`, `paypal`).
    - `customerDetails`: An object containing the customer’s details (e.g., name, email).

- **Returns**: A promise that resolves to the payment response.

#### `getPaymentStatus(paymentId)`
Fetches the status of an existing payment.

- **Parameters**:
  - `paymentId`: The ID of the payment whose status you want to check.

- **Returns**: A promise that resolves to the payment status.

#### `refundPayment(paymentId, amount)`
Refunds a payment.

- **Parameters**:
  - `paymentId`: The ID of the payment to refund.
  - `amount`: The amount to refund (in the smallest unit of the currency).

- **Returns**: A promise that resolves to the refund status.

## Configuration

You can configure the package by passing an object to the constructor. The configuration object can include the following properties:

- `apiKey`: Your API key to authenticate with the payment gateway (required).
- `secretKey`: Your secret key for security (required).
- `baseUrl`: The base URL of the payment gateway's API (optional, default is `https://api.chapa.com`).

Example:

```javascript
const payment = new ChapaSDK({
  apiKey: 'your-api-key',
  secretKey: 'your-secret-key',
  baseUrl: 'https://custom-api.chapa.com',
});
```

## Testing

You can test the payment gateway by using the `test` mode. This allows you to simulate payments without actually processing real transactions.

Example:

```javascript
const payment = new ChapaSDK({
  apiKey: 'your-api-key',
  secretKey: 'your-secret-key',
  testMode: true,
});
```

## License

This package is licensed under the [MIT License](LICENSE).
```

### Key Updates:
- **Package name** updated to `chapa-sdk`.
- Placeholder `your-api-key` and `your-secret-key` are included for configuration.
- Methods and usage are based on a standard payment gateway structure. Update these methods as needed based on your implementation.

Let me know if you'd like further modifications!
