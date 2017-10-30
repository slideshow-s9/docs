---
title: Welcome
---

## What's Slide Show (S9)?

A free command line tool that lets you build slide shows
from your notes
written in plain text with markdown formatting conventions.
The Slide Show (S9) project also collects and welcomes themes
and ships "out-of-the-box" with built-in support
for "loss-free" gradient vector graphics backgrounds.


## Getting Started in 1-2-3 Easy Steps

* Step 1: Write your slides in plain text with markdown formatting conventions
* Step 2: Build your slide show using the `slideshow` command line tool
* Step 3: Open up your slide show (web page) in your browser and hit the space bar to flip through your slides
* That's it. Showtime!


### Step 0: Install the `slideshow` command line tool and setup template packs

Use the Ruby package manager, that is, `gem` to install:

```
$ gem install slideshow
```

Use the Slide Show (S9) command line tool to download (fetch) the S6 Blank template pack:

```
$ slideshow install s6blank        # fetch s6 blank template pack
```

To double check what template packs you have installed try:

```
$ slideshow list
```

resulting in:

```

```



### Step 1: Write your slides in plain text with markdown formatting conventions

Slide Show lets you write your slides in plain text with markdown formatting
conventions for headings, emphasis, links, images and more.
Let's write some slides about best practices for web services using REST:

```
# Web Services REST-Style: Universal Identifiers, Formats & Protocols

Agenda

- What's REST?
- Universal Identifiers, Formats & Protocols
- The Holy REST Trinity - Noun, Verbs, Types
- REST Design Principles
- Architecture Astronaut REST Speak


# What's REST?

Representational State Transfer (REST) - Meaningless Acronym? Wordplay?

> rest - n. - peace, ease, or refreshment resulting from the insight that the web works

No matter what vendors tell you - no need to "Light Up the Web" - relax - built on
an **open architecture using universal identifiers, formats & protocols and _evolving_ open standards** -
no need to reinvent the wheel and sign-up for single-vendor offerings.


# What's REST? (Cont'd)

### Narrow Definition

Alternative to BigCo Web Services:

* SOAP
* WS-\*¹ and
* RPC-Style Web Services (XML-RPC)

### Broad Definition

Best Practices for Designing Web Services for a Unified Human and Programable Web

¹: WS-\* =  Web Service Specs including WS-Transfer, WS-Addressing, WS-Eventing,
   WS-Security, WS-Federation, WS-Trust, and many more.
```

Use headings `#` to start a new slide. That's it.
For more formatting options see the Markdown reference.


### Step 2: Build your slide show using the `slideshow` command line tool

Run `slideshow` to build your slide show. The `slideshow` command line tool
expects the name of your source document (e.g. `rest.text`)
and will build a web page
(e.g. [`rest.html`](demos/rest.html)
that is an all-in-one-page handout and a live slide show all at once.

```
$ slideshow build rest.text

=> Preparing slideshow 'rest.html'...
=> Done.
```

### Step 3: Open up your slide show in your browser

Open up your slide show [`rest.html`](demos/rest.html)
in your browser (Firefox, Chrome, Opera, Safari, Edge and others) and hit F11 to switch
into full screen projection and hit the space bar or the right arrow, down arrow
or page down key to flip through your slides.

<a href="demos/rest.html"><img src="i/slideshow.png"></a>

That's it. Voila.

### Bonus: Try some different templates/theme packs

* [S6 PDF Theme](demos/tutorial.pdf.html) -> [PDF](demos/tutorial.pdf)
* [Google HTML5 Slides Theme](demos/packs/g5/tutorial1.html5.html)
* [S5 Blank](demos/packs/s5/tutorial1.html)
* [Slidy W3C Blue Theme](demos/packs/slidy/tutorial1.w3c.html)
* [More »](https://github.com/slideshow-templates)
