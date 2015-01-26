# bitcoin-exchange-smart-order-router

2015 C. Papathanasiou

A smart order router for selling bitcoin at the exchange with the best price for amount being sold.

Precisely replicates orderbooks at Bitstamp, Bitfinex, Kraken and models impact to price of  Market sell order taking into account withdraw fees and comission (correct as of 26 Jan 2015).

Output is exchange which would 'win' i.e, give you highest payout for amount of btc being sold.

Exercise left to reader to use bitcoinrpc send etc to send btc to that exchange and implement hedging.

Things to consider:
3 confirmations will likely mean that by the time your btc arrive on the winning exchange, the order book will be different. You need to either hedge your position while btc are in transit or have btc ready on the other end that you can then do the accounting for.

Depends on:
<pre>
https://github.com/unwitting/bitstampy
https://github.com/scottjbarr/bitfinex
https://github.com/veox/python2-krakenex
</pre>

```
Christian-Papathanasious-iMac:/ chris$ ./smartrouter.py 50
** BITSTAMP ** our bankroll is: $15079.65
** BITSTAMP ** total fees are: $75.40
** BITSTAMP ** take home is: $15003.35
** kraken ** our bankroll is: $10924.77
** kraken ** total fees are: $54.62
** kraken ** take home is: $10869.25
** bitfinex ** our bankroll is: $15131.74
** bitfinex ** total fees are: $75.60
** bitfinex ** take home is: $15055.24
Bitfinex wins: 15055.24
Christian-Papathanasious-iMac:/ chris$
```

