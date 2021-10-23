# Bestside-exchange

Best Side Exchange compares Bitcoin and Ethereum prices from multiple exchanges and gives you the best exchange to buy or sell.

## Demo 👀

#### http://147.182.182.117:3000/

## Screenshot

![Service FLow diagram](/docs/app-screenshot.png)

## Goals

This includes:

- Prices of Bitcoin and Ethereum from two (any) different exchanges/sources.
- Differentiate buy and sell price clearly
- Recommenddations on where to buy and where to sell.

## Requirements

- Python 3.x
- Docker
- make

## Setup

## Server

### Create .env with

```
BITSTAMP_BASE_URL="https://www.bitstamp.net/api/v2"
GEMINI_BASE_URL="https://api.gemini.com/v2"
BLOCKCHAIN_DOT_COM_BASE_URL="https://api.blockchain.com/v3/exchange"
BITFINEX_BASE_URL="https://api-pub.bitfinex.com/v2"
```

#### Start server

```
make server
```

## Web Frontend

#### Start web

```
make web
```

## Alternative Using Docker (Server & Web)

```
Build start
```

#### Development

##### http://127.0.0.1:3000

#### Demo

##### http://147.182.182.117:3000/

## Questionnaire:

### Are there any sub-optimal choices( or short cuts taken due to limited time ) in your implementation?

The implementation is not perfect, for instance some API doesn't display sell Prices because it's not available and also if the exchanges URL grows to hundreds, fetching data from this exchanges in seconds might become nearly impossible thereby increasing the time taken to display market prices.

### Is any part of it over-designed? ( It is fine to over-design to showcase your skills as long as you are clear about it)

I think every design i did was well thought out and neccessary for instance using docker for containerization fostered an easy deployment to digitalocean Virtual machine. The realtime analysis is neccessary because market prices accross these exchanges are constantly changing and it is important to fetch and analyze this data in realtime and display the best side prices for different exchanges.

### If you have to scale your solution to 100 users/second traffic what changes would you make, if any?

- Deploy this application to a kubernetes cluster.
- Improve the realtime analysis algorithm that compares exchanges prices from O(N^2) time complexity to a better time complexity.
- Fetch data differently using threads and handle errors gracefully such that if an exhchange API call fails or hangs, this won't affect other exchanges from fetchinng it's data.

### What are some other enhancements you would have made, if you had more time to do this implementation

- Scalability issues as discussed in the above question.
