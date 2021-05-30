# Federated Crypto Payment Address API

This project exists as a way for people to look up crypto payment
addresses using an email-style address.

The idea is to give domain administrators the ability to provide a service to their users that allows their users to register in a crypto wallet address, and for the domain to provide an email-style address which the user can give to people who would pay them via crypto.

## Who Does What

* Users can provide one or more crypto payment addresses to a domain provider, one for each crypto the user has an address for.
* The domain provider gives the user a username that resembles an email address. If the domain provides email addresses, it can even make the user's username the same as their email for convenience. This acts as an easy-to-remember, domain-provided payment address.
* The user can give that domain-provided email address to friends and family who wish to pay them.

## How to View this API

You can view this API specification in a user-friendly interface on [Restaway](https://backupbrain.github.io/restaway/?q=https://raw.githubusercontent.com/backupbrain/federated-crypto-address-api/main/federated-crypto-address-api.yaml)

## Audience

This project is intended for:

* Crypto wallet producers
* Crypto exchange operators
* Internet domain maintainers

## Use-Case

The use case for this is as follows:

Coinbase and Yahoo both support the Federated Crypto Payment Address Protocol (FCPAP).

Becky wants to pay ETH to Allison. Allison has an email account at Yahoo, which in this example connects her email address to the FCPAP. Allison's username at Yahoo is "allison" and her email address is "allison@yahoo.com." 

Yahoo has decided that the FCPAP addresses will look like "pay-username@yahoo.com". They could have made the FCPAP exactly the same as the user's email but then the readers of this example might confuse email and payment addresses.

Instead of giving Becky a long-form ETH address, she says, "you can pay me ETH at pay-allison@yahoo.com"

Becky uses Coinbase as a crypto exchange, and has ETH in one of her wallets. Since Coinbase (in this example) supports FCPAP, she can type in "pay-allison@yahoo.com" into the recipient's field of her send form. When she does this and selects that she is sending ETH, Coinbase sends a REST API call to Yahoo asking for an ETH address for the user "pay-allison"

Yahoo responds with an ETH address, which is Becky's Coinbase stores as the destination address for Becky's payment.

In this way, Becky can pay Allison by paying ETH to "pay-allison@yahoo.com" without ever having to type in an ETH address or scan a QR code. Allison doesn't even have to remember the address when she tells Becky to pay her.
