- [Web Monetization Quick Start](#content-monetization-quick-start)

# Web Monetization Quick Start

To get started with Web Monetization, you'll be taken through these three steps:

1. Create an XRP wallet
2. Get a "Payment Pointer" on Siren
3. Add the Web Monetization script to your website.

Once you complete these steps, you'll be able to monetize your site traffic to
receive live XRP.

### Create an XRP Wallet

You can use the [Toast Wallet](https://toastwallet.com/) to create an XRP
address. Follow their instructions until you've created a wallet. Make sure you
back up your secret!

When you've created your wallet, you'll have an address that looks something
like `rsKguPpyAZhpHqGyP8A3xu7Acsk3PF8zyx`. This is your **XRP Address**.

### Get a Payment Pointer on Siren

Now that you have an XRP address, you can easily receive money through Siren.
The identifier that you use to receive money with Interledger is called a
**Payment Pointer**. It starts with a `$`, then a domain, and then an optional
path. Your payment pointer will be based on Siren's domain, so you don't need
to run anything yourself.

Your payment pointer is: `$spsp.siren.sh/YOUR_XRP_ADDRESS`.

So if your XRP address were `rsKguPpyAZhpHqGyP8A3xu7Acsk3PF8zyx`, your payment
pointer would be `$spsp.siren.sh/rsKguPpyAZhpHqGyP8A3xu7Acsk3PF8zyx`.

### Add the Web Monetization Script to Your Website

Add the following tag to your site's body. Make sure to replace
`YOUR_XRP_ADDRESS` with your XRP address.

```
<script>
  if (window.MonetizationRequest) {
    var money = new MonetizationRequest({
      receiver: `$spsp.siren.sh/YOUR_XRP_ADDRESS`
    })

    money.start()
      .then(() => {
        // You can insert code here to thank the user
      })
  }
</script>
```
