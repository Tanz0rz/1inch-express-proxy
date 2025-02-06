# 1inch Express Proxy

This is a simple Nginx proxy for the 1inch API that can be deployed locally.

# Why use a proxy with the 1inch API?

Non-proxied 1inch API requests from a web browser will always throw a CORS error. This is done to keep 1inch API keys off of frontends where nefarious users can extract them while listening to network calls. By executing 1inch API requests on a separate backend, the API key is no longer living in the same environment as the users.

## Prerequisites

This project requires Node version 20 or higher due to the use of `fetch`

# Setup

1. Install with `npm install`
2. Create a `.env` file in the root directory and add your 
   authorization token:
   ```
   AUTHORIZATION=Bearer replace_with_dev_portal_api_token
   ```
3. Execute the command `node index.js`. The server will start on `http://localhost:3000`.

## Usage
To make a request, use the following structure:
```
http://localhost:3000/?url=https://api.1inch.dev/fusion/orders/v1.0/1/order/active
```
Replace the URL parameter with your desired 1inch API endpoint.
