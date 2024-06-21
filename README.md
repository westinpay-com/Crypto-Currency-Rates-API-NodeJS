# Crypto-Currency-Rates-API-NodeJS
WestinPay's Free Crypto API provides real-time cryptocurrency exchange rates and conversions. It's perfect for financial apps, e-commerce platforms, and travel services that integrate cryptocurrency transactions.
# Free Crypto Currency Conversion API

WestinPay’s free API provides access to cryptocurrency exchange rates, ensuring your crypto conversions are quick, accurate, and backed by reliable, up-to-date data.


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
