# Spinacho: The Ultimate Telegram NFT Bot

### Unlock the Power of NFTs with Spinacho. The Cutting-Edge Telegram Bot for Binance Smart Chain NFT Data and Notifications

___

## Motivation

Spinacho was made with one goal in mind - Affordable collection tracking in Telegram. It relies on an affordable
on-chain subscription system to deliver all relevant collection data to your Telegram chats. It is not limited to one
chat per collection, rather you can add it to as many chats as you want, private or public.

## Functionality

Spinacho offers all crucial NFT bot functionalities from a single bot, in all your chats. By subscribing, you gain
access to all of them. There are no tiers, everything is available through a single subscription. Spinacho works on the
principle of **default chat collections**. Every chat can pick its default collection by sending
`/select ${ticker}`. Spinacho will look up a collection with the given ticker, and select it as default for that chat.
Default collection can be changed or removed at any time. You can switch between different collections seamlessly.

#### Feature overview
- Realtime mint notifications
- Realtime notifications about marketplace events
    - Here is a list of supported marketplaces with a list of supported events from each
        - NFTKey
            - Listing
            - Buy
            - Bid
            - Bid accepted
            - Global bid
            - Global bid accepted
        - Rareboard NFTKey
            - Buy
        - OpenSea
          - Coming soon
- View any NFT from any subscribed collection with the `show` command. If there is a default collection,
   calling `/show ${id}` will assume you're looking for a token from the default collection. You can also specify a
   collection ticker: `/show ${ticker} ${id}` to see an NFT from any of the subscribed collections.
- View addresses via their space.id or PancakeSwap usernames

#### Usage screenshots
![Mint notification](mint.png "Mint notification")
![Listing notification](listing.png "Listing notification")
![Show command](show.png "Show command")

## Subscription-based model

Spinacho works on a simple, on-chain subscription-based model.

Subscription is paid by calling `createSubscription` or `extendSubscription` on
the [SpinachoSubscription](https://bscscan.com/address/0x210BBC42561d440c20eF1f833F62D17894c29Af0)
contract on BSC, preferably through [spinacho.org](https://spinacho.org) or manually on BscScan. Single subscription fee will cover _one month_ of premium usage, but you can purchase multiple months in advance.

Spinacho performs daily on-chain checks for subscription updates. Therefore, after extending your subscription,
everything is handled automatically. Spinacho will perform daily checks for subscription validity, and in case of expiry, will notify you in all groups where
your collection is selected as default. You will be notified once every day during the last 7 days of the subscription
with a reminder message. If the subscription is not renewed, on the day of the expiry, all chats where your collection
is selected as default will receive the termination message, and the default selection will be removed. You can always
extend your expired subscription and continue using it regularly.

**note** 1st month of subscription is FREE

## Supported commands

- `/show ${ticker} ${id}`
    - Shows the token with `id == ${id}` from the given collection
- `/show ${id}`
    - Shows the token with `id == ${id}` from the default collection
- `/select ${ticker}`
    - Selects the given collection as default in a chat
- `/reset`
    - Removes the default collection from a chat
- `/current`
    - Shows currently selected collection for a chat
- `/collections`
    - Shows all currently and previously subscribed collections
- `/help`
    - Show help
