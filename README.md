# gundb-chat-blockchain-content-addressing
Demo example for Gundb with blockchain proofs.

Includes publicly accessible (yet not over writable) blockchain proofs aka branch of merkle-tree.

Content addressing is also highlited here. If you know the sha256 of some content you may retrieve the content and proof from gun.

## Demo
https://plato.seallake.net/API/v1/data/gunProof1/chat-proof.html <-- may not always be available

## Installation

Run from browser or push to your fav cdn. If you hit a cors error it's due to calling the cryptowerk api. Just drop the page into this...
https://app.netlify.com/drop

## Usage

Once you enter a chat message or two refresh the page. When hovering on a chat message you will have a link to the blockchain explorer, a copy of the data Seal (hosted by cryptowerk.com). The data seal is eventually stored back into gundb. Tap on who, what, and when to see details of the proof.

## Contributing
Pull requests are welcome but I'm unlikely to do anything beyond cleaning up the code in this example.

## TODO

- Automatically send the proofs into gundb from Cryptowerk.com
- Create a page that shows how to retrieve content and proofs via hash
eg retrieve the original data from it's hash 
```javascript
gun.get('#3654cf4b20d505f2d311e62c63637eeac99e6672ffcf9104c697fed27e17b25d').map().once(data3=> {
     gun.get(data3).get('dataSeal').once((d=>console.log(d)));
})
```
eg retrieve the blockchain proof from the hash of the original data

```javascript
gun.get('#3654cf4b20d505f2d311e62c63637eeac99e6672ffcf9104c697fed27e17b25d').map().once(data3=> {
     gun.get(data3).get('ogData').once((d=>console.log(d)));
})
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
