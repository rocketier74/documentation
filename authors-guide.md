---
layout: default
title: Author's Guide
---
# Author's Guide

## tl;dr: Look at Other Recipes, and Blend In

Look at the source of other recipe pages and follow that page structure.
Start with the [Developer's Guide]({{site.url}}/developers-guide) to get a test version of the cookbook up and running on your machine, and get to work!

## General Guidelines

* Feel free to add new pages, or even chapters.
Just keep them organized. *(See "How to Add a Chapter" below)*
* Don't forget to add your name to the authors page!


## Copyright Issues

Do not post code that is copyrighted by another user, unless you have permission to use that code AND to relicense that code under the [CC BY 3.0]({{site.url}}/license) license.
If you DO have permission and the author would like credit, please add them to the [authors]({{site.url}}/authors) page.


## Tag the page with Jekyll frontmatter

...that's a lot of fancy words that mean "don't forget to put the layout, chapter and page title at the top of the file in a YAML block".
For example, the string interpolation page begins with

{% highlight text %}
---
layout: recipe
title: String Interpolation
chapter: Strings
---
{% endhighlight %}


# Grindy HOWTOs

## How to Add a sub-chapter

Create a new markdown page (or copy the [Recipe Template]({{site.url}}/recipe-template).
The filename should be about the problem, e.g. `finding-last-day-of-the-month.md` or `reversing-arrays.md`.
In your file, start with the following template:

{% highlight text %}
---
layout: recipe
title: Title of The Recipe
---

Your own Text

{% endhighlight %}

## How to Add a Chapter

* Open \_config.yml and add your chapter's name to the yaml list of chapters.
* cd into chapters/ and create the directory for the chapter name.
Downcase the name and replace spaces with underscores.
* add an index.md file that uses `layout: chapter`, `title: Your Title` and 'chapter: Chapter Name'.
Make sure, *Chapter Name* is spelled and written like the chapters name in \_config.yml.

For example, to add a chapter called "Dates and Times", you would add it to the chapters array:

{% highlight yaml %}
chapters:
- Syntax
- Objects
- Arrays
- Dates and Times
{% endhighlight %}

...and then create that chapter in the file system:

{% highlight bash %}
cd chapters
mkdir dates_and_times
{% endhighlight %}

Now create a new page in that chapter (remember to add its YAML front matter) and once jekyll regenerates the chapter index, your new page should appear (after a restart of the server, since we changed \_config.yml).

# FAQ


## What If My Recipe is Inefficient/Too Big/Too Slow?

If it solves a problem to which the alternative is to _not_ solve the problem, share it.
Let the reader decide if they want to use it.
Sometimes we want tight efficient code, other times we want a robust featureset.
If the code has abysmal performance characteristics, be sure to warn the reader in the Discussion.

## Can I Edit An Existing Recipe?

Yes.
Please improve anything and everything! Be sure to test your changes and make sure that your solution really is better.

## I Have a Really Efficient Solution, But It's Not As Readable As the Existing Recipe. Should I Add It?

See the "Weird Recipe" note above.
Do real people in the real world ever hit the performance constraint? If so, then by all means, add your strategy to the existing solution, and be sure to explain why your solution is not idiomatic.
If a reader really has that problem, they'll be glad for the extra options.

## I Have A Problem/Solution, But It's Basically Just JavaScript.
Should I Add It?

Yes! CoffeeScript compiles to JavaScript, and that means that some of its functionality comes straight from JavaScript. (For example, see [Reversing Arrays]({{site.url}}/chapters/arrays/reversing-arrays).) But if you're programming in CoffeeScript and you need to reverse an array, this Cookbook should stand ready to tell you it's available to you in CoffeeScript -- even if it's just a straight call into a JavaScript library.

## I Found a Typo.
Is That Enough of a Fix? Does That Count?

Absolutely!
