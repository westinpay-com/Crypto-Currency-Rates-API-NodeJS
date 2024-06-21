# Crypto-Currency-Rates-API-NodeJS
WestinPay's Free Crypto API provides real-time cryptocurrency exchange rates and conversions. It's perfect for financial apps, e-commerce platforms, and travel services that integrate cryptocurrency transactions.

WestinPay's Free Crypto Currency API provides real-time exchange rates and currency conversion for all cryptocurrencies. It's ideal for financial apps, e-commerce platforms, and travel services.

## Endpoint

The WestinPay Crypto Currency Endpoint delivers real-time exchange rates.

### Authentication

Once you have created an account on [WestinPay](https://westinpay.com/merchant/register), your account will be assigned a unique 32-character API key. Think of this like a secure password; keep it safe and do not share it with others.

### Getting Your API Key

After registering, go to the dashboard and navigate to the "Currency Key" section. Here, you can generate your Fiat API key. This key is essential for authenticating your requests to the API.

### Parameters

- **base**: The base currency for conversion. Default is BTC. // For other currencies, use the currency symbol e.g. base=USDT
- **output**: Response format, either JSON or XML. Default is JSON.
- **api_key**: Your unique API key. Replace YOUR-API-KEY with your actual API key.

### Usage Limitations

Please note that your API key allows for up to 5000 monthly requests. This limit is automatically renewed each month. It's important to manage your usage to ensure continuous access to the API.


## WestinPay Crypto Currency NodeJS Code

```nodejs
const https = require('https');

const api_key = 'your_api_key';
const base = 'BTC';
const output = 'JSON';
const url = `https://westinpay.com/currency/crypto_api?api_key=${api_key}&base=${base}&output=${output}`;

https.get(url, (resp) => {
  let data = '';

  resp.on('data', (chunk) => {
    data += chunk;
  });

  resp.on('end', () => {
    console.log(JSON.parse(data));
  });

}).on("error", (err) => {
  console.log("Error: " + err.message);
});
