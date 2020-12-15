# w7--research---iman

# HTTP vs HTTPS
protocols used by browser and server to communicate and exchange information
- in http (Hyper Text Transfer Protocol) data is unencrypted
- in https (Hyper Text Transfer Protocol security): http protocol but with data encrybtion using SSL/TLS which means more Security

## What are TLS/SSL 
- Secure Sockets Layer (SSL) protocol: protocol created by Netspace company for establishing an encrypted link between a server and a client,
ssl have two keys for encrypting: 

1.public key: 
Public key: server gives it to client to encrypt data and send it back to server
2. private key: found only in the server side and it's used to decrypt data sent by client

- Transport Layer Security (TLS): it's an improved version of SSL

## why HTTPS is important
1. for privacy, since data is encrypted
2. for integrity: that the message is not manipulated on the way to its destination(man-in-the-middle attack)
3. for identification: the site that you are visiting is indeed the one you think it is couse its the only one have the private key.



# Stateless Authentication:
uses tokens which often JSON Web Tokens(JWT),It creates tokens and it to gives clients after logging-in that considered as identity to users when they request certain resources and those tokens stored in client side.

## flow of Stateless Authentication
user login user name and password => server validates this againest database stored data and creates token with cryptographic signature and gives it to user => 
user request resources with the given token => server verify token => if its the same and not mainipulated it gives you resource you want.

## Advantages of Stateless Authentication
1. Reduce the number of database access since the token is not stored in database
2. Easy to scale since the token is store in client side so it does not matter which backend server the request is routed to

## Disadvantages of Stateless Authentication
1. Cannot revoke the session anytime before the expiration time which selected when creating token since is not stored in database

# Stateful Authentication
Stateful session is created on the backend side, and the correspondent session reference Id is sent to the client. Each time the client makes a request to the server, the server locates the session memory using the reference Id from the client and finds the authentication information. In this model, you can easily imagine that if the session memory is deleted on the backend side, then the session reference Id, which the client is holding, is completely meaningless.

## flow of Stateful Authentication
 user submit loggin details => server store session data in memory and send 'sesssion_id' to cookie => when user request certain resource with that 'session_id' => server compare seeion_id with data stored in database => if it's identical it gives you the requested resource
 
 ## Advantages of Stateful Authentication
 server can revoke the session anytime since session is not stored in database
 
 ## Disadvantages of Stateful Authentication
 1. increase the number of database access since sessions stored in database
 2. Session data can be changed if theres database attacks
 


 
 
 















