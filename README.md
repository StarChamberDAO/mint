# Star Chamber Minting Daap: Installation

```sh
git clone https://github.com/HashLips/hashlips_nft_minting_dapp.git
```

Make sure you have node.js installed so you can use npm, then run:

```sh
npm install
```

## Usage ℹ️

In order to make use of this dapp, all you need to do is change the configurations to point to your smart contract as well as update the images and theme file.

For the most part all the changes will be in the `public` folder.

To link up your existing smart contract, go to the `public/config/config.json` file and update the following fields to fit your smart contract, network and marketplace details. The cost field should be in wei.

Note: this dapp is designed to work with the intended NFT smart contract, that only takes one parameter in the mint function "mintAmount". But you can change that in the App.js file if you need to use a smart contract that takes 2 params.

```json
{
  "CONTRACT_ADDRESS": "0xa739c8952e73f73C52501Fb0Fb9F011719B7Bc9b",
  "SCAN_LINK": "https://ropsten.etherscan.io/token/0xa739c8952e73f73C52501Fb0Fb9F011719B7Bc9b",
  "NETWORK": {
    "NAME": "Ropsten",
    "SYMBOL": "ETH",
    "ID": 3
  },
  "NFT_NAME": "Star Chamber DAO",
  "SYMBOL": "SC",
  "MAX_SUPPLY": 100,
  "WEI_COST": 300000000000000000,
  "DISPLAY_COST": 0.3,
  "GAS_LIMIT": 285000,
  "MARKETPLACE": "Opeansea",
  "MARKETPLACE_LINK": "https://opensea.io/collection/starchamber",
  "SHOW_BACKGROUND": false
}
```

Make sure you copy the contract ABI from remix and paste it in the `public/config/abi.json` file.

Now you will need to create and change 2 images and a gif in the `public/config/images` folder, `bg.png`, `example.gif` and `logo.png`.

Next change the theme colors to your liking in the `public/config/theme.css` file.

```css
:root {
  --primary: #ebc908;
  --primary-text: #1a1a1a;
  --secondary: #ff1dec;
  --secondary-text: #ffffff;
  --accent: #ffffff;
  --accent-text: #000000;
}
```

Re-add background layer + Re-add (replace) the "Star Chamber DAO" text header with an image to App.js if you so wish.

```
      <s.Container
        flex={1}
        ai={"center"}
        style={{ padding: 24, backgroundColor: "var(--primary)" }}
        image={CONFIG.SHOW_BACKGROUND ? "/config/images/bg.png" : null}
      >
 <StyledLogo alt={"logo"} src={"/config/images/logo.png"} />
```

Now you will need to create and change the `public/favicon.ico`, `public/logo192.png`, and
`public/logo512.png` to your brand images.

Remember to update the title and description the `public/index.html` file

```html
    <title>Star Chamber DAO</title>
    <meta name="description" content="Star Chamber DAO" />
```

Also remember to update the short_name and name fields in the `public/manifest.json` file

```json
{
  "short_name": "SC",
  "name": "Star Chamber DAO",
}
```

After all the changes you can run.

```sh
npm run start
```

Or create the build if you are ready to deploy.

```sh
npm run build
```

Now you can host the contents of the build folder on a server.

That's it! you're done.
