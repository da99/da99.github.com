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

