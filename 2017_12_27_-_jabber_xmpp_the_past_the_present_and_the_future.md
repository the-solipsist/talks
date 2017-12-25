---
title: Jabber/XMPP - the past, the present & the future
theme: league
---
# Jabber/XMPP
### the past, the present & the future
[Daniel Gultsch](https://gultsch.de)
<p><small>December 27th 2017 @ 34C3</small></p>

---

## Motivation
* Single vendors are dangerous
* Open Source doesn’t help
* Phone numbers 

Note: After being a Jabber User for more than a decade I started working on my own Jabber client four years ago and later became actively involved in the XMPP community.

While there are many reasons for using Jabber instead of WhatsApp or Signal by personal motivation is that I don’t want a single company to control my communication. Not only do companys like Facebook see whom I communicating with they can also control whom I’m communicating with. Or even worse; stop me from communicating at all.

Or to put this in other words; I don’t want to get in a Twitter-fight with Moxie only to wake up one morning and not being able to use Signal anymore. And this has nothing to do with being paranoid. Companies have kicked people of their networks before. There is this interview with the CEO of cloudflare where he describes that he woke up one morning and decided to [take the daily stormer of the internet](https://www.youtube.com/watch?v=ULXWJgmhP1c).

This is also the point where just being open source doesn’t help you at all. If Moxie decides he doesn’t want me to use Signal there is absolutely no benefit in Signal being open source. Yes I can setup my own server. But nobody else would be using that server.

I’m also not a huge fan of instant messengers being tied to my phone number. While I’m totaly fine with putting my Jabber ID on my website or handing that out to new people I meet I’m not comfortable handing my phone number out to random strangers.

---

## Jabber/XMPP
* Provider independent
* IETF working group since 2002
* Extensions *published* by the XSF

Note: So what is Jabber/XMPP and does it help us to take back our control?
Jabber is federated, provider independent instant messaging. Just like in email users are identified by username@provider and can freely choose a combination of client and provider since every client will work with every provider.
Clients are usually not developed by the same companies that act as providers.

The base protocol is published as an IETF standard that can easily be extended. Extensions are published by the XMPP Standards Foundation. I say published because standards are not written by the XSF. The XSF just provides the common framework and the standarization path. Extensions can be written by anyone. Although of course a lot of people who write extensions are also involved in the XSF.

----

### Jabber or XMPP?
* Jabber = Ecosystem (Email, Web)
* XMPP = Protcol (IMAP, SMTP, HTTP)

Note: Just to clarify things very quickly. When I say »Jabber« I’m refering to a network of providers which can talk to each other and the clients which can connect to those providers. Jabber describes the ecosystem and the term can be compared to the terms »Web« or »Email«.
XMPP is just the protocol. So when a company like Facebook or HipChat create an XMPP interface this interface is just XMPP but not Jabber because they are not part of the Jabber Ecosystem.

----

### Jabber vs Matrix
* Similiar goals
* Personal preference
* Gateways are flawed

Note: Just to get ahead of the question that some of you will have at the end of that talk; Whats the difference between Jabber vs Matrix or which one is better?
I’ve personally never really used Matrix so I’m not the right person to ask. They have similar goals and if either one of those ends up taking away the power Facebook and Google have over us I’m happy.

Use what ever you prefer.

But don’t get all excited about gateways. XMPP has had transports 15 years ago and the entire concept is flawed. It’s incredible difficult to map one API on to anther. Gateways can only ever provider lowest common denominator of features between the two chat systems. WhatsApp can delete messages? Well if Matrix can’t delete messages that feature won’t work properly. XMPP can edit the last messages? Well if WhatsApp can’t you won’t be able to use that feature.

That’s why multi protocol messenger like Pidgin or Trillian usually suck. That’s why concept’s like telephaty never really took of.

Transports work fine for very limited protocols like IRC where your own protocol is a superset of the protocol you are trying to create a gateway to. XMPP and Matrix both of working IRC gateways. But that’s it. It won’t work for protocols more complex than that. And by the way it will break end-to-end encryption.

---

## 2016
* Reliable & battery friendly ¹
* Multiple devices ¹
* Media transfer ¹
* Group chats
* Optional: E2EE ¹

<p><small>¹ When using a modern client and server</small></p>

Note: In case you haven’t used XMPP in recent years  

----

### State of Mobile XMPP in 2016
* [gultsch.de/xmpp_2016.html](https://gultsch.de/xmpp_2016.html)
* XMPP talk @ FrOSCon 2015, [media.ccc.de](https://media.ccc.de/v/froscon2015-1548-xmpp_2015_-_challenges_of_modern_day_instant_messaging)

----

### A choice of E2EE
* None
* OMEMO: Forward secrecy
* PGP: Server side archive

---

# 2017

---

## Direct TLS / SNI
* Replaces STARTTLS
* Domain name / certificate selection
* Faster
* Public WiFi / Port 443

---

## Push
* *something* happened
* Important on iOS
* Might become important on Android
* Server support / Proxies over App server

---

## Group chat read markers
* XEP-0333
* small changes to XEP
* *Read to this point* UI

---

### Message Styling
* Not markdown
* Italic, bold, strikthrough & monospace
* Inspired by WhatsApp & Slack

---

## Avatars
* Two »competing« standards
* One simple solution

----

### XEP 0084: User Avatars
* efficient interface
* only contacts can access

----

### XEP 0153: vCard-Based Avatars
* Data is public
* works in group chats

----

### XEP-xxxx: User Avatar to vCard-Based Avatars Conversion

---

# Future

---

## OMEMO by default
* Easier trust model
* World readable keys
* Deployment

----

### Easier trust model
* TOFU is difficult to apply
* BTBV
 * Trust everything by default
 * Trust new keys
 * After scanning a contact, stop trusting new keys from that contact

----

### World readable keys
* `publish_options`
* `mod_omemo_all_access`

----

### Deployment
* Every plattform has at least on client
* [omemo.top](https://omemo.top)

---

## OTR must go away
* Unreliable
* Doesn’t work with multiple devices
* Auto response loops

---

## Image Thumbnails
* XEP-0385: Stateless Inline Media Sharing
* OMEMO: Data URIs
* Size limit (10,000 bytes)

---

## Initial login
* Initial login / discovery expensive
* Resume requires TLS and SASL

---

## Message routing
* Delivery to multiple devices
* Offline delivery / catchup

---

## SPAM
* »Cyber criminals« spamming each other
* Be careful about publishing your JID
* Blocking made easy / No notifications
* [Spam Reduction on yax.im](https://yaxim.org/blog/2017/12/22/spam-reduction-on-yax-dot-im/)

---

## Conversations v2.0.0
March 24th, 2018

---

# Getting started

---

## Clients
* Conversations
* ChatSecure
* Gajim / Dino

---

## Servers
* Self hosting
* Hosting
* Domain hosting

---

## Developers wanted
* Go help out the existing clients!
* Tooling
 * Compliance Tester
 * Server Status page
* Google Summer of Code

---

# Questions?
[@iNPUTmice](https://twitter.com/inputmice)

[gultsch.de](https://gultsch.de)
