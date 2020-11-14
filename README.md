# hw-sign: Hardware Wallet Browser Signer

## setup
Must `browserify` `bitcoinjs-lib` prior to use. Optionally can run through `uglify` to minify. Also need the `index.js` file included here for the below commands.
```
npm install
npx browserify -r . --standalone bitcoinjs > bitcoinjs.js
npx uglifyjs -c --mangle reserved=['BigInteger','ECPair','Point'] bitcoinjs.js > bitcoinjs.min.js
```

Then to run HTTPS because Ledger requires that, so use:
* https://github.com/FiloSottile/mkcert
```
mkcert -install && mkcert -key-file snowpack.key -cert-file snowpack.crt localhost
npx snowpack dev --polyfill-node --secure
```

Go to (https://localhost:8080) and click the "Get Address" button to test.

## Notes
* Ledger's WebUSB library requires us to click a button or do some user interaction to do the test.
* Ledger requires HTTPS.
