# Metamask Lagging 

Slow response when inputting tansfer amount, fetching gasprice, etc. It is a chrome's known issue according to the following issue:

https://github.com/MetaMask/metamask-extension/issues/10202

Workarounds are:

1）Use expand view

![](../images/metamask_lag.jpg)

2）Move to primary monitor if using multiple monitors

3）Use other explorers

# Transaction pending for a long time

## 1）Inappropriate nonce:
Suggestions:

- Try to reset a appropriate value
- If you have many pending transactions, please wait for Earlier Are confirmed.
- metatask--setting-advanced--reset account
- metatask--setting--advanced--Customize transaction nonce: resend transaction with pending tx's nonce and higher gas price.

## 2) Low gas price: 
- Set a higher gas price and resend

