# Documentation
## Import and configure

First, download the NPM package and import it in your app. You can import the package by adding the following lines:
``` js
const { EvelonSDK } = require("evelon");
```

As a user, you need to `authenticate` yourself and set the `chainid`. Add a config to your app:
``` js
const config = {
  apikey: "test_ev_cd153f41193e692ec0434ecb52a9c5a1560d7e13", // This should be your API key (copy it from your profile page)
  chainId: 1287,
};
```

Load the SDK and set the configuration parameters:
``` js
const sdk = new EvelonSDK(config);
```

## Example function
### Get NFT data
``` js
async function getNFTs() {
  const data = await sdk.getAllNFTs(
    "0x02F4Db4adeA0E1E84e3Ff4901c4Af3DB4Cca2f80"
  );
  return data;
}
```

### Update NFT
``` js
async function setNFT() {
  const image = await fs.readFile("./images/example.jpg");

  const data = await sdk.modifyNFT(
    3,
    "New NFT name here", // NFT Name
    "", // Description
    "https://lh3.googleusercontent.com/Ryg5ih-fOWbpEGDpbJYJz5RTq3_28Tvo2h3JQRCdiz16lw5ghitDMN6hcWA57g0d6_8VOqQYcCemRBOfZGQA64ZKkFOn71zuF1LDsXwCh4ywF-_z6VqxbBqmbQvK_-PWfZcztxDd1WDTEEUHX6GdP60", // Image
    [
      // {
      //   trait_type: "Your trait type",
      //   value: "Your value",
      // },
    ]
  );
}
```