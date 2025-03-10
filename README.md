# NASPIP: Network-Agnostic Secure Payment Instruction Protocol

## What is NASPIP?

NASPIP (Network-Agnostic Secure Payment Instruction Protocol) is a standard for securely transmitting 
payment instructions regardless of the payment network you want to use.


NASPIP defines the structure of the data to be transmitted, allowing for typical open or closed payment 
flows, static and dynamic QR codes, expiration, etc. 
It even allows you to choose the network and token from various options.


## Motivation

In payment systems, there is a transfer of the information necessary to make the payment from the collector 
to the payer or vice versa.

The different payment methods that exist have developed different solutions to this problem thinking about 
the best experience for users. For example, credit and debit cards have been changing this solution over time, 
facilitating the interaction between the payer and the collector.

For cryptocurrency payments, in particular, this is currently a challenge. The existence of several blockchains
and tokens, and the type of information that the user needs to handle to make a payment, make it complex for 
users who do not have knowledge of blockchain or cryptocurrencies in general.

In particular for cryptocurrency payment systems, we want to build a solution that allows to improve the user 
experience to the level of other traditional payment methods.

## Introduction

As mentioned above, payment systems need to transfer information between the payer and the collector. There are 
some interesting cases that I want to highlight.

- **Lightning Network** </br>
LN invoices are very practical to present in a QR code and can be generated dynamically with an expiration for both open and closed amounts. In turn, the LNURL protocol allows generating static QR codes with a public encoding of a URL that is used to request an LN invoice.
[LNURL](https://github.com/lnurl/luds) is a very simple and easy to implement protocol, the only disadvantage is that there is no validation or verification of the URL.

- **PIX Brazil** </br>
A centralized interoperable solution from the [Central Bank of Brazil (BCB)](https://www.bcb.gov.br/en/financialstability/pix_en). It is a very good solution for payments with the Brazilian banking system.

- **QR Interoperable Argentina** </br>
A centralized interoperable solution from the [Central Bank of Argentina (BCRA)](https://www.bcra.gob.ar/). It uses the [EMV&reg; QR](https://www.emvco.com/) standard and the data validation is carried out by the parties that interact in the payment process.
From my point of view, it has two disadvantages. The first is that the length of the EMV format fields is limited to 99 characters, which does not allow it to be used in other networks. The second disadvantage is the implementation. In addition to compliance with the BCRA regulations and legal conditions of Argentina, it requires interaction with all the companies that are already using the protocol to validate the correct implementation.

For the cryptocurrency payment system, we propose a [protocol](./docs/Implementation.md) that has the following requirements:

- **Easy to implement:** The implementation to generate the information or read it must be totally individual to who wants to use it.
- **Interoperable:** So that the payer and the collector can interact without having the same wallet, exchange or provider.
- **Secure:** The payer must be able to verify/validate that the information was generated by the collector.
- **Agnostic:** It must be able to be used for any network and currency.
- **It must be able to support typical open/closed amount payment flows and dynamic/static payment data.**

