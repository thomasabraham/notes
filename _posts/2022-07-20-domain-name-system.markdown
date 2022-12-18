---
layout: post
title: DNS - Domain Name System
date: 2022-07-20
categories: internet
---

## Why do we need DNS?
Using the internet, computers from various parts of the world can communicate
with each other. This process can be compared to how people used to send letters
to each other through post offices. Computers send IP packets to each other,
through routers, ISPs and various types of cables; they just do it very fast.
And Unlike the physical address on the envelopes, computers uses IP addresses to
send the IP packets to the right computer. And every computer connected to the
Internet got one; except when you share an
[IPV4](https://en.wikipedia.org/wiki/IP_address#IPv4_addresses) address with
others, but I'll ignore it for now.

Whether it is an IPV4 address (example - `22.23.38.57`) or the more modern IPV6
address (example - `0:0:0:0:0:ffff:1617:2639`), they are both designed with
computers in mind. How can we humans tell the computers, which computer we want
them to connect to? I'm sure there are still many corporate offices where
different servers are identified by their IPV4 addresses. But even if we can
somehow remember the IP address, they can change over a period of time for a
variety of reasons.

The Domain Name System, or DNS for short, gives us easy to remember names like
[notes.thomsbox.com](http://notes.thomsbox.com) that can be mapped to an IP
address. 

We use a DNS to resolve the IP address when entering an addresses like
<https://notes.thomsbox.com/2022-07-20-domain-name-system.html>. In this
example, The `https` is the protocol, `notes.thomsbox.com` is the host, and
`2022-07-20-domain-name-system.html` is the path. The host part is used to
identify the computer to which we want to communicate with; the protocol says we
want to use the HTTP protocol for the communciation and the path part says that
we want to `GET` that particular page.

When we type (or copy paste) this example to the address bar or a browser, first
it has to convert the host part, `notes.thomsbox.com` in our case, to an IP
address. How it does that using DNS is covered in the next part.

## TODO: How DNS translates a domain name to an IP address?
Let's take `thomsbox.com` as an example, try the following in your terminal.


{% highlight shell %}
    dig thomsbox.com
{% endhighlight %}

## TODO: Different types of DNS records
