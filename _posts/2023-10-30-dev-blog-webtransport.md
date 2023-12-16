---
layout: post
title:  "Dev blog: WebTransport vs WebRTC"
author: kevthecoder
---

At Kengin, we're treating web as a first class deployment platform. This means
we need multiplayer services that can work across web and native 
clients. Traditionally that meant WebRTC, however the 
[WebTransport](https://www.w3.org/TR/webtransport/) standard is nearing 
completion.

We faced the difficult choice of being an early adopter of WebTransport or going
with the safer option of using WebRTC.

Some of the pros for WebRTC are:

- It's a mature standard, so there are code libraries already available
- It allows peer-to-peer networking. This can be useful if you want serverless
  networking scenarios.
- We already have some WebRTC code and infrastructure

Some of the advantages of WebTransport are:

- Low latency connections
- Connections can be reliable (where data is important and delivery
  should be ackknowledged) or unreliable data where it doesn't matter is some
  data is lost (e.g. a realtime voice stream where speed is more important than
  some lost data) where unreliable connections mean lower latency
- It allows multiplexed connections - making better use of connections in a non
  blocking way
- You can create multiple streams per connection, making it a lighter weight
  solution to manage multiple data streams

However there are some disadvantages to WebTransport:
- Slightly more complicated to develop with locally - requires a secure context
  so you need to generate TLS certificates to use locally. This level of 
  security is  good for runtime though.
- Not supported in Safari browser yet, but 
  [it's coming](https://github.com/WebKit/standards-positions/issues/18#issuecomment-1495890122)
- It's early days, so library support isn't great
- It's based on http/3 and uses IPv6 which not all hosting providers supply.

We've decided to take the decision to support WebTransport early on. It took a
bit more effort to implement but we're happy with the methods it gives us to
manage streams of data. The deciding factor was the low latency, UDP style
connections which are going to be useful for multiplayer data.

Some of the challenges setting up WebTransport were around http/3. This requires
IPv6, which does't have great support yet amongst all hosting providers.
We've currently got it running on AWS EC2, but will look to extend support to
other providers soon.
