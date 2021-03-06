---
title: Settings, Tips, Tricks and More
---


## How To Fetch New Template Packages?

Using the `install` command lets you fetch (install) new templates. Example:

```
$ slideshow install s6blank
```

or

```
$ slideshow install https://raw.github.com/slideshow-templates/slideshow-s6-blank/master/s6blank.txt
```

Resulting in:

```
Fetching template pack 's6blank'
    from 'https://raw.github.com:443/slideshow-templates/slideshow-s6-blank/master'
    saving to '~/.slideshow/templates/s6blank'
  Downloading manifest 's6blank.txt'...
  Downloading file 'slides.html'...
  Downloading file 'style.css'...
  Downloading file 's6/projection.css'...
  Downloading file 's6/screen.css'...
  Downloading file 's6/print.css'...
  Downloading file 's6/jquery.js'...
  Downloading file 's6/jquery.microsoft.js'...
  Downloading file 's6/jquery.slideshow.js'...
  Downloading file 'slides.pdf.html'...
Done.
```

Note, if you want to store the template pack somewhere else
use the `-c/--config` option (defaults to `~/.slideshow`).

To find more templates browse the [Template Gallery](https://github.com/slideshow-templates).



### Troubleshooting

Trouble downloading? Do you have a direct internet connection?
If not, configure your proxy using the HTTP_PROXY environment variable. Sample:

```
HTTP_PROXY=http://234.445.454:4341
```

Or with user credentials (that is, login and password):

```
HTTP_PROXY=http://gerald:topsecret@234.445.454:4341
```

If all fails, you can always download the template pack on your own
(using lets say `git` itself) and than move the souces into your
templates folder (that is, `~/.slideshow/templates`).



## How To Fetch New Template Packs Using `git`?

If you prefer you can fetch template packs using `git` itself in two steps

Step 1: Change to your templates folder

Issue the command:

```
cd ~/.slideshow/templates
```

Step 2: Clone (Fetch) the template pack using `git`

Let's clone the reveal.js template pack. Issue the command:

```
git clone http://github.com/slideshow-templates/slideshow-reveal.js.git
```

That's it. Use the `list` command to list all installed template packs.


## How To List All Installed Template Packages?

Using the `list` command lets you list all installed templates. Example:

```
$ slideshow list
```

or

```
$ slideshow ls
```

Resulting in:

```
Installed template packs in search path
    [1] templates/*.txt
    [2] templates/*/*.txt
    [3] node_modules/*/*.txt
    [4] ~/.slideshow/templates/*.txt
    [5] ~/.slideshow/templates/*/*.txt
  include:
       reveal.js (~/.slideshow/templates/reveal.js/reveal.js.txt)
         s6blank (~/.slideshow/templates/s6blank/s6blank.txt)
```


## How To Use Your Own Slide Show Template Packages?

Fetch a sample template pack from the internet or clone it using `git` or create
it from scratch.
See the [Template Gallery](https://github.com/slideshow-templates) for more info and samples to get started.

To use your own template pack use the `-t/--template MANIFEST` option
passing along the manifest. Example:

```
$ slideshow build microformats.text -t s6blank
$ slideshow build microformats.text -t reveal.js
```

Got templates? Send a link and announcement to the
[wwwmake forum/mailing List](http://groups.google.com/group/wwwmake)
and get added to the [Template Gallery](https://github.com/slideshow-templates).


## How To Create Slides Without Titles?

You can use the `!SLIDE` directive to create slides without headings.
Example:

```
!SLIDE

A slide with no title

!SLIDE

Another slide with no heading

!SLIDE

And another

!SLIDE commandline

    $ ruby print.rb

!SLIDE image

!i/friendsbadge.png!
```

Note, you can pass along CSS style classes to your generated `div`
or `section` that wraps your slide. Example:

```
!SLIDE smaller commandline
```

Will become:

```
<div class='slide smaller commandline'>
  ...
</div>
```


## How To Use Gradient Background Themes for the Built-In S6 Template Pack?

You can define your gradient background theme in plain text in the slide show source in the header
using a simple CSS-style name value pair. [More »](#how-to-use-gradient-background-themes-for-the-built-in-s6-template-pack)


## How To Generate PDF Documents from Your Slide Shows?

When you generate your slide show as usual with the built-in S6 template pack
you will get an extra `<your_name_here>.pdf.html` document generated that
you can use to generate a PDF-version of your slide show
using lets say the free, open source [`wkhtmltopdf`](http://code.google.com/p/wkhtmltopdf/) tool.

Example:

```
$ slideshow build tutorial.text

$ wkhtmltopdf --outline --orientation Landscape tutorial.pdf.html tutorial.pdf
```


## How To Comment Out Content?

Use `%` for comments anywhere (including headers) and `%begin`/`%end`
for multi-line comments and `%end` to skip everything until the end.

```
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%  Start off with some headers

title: 10 Things Every Java Programmer Should Know About Ruby
author: Jim Weirich

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%  Let's go. The presentation starts here

# 10 Things Every Java Programmer Should Know About Ruby

Jim Weirich
```

See [10 Things Every Java Programmer Should Know About Ruby](http://raw.github.com/slideshow-s9/samples/master/10things.md)
sample.

Note, as an alternative syntax to skip (comment out)
content in your source enclose it with  `__SKIP__`/`__END__`. Example:

```
__SKIP__
  not yet ready or private notes/comments
__END__
```

As a shortcut if you just use `__END__` (without `__SKIP__`) (Ruby-like)
it will skip everything from `__END__` until the end of the file.
