---
layout: page
title: "Software Development Guidelines"
description: ""
---
{% include JB/setup %}

These are the guidelines I use to write software.
They are not universal guidelines.

1.  **When creating libraries (eg Ruby gems),
avoid objects as much as possible and create functions.**
Functions are easier to test. OOP should be used when you 
need state. Functions are more than enough when you need 
functionality.

2.  **Writing apps takes time and is harder than you think.**
If Jamis Buck can't continue Capistrano development, 
why should you roll your own?

3.  **Close to the metal, abstractions, and alternatives.**
Bad abstractions: NoSQL doc-to-object mappings). Abstractions 
work when you want to comply with an existing protocol, 
extend/implement/standardize the protocol, or hide certain 
functionality that no one cares about. HTTP web servers 
are an example of this. Abstractions do not work when you try 
to take away from the protocol/standard. Java desktop apps
take away underlying functionality of the OS. They create 
something just as mediocre as the underlying system, but 
even more restricted and confusing. Squeak, however, is an
example of an alternative to the OS, rather than an 
abstraction of it. Squeak knows when to use an abstraction 
and when to offer an alternative.

4. Error checking frameworks:  I avoid them. I have written
several and I had to throw them all out.  They make development
harder. They make understanding the architecture/essence of
the app even harder.  In the end, I found that having a 
predictable, easy-to-learn design with few lines of code
is better than creating error checking frameworks, no matter
how simple the error checking DSL is. 
Even in the future 
when [code is better visualized](http://vimeo.com/36579366), 
the easiest way to debug is have fewer calls and an easy to
understand design. This is hard to do because it requires
changing working code to be easier to understand, rather than more
efficient.  IN OTHER WORDS: 
[write confident code](http://confreaks.com/videos/763-rubymidwest2011-confident-code).
