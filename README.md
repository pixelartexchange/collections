
[Feed.HTML @ GitHub](https://github.com/feedhtml)


# Feed.HTML - A Free Feeds Format in HyperText Markup Language (HTML) w/ Structured Meta Data


What's Feed.HTML? Let's start with an example from the Microformats v2 `h-entry` spec:

``` html
<article class="h-entry">
  <h1 class="p-name">Microformats are amazing</h1>
  <p>Published by <a class="p-author h-card" href="http://example.com">W. Developer</a>
     on <time class="dt-published" datetime="2013-06-13 12:00:00">13<sup>th</sup> June 2013</time>
 
  <p class="p-summary">In which I extoll the virtues of using microformats.</p>
 
  <div class="e-content">
    <p>Blah blah blah</p>
  </div>
</article>
```

Let's try to make it simpler and easier. Why in 2017 still (re)use `class` for microformats / microdata? 
Let's use `o` for object types / structs / scopes and `x` for (object) props / property keys:

``` html
<article o=item>
  <h1 x=title>Microformats are amazing</h1>
  <p>Published by <a o=card x=author href="http://example.com">W. Developer</a>
     on <time x=published datetime="2013-06-13 12:00:00">13<sup>th</sup> June 2013</time>
 
  <p x=summary>In which I extoll the virtues of using microformats.</p>
 
  <div x=content>
    <p>Blah blah blah</p>
  </div>
</article>
```

Why `o` and `x`? and not let's say `p` and `q`? The idea is to use letters that are not already used in single-letter tags
and that are easy to remember - think: tic-tac-toe-like ;-)


Parsed to JSON resulting in:

``` json
{
   "title": "Microformats are amazing",
   "author": "W. Developer",
   "card":   { "name": "W. Developer",
               "url":  "http://example.com"
             },
   "published": "2013-06-13 12:00:00",
   "summary": "In which I extoll the virtues of using microformats.",
   "content": "<p>Blah blah blah</p>"
}

```



## License

The Feed.TXT format and conventions are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.

## Questions? Comments?

Send them along to the [wwwmake mailing list/forum](http://groups.google.com/group/wwwmake). Thanks.


<!-- todo: move footer to layouts -->

Brought to you by [feedparser](https://github.com/feedparser) and friends. You might also like [Feed.TXT](http://feedtxt.github.io) ;-).
