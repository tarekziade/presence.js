presence.js
===========

**This is an experiment**


XXX just random notes below

The goal of presence.js is to provide a presence feature for web apps.
Combined with plain webRTC, it can be used to write applications where
you want several users to interact on web apps.

There are two components:

- the server, that keeps track of who's present
- the client, that tells the server about its presence

features:

- the client can notify the app the user is present under a
  Persona-verified e-mail
- the client can connect, disconnect and set a status (active, hidden, idle,
  etc)
- the client can see who else is present, if it's a publicly available info.
  (think: the geolocation popup)

not in scope:

- initiate a webrtc dialog between users
- channels, etc
- sessions

server API

- POST  /++presence++/   {'email': xxx, 'status': xxx, 'realm': xxx}
- GET    /++presence++/email  => sends a 404 or some info if publicly available
- GET    /++presence++   => sends a batched list of users
- GET   /++presence++/search?  search for online users

Scaling etc - the server can be backed by an XMPP server - but the initial
implementation is a stupid node.js app

Demo app => a chat app based on presence.js and webrtc


