# hw-sign: Hardware Wallet Browser Signer

## install deps and run
Needs to run HTTPS because of Ledger requirements
* https://github.com/FiloSottile/mkcert
```
mkcert -install && mkcert -key-file snowpack.key -cert-file snowpack.crt localhost
npm install
npx snowpack dev --polyfill-node --secure
```
