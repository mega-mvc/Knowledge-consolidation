# How HTTPS works

1. Client establishes a connection to server

2. Client ask for certificate, Server responds with the cert

3. Client verifies the cert, then give public key to server 

4. Client generates a sessionKey, encrypt it with server's publicKey (encryptedSessionKey)

5. Server receives the encryptedSessionKey, decrypt it and get the original sessionKey

6. Client and servers begins to transfer data using encrypted data with sessionKey 

<img width="455" alt="image" src="https://github.com/hoangelec/Knowledge-consolidation/assets/9737526/bc1d8ea2-0bd3-4d16-b55b-26b15b83d9fd">

# SSL pinning

## Concepts: 
We store the server's identity inside the app and use it to verify whether the server's identity is valid. 

## 2 ways we can do this:
- We store the cert (or cert's hash)
- We store the public key of the server. This is more flexible because cert can be expired

## Problem: Pinned SSL expired?
- Use a long-alive cert
- Apply dynamic renew solution 

