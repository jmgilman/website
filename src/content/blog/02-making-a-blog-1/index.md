---
title: "Making a Portfolio Pt 1"
summary: "Join me in the journey of setting up this portfolio and blog."
date: "Sep 28 2024"
draft: false
tags:
- Web
- Journey
---
Today I started the journey of setting up my own portfolio website and blog.
What better way to kick the tires on it than write about the process of making it?
So, for my first journey, I'm going to be writing about the process of setting up this website.

## Requirements

I had a few requirements going into this journey:

- The underlying technical stack must prioritize OSS as much as possible
- There should be a low barrier to writing
- The stack should minimize having to write HTML/CSS/Javascript
- The content shouldn't be tied to a specific vendor (data sovereignty)

Being an avid consumer of all things technology, it was pretty obvious from the beginning that a static site generator checks all
of those boxes.
However, that's the _easy_ part.
Which, of the dozens, of generators should I use?
This is where things got more complicated.

## Generators Galore

At the time of this writing, there's certainly no shortage of static site generators.
Don't believe me?
[Take a look](https://github.com/myles/awesome-static-generators).
Given their popularity, I expect to only see the number increase over the next few years.

After seeing the state of things, I started filtering down a bit more.
First, I wanted something with an existing ecosystem of templates, components, etc.
This is primarily because I do not enjoy writing HTML, CSS, or Javascript.
In fact, I have practically zero artistic flair and generally lack the patience to make something that is visually pleasing (unless
said thing is code!).
This immediately limited the contenders to the following:

- [Astro](https://astro.build/)
- [Gatsby](https://www.gatsbyjs.com/)
- [Hugo](https://gohugo.io/)
- [Jekyll](https://jekyllrb.com/)

These four names consistently showed up in search results, Reddit, Stack Overflow, etc.
After independent investigation, they each also have a fairly mature ecosystem of existing examples/designs (with Astro seemingly
being the newest).

## Testing the Waters

From this point, I performed a simple exercise of going to the documentation for each one and trying out whatever tutorials were
offered.
I didn't find a huge variance in quality/content, but I think the winner was Astro due to it building something relevant (a blog no
less!) and the depth that it went into.
It was a little "flashy" for a tutorial, but they also make a dedicated framework for documentation, so I guess they have a reason
to show off.

As for experience, Astro was also the clear winner here.
I'm pretty ignorant of what's happened in the frontend space for the last ten or so years, so a lot of features from all four
frameworks were new to me.
However, Astro seeemd to be the one that decided to just make integrating _all_ of it as easy as possible.
What I mean to say is that, from my limited understanding, you could basically bring any UI library you want into it.
In fact, they even proudly advertise this on their front page along with actual examples of doing it.

For someone who is new to this space, I really liked the idea of having a choice, especially since I haven't really had the time to
form an opinion on any of these frameworks yet.
Astro provides an opportunity for me to experiment with several new technologies (if I so choose) and to do so relatively pain-free.

Finally, despite my wariness of DSLs, I really ended up liking the `.astro` files.
It sort of feels like a JS-infused markdown file, except the front matter is Javascript and the content is HTML.
The feel of importing some styles/components at the top, maybe doing a bit of logic to populate some variables, and then using a
simple templating language to generate the content felt really nice.
Even a front-end novice like myself was able to understand and start using it almost immediately.

So, at the end of the day, I decided Astro would be where I started.

## Don't Reinvent the Wheel

As mentioned in the first section I have no desire to design my portfolio from scratch.
It would end up taking me weeks before I'd even write my first blog post and that doesn't align with my priorities.
Luckily, Astro ships with a wonderful little library of [ready-made templates](https://astro.build/themes/).

When it comes to templates, I don't mind spending money.
The same principle drives me to support OSS projects when I can.
However, I did start with the goal of making this setup as "free" as possible, so I decided to stick with non-paid templates.

Fortunate for me, though, it didn't take too long to stumble across [astro-sphere](https://github.com/markhorn-dev/astro-sphere)
template.
It managed to check all of the boxes I was looking for:

- Free
- Geared towards a personal portfolio
- Included a blog
- Had support for tags (important for finding things later)

Visually, it was superior than most of the other options.
I tend to be more of a minimalist, but I don't mind a little bit of flair, and I think this template landed somewhere in the middle.

## Customizing

After going through the Astro tutorial, understanding how the template was built took a surprisingly short amount of time.
In fact, since Astro is a bit opinionated about how projects should be organized, I was able to orient myself fairly quickly.
I knew what components were and how they were being used.
I understood the value of layouts and, as expected, they were being used in areas like the overall page structure, header, and
footer.
All of the "dynamic" pages were straight-forward to understand: primarily just looping through and displaying elements.

Luckily, the template author did a great job of keeping the markdown content mostly separate from the dynamic stuff.
I made very few changes to the astro files and most of them were just minor visual tweaks (for example, I don't need a ToS for my
personal portfolio).
My editor of choice (VSCode) even has a specialized plugin for `.astro` files that made the whole experience even more pleasant.

The hardest part of the whole process was actually creating the little "branding" icon you see next to the site name at the top and
bottom of the page.
I shamelessly used AI to create something passable and then had to go about vectorizing it (which is still a bit painful to get
it looking right).
Other than that, everything was fairly straightforward.

## Moving On

Now that I have a customized template and I'm armed with the knowledge to break things, the next step is actually getting this
thing built and deployed.
It is a static site _generator_ after all.
And, of course, I can't possibly do any of this manually.
That would be horrible.

So in the next post, I'm going to work on selecting a hosting provider and automating the build/deployment process.
Stay tuned!