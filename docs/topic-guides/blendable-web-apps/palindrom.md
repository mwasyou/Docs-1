# Palindrom

## Introduction

Palindrom is a library that implements a simple, standards-compliant protocol for thin client web apps. It allows for Single Page Applications with no logic on the client side.

## Protocol

![](../../.gitbook/assets/palindrom-flow%20%281%29.png)

With Palindrom, the application state is kept in JSON. Any changes to it, coming from the client or the server, are expressed in automatically generated JSON-Patch \([RFC 6902](http://tools.ietf.org/html/rfc6902)\). HTTP PATCH and WebSocket are used to send the changes over the network.

With this protocol, the server owns the view-model and controls its content. The clients suggests changes by sending user input with HTTP PATCH.

The protocol is defined in the [Palindrom wiki](https://github.com/Palindrom/Palindrom/wiki/Server-communication).

## Implementation

To make it easy to use this pattern in your web apps, we are using a library called [Palindrom](https://github.com/Palindrom/Palindrom). It is possible to use Palindrom implicitly in your web apps, so using it becomes self-configurable and as easy as putting few lines of code in your app.

For the maximum benefit, use a two-way data binding framework such as Polymer or AngularJS to render your views in HTML without writing a single line of JavaScript. If you have needs for client-side coding, a JavaScript object is exposed and can be used with any library, such as D3 or React.

In most of the code samples we stay on the bleeding edge of web development by using Palindrom with Polymer and Web Components.

