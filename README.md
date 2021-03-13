# wrongthink
wrongthink chat v2:
* is peer-to-peer
* has end-to-end encryption (Axolotl Ratchet over PeerJS)
* supports Markdown
* has notifications using MaterializeCSS

## how are things derived
### fingerprint
the fingerprint used for connection is derived from the SHA-512 hash of the public key. the fingerprint is converted to decimal and then the first 10 digits are taken (allowing for 10 billion combinations).
### safety number
the safety number is derived from `SHA256(xPublic + yPublic)`, where both keys are the identity keys of the peers. the hash is converted to decimal and then the first 35 digits are taken (allowing for approximately 120 bits of security). the order of the fingerprints is determined by the first byte of the public identity keys.

## custom clients
custom clients are as easy as 1, 2, 3. just use PeerJS and use https://wrongthink.me:8080 as the PeerJS server. from there, you'll need to use forward-secrecy to handshake and send messages.

## running it
just open `index.html` in the browser of your choice.

## misc
`v2.0.html` is the old version of wrongthink2 which used OTRv3. it is now obsolete (NOT compatible with any new clients) and kept only for educational purposes. `v1.html` is the old version of wrongthink which was not E2EE. it is still usable with server `wss://wrongthink.me:9764` but not recommended. it is also kept only for educational purposes.
