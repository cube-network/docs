# Metamask Lagging 

Slow response when inputting tansfer amount, fetching gasprice, etc. It is a chrome's known issue according to the following issue：

https://github.com/MetaMask/metamask-extension/issues/10202

Workarounds are:

1）Use expand view

![](../images/metamask_lag.jpg)

2）Move to primary monitor is using multiple monitors

3）Use other explorers

# transaction pending for a long time

## 1）Inappropriate nonce:
Suggestions:

- Try to reset a appropriate value
- If you have many pending transactions , please wait for earier transactions confirmed.
- metatask--setting-advanced--reset account
- metatask--setting--advanced--Customize transaction nonce :resend transaction with pending tx's nonce and higher gas price.

## 2) low gas price：
- Set a higher gas price and resend

