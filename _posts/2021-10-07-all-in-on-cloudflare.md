---
layout: post
author: Wook
title: All in on Cloudflare
date: 2021-10-06 00:00:00 -0400
---

Okay, Cloudflare has won me over.  It has been a slow process, but today I decided to move as much of my online presence to Cloudflare as I can.

Why?

TL;DR:

> I've used  Cloudflare tools that I've liked.  They don't trip my privacy wonk senses.  They are in way better shape than my current domain registry appears to be.  Cloudflare seems to have me covered in what I need to be "on the internet".

Firstly, any company that uses Lava Lamps for anything "real" gets my respect.  Cloudflare uses a [wall of Lava Lamps](https://www.cloudflare.com/learning/ssl/lava-lamp-encryption/) to create encryption keys.  That is an amazingly good idea for generating random numbers.  In fact a genius idea.

There is a practice in the internet world where if you type in an incorrect name of a website, instead of saying "doesn't exist", your internet provider will instead send you to a page with ads on it.  There are also internet crime attacks that can be carried out in part by fucking with DNS servers on the internet.  These attacks are sophisticated, and require expertise to prevent.

Google, being a general internet good guy created [Google Public DNS](https://developers.google.com/speed/public-dns/), with an easy-to-remember internet address of 8.8.8.8.  Google DNS is my default DNS on Google Fiber.  They created an overall fast DNS service, that replies honestly, and they protect it from becoming an attack vector.

But Google tracks everything and remembers it all.  They track you for their advertising business.  This gives me a mild case of the creeps from a privacy perspective.  I don't have time to dive into this to figure out how transparent they are about this.  I just decided to avoid it.

Along came [Cloudflare's 1.1.1.1 service](https://1.1.1.1).  Another DNS server, and another easy-to-remember address.  They state up front that they do not track access, and your browsing is private.  This is also tied in with WARP+, their VPN service.  I use WARP+ on my iPhone and iPad, and so far it has been bulletproof over the last year or two.

While working on my Kubernetes thing, I ran into and used Cloudflare's cfssl tool.  Much simpler and user-friendly than openssl.  A tool they created internally, and then shared with the world because that's what being a good internet citizen looks like.

I registered my domains via a company called [Superb Internet](https://www.superb.net).  I used them because they were the first webhosting service I ever used.  I moved to a cheaper one that didn't work, and another cheaper one that may have worked if I'd been able to figure out their horrible management interface.  Neither of those other two companies ever got email right for my domains.  I went back to Superb.

But recently, [Superb was acquired by CherryRoad Technologies](https://www.superb.net/about/pressrelease.php).  I don't know anything about CherryRoad.  What I do know is that suddenly I started getting bombed with "you must update your credit card details" emails every day.  I mean: Every. Goddamn. Day.  I opened a support ticket and told them I'd update my credit card when I was going to spend some money with them and not sooner, so please stop spamming me.  Their response: "No, give us your credit card details".

Fuck them.

Plus, the Suberb management tool, called MyCP, hasn't been updated hardly at all since it came out in 2005.  The DNS editing tool is a horror to use.  All leading one to believe that no money is being spent.  Indicates to me a company in decline.  Time to move on.

Tonight, I noticed that Cloudflare has a free account for doing content delivery for personal, small, web sites.  So I signed munged.org up.  In a day or two, once the DNS swings over to the Cloudflare servers, this site will be coming at you from wherever Cloudflare's servers are, which is all over the place.

I also noticed that Cloudflare has a "no markup" DNS registry.  Since Cloudflare is probably in way better shape than Superb, I figure I'll move my domains while I'm at it.

I host this website in [GitHub Pages](https://pages.github.com).  Cloudflare also has a [Cloudflare Pages](https://pages.cloudflare.com).  I probably won't make this switch, because GH pages are based on Jekyll behind the scenes.  To move to CF Pages would involve building the Jekyll rendering step myself, which I don't really want to spend time on right now.

It is also just nice to have everything in one place, as much as possible.