---
title: "Making a Portfolio Pt 2"
summary: "Join me in the journey of setting up this portfolio and blog."
date: "Sep 29 2024"
draft: false
tags:
- Web
- Journey
---

In the last post I covered my journey in selecting the underlying technology for this website.
The result was choosing Astro with one of their free templates to get me started.
In this post, I'm going to cover the next step: finding someone to host it.

## Requirements

Just as there is a plethora of static site generators, there's also a plethora of services that want to host them for you.
This isn't surprising, of course, because where there is a popular tech stack everyone is uisng, companies are going to optimize for
it.

Just like with the tech stack itself, I have some requirements going into this discovery process:

- Cost should be low, preferably in a free tier
- Serverless is preferred
- Built-in support for preview deployments is a plus
- Github integration

Basically, like with my choice for an SSG, I want minimal fuss.
This may sound counter-intuitive for someone's who day job is being an SRE, but even in my job this is generally the way I approach
things.
Throughout the years, I've found that introducing complexity is so easy that you might as well assume it's a constant force acting
against you at all times.
Don't read this as a suggestion to farm _everything_ out to third-parties, either.
There's a "radical center" point that is generally only discernable after trying and failing to fight this battle many times over.

But I digress.
The point here is that I want the focus to be on writing, not spending all of my time tinkering with the underlying systems.
Given a choice, I am often more inclined _to_ tinker with these systems.
So some of this is just understanding my own pitfalls and setting myself up for success.

## Excuse me, can you host my static site?

Unfortunately, my list of requirements doesn't really make the list of potential providers that much smaller.
However, going into this process, I already had a list of services that I knew would likely fit the bill:

- [AWS S3](https://aws.amazon.com/s3/)
- [Cloudflare Pages](https://pages.cloudflare.com/)
- [Netlify](https://www.netlify.com/)
- [Railway](https://railway.app/)
- [Vercel](https://vercel.com/)

Now, here is where things get tricky.
While I just spent a lot of time talking about the imporant of simplicity, that doesn't mean I'm not interested in learning
something new (which necessarily means added complexity).
These types of projects are the main contributor towards growing my experience and knowledge as an engineer.
So this necessarily means I will be slightly biased in my decision here.

First, I've been working with S3 for years, and while it would be the quickest thing for me to reach for, it robs an opportunity for
me to expand my horizons with something else.
Likewise, I also have previous experience with Netlify, and while it's even simpler in design than S3, I'm worried about their cost
model. Specifically, it's gotten worse since I first used it.

That leaves me looking primarily at Cloudflare, Railway, and Vercel.

### Cloudflare

I've been eyeing Cloudflare Pages ever since it launched.
Their free tier is impressively liberal: basically, as long as I'm not deploying ~15 times a day (very unlikely with a local dev
server), then I'm fine.
I don't expect my portfolio's traffic to blow up, but it's always nice knowing if that _does_ happen, I won't come back to a massive
bill due to unlimited requests/bandwidth.
Finally, it's Cloudflare.
If there's one service I expect to have high reliability and a blazing fast network, it's them.

Interestingly enough, that also brings me to the one con with them: it's Cloudflare.
In the last few years, they've been in the headlines a couple of times for having a poor track record of responding to baseless DMCA
requests.
Now, I hope to never post something so controversial as to attract some of these trolls, but should such a thing happen, I have low
confidence that Cloudfare won't just bend over and shut my site down.

That being said, they certainly check all of the boxes: free, serverless, wonderful GitHub integration that includes multiple
preview deployments, and great documentation to boot.
It seems like I could have something working in a few hours.

### Railway

I'm not sure how long Railway has been around.
I know they are relatively new and have seem to grown quite substantially in the last year or so.
Their major promise is "a platform without a platform engineer."
Which, of course, is ironic given that I've spent the last year of my career acting more like a platform engineer than anything
else.
However, that's actually the reason I'm interested in trying it: what better way to learn platform engineering then use what appears
to be a popular developer platform?

All that being said, Railway is by far the most "complex" offering on the list in terms of getting something going.
This is primarily because their audience is far bigger than static site owners.
They are targeting startups and founders with more complex requirements.
For example, they have a robust offering for things like disk, networking, and even database provisioning.
Not surprisingly, they do check all of my requirements: quasi-serverless (it's all abstracted away), native GitHub integration, and
support for multiple environments out of the box.

All of these bells and whistles necessarily means there's no free tier (such things would be expensive to give away for free).
But they have a "hobby" tier priced at $5/mo, which is well within my means of paying.
I'll admit, the pricing scheme is a bit odd: the $5/mo is the "plan" cost, but it also includes $5 of credits.
They estimate a static website to cost $0.50 per month.
So I'm basically mostly paying for platform.

### Vercel

Out of the three I've selected, I believe Vercel is the oldest.
I consistently see the name show up in recommendations for deploying static websites.
They seem to deeply integrate with existing frontend ecosystems, Astro being one of them.

They are very comparable to Cloudflare Pages in their free tier, the difference being it's not "unlimited."
Like Cloudflare Pages, their deployment pipeline is optimized for minimal fuss and direct GitHub integration.
Out of the box, they do seem to offer a few additional features (image optimization, advanced caching, etc.) which is to be expected
given they've been around longer.

Overall, Vercel seems to be proven service that has a lot of fans.
It fits all of my requirements and even has entire documentation page detailing how to deploy Astro.

## And the winner is...

At the end of the day, I've decided to go with Cloudflare Pages.
It's practically free, ships on a blazing fast edge network, and has the git and preview integrations I am looking for.
Vercel came in second, but I had no need for any of the extra features it offered over Cloudflare Pages.
To me, it seems like Cloudflare Pages is built especially for static websites, and you rarely run into issues when you fit the
target demographic perfectly.

## Blast off

Getting the site deployed on Cloudflare pages could probably have not been any easier:

1. Connected Cloudflare to my GitHub account and gave it permissions on my website repository
2. Initialized a new Cloudflare Pages project for the repository
3. Configured the presets to `astro` and clicked deploy
4. Profit???

Even better, since Cloudflare already manages all of my domains (RIP Google Domains), getting it setup was as simple as selecting
the configure button, entering in my domain, and clicking OK to update DNS records.
A short bit later and the website is up and running, with SSL already handled for me.
Thanks Cloudflare!

## Fin

For what was perhaps no more than two hours of actual work (not counting research), I went from nothing to a custom portfolio
website being hosted on a blazing fast CDN.
Due to the git integration, deployments are as trivial as pushing a new commit to the default branch.
Overall, I am very satisfied where I've landed, and I look forward to seeing how easy things are to maintain.