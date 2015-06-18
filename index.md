title: ETDG, Introduction to Networking
date: 2015-06-23
author:
    name: Ben Wallberg, Peter Eichman
    email: wallberg@umd.edu, peichman@umd.edu
output: index.html

--

### Introduction to Networking

UMD Libraries, Emerging Technologies Discussion Group

June 23, 2015

--

### Internet protocol suite

Many network models exist.  Today we will discuss the network
model used for The Internet, known as the Internet protocol suite.

https://en.wikipedia.org/wiki/Internet_protocol_suite

--

### Layer Model

A common way to build and understand complex computer systems is to create layers,
with each layer only needing to know its own implementation and how to
interact with an adjacent layer.
- Application layer
- Transport layer
- Internet layer
- Link layer

In the Internet model each layer only needs to understand itself and how to
interface with the next lower layer.
