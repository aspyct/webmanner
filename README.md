What is it?
-----------

Yet another manpage to html converter, built and tested on OSX.

**Although webmanner works under Linux, it does not recognize formatting yet. I'll fix that as soon as possible.**

How to use?
-----------

Call it just like you would call the man, and redirect `stdout` to a file.

```bash
webmanner 2 read > read.2.html

# Or omit the section
webmanner read > read.1.html
```

**Options**

```
Usage: webmanner [[<section>] <title>]
  -j, --js PATH        Add a <script> tag with given PATH as source
  -s, --style PATH     Add a <link rel='stylesheet'> tag with given PATH as href
  -t, --tab-width NUM  Set the number of whitespaces for html indentation
  -l, --linux          Force webmanner to operate under linux
  -u, --unstyled       Remove default css styling
  -p PATTERN,          Page title pattern (ex: '%{page} | my online man)'
      --title-pattern
  -h, --header HTML    HTML to be put into header
```

Where to get the latest version?
--------------------------------

Code is and will always be available on the github repository:
https://github.com/aspyct/webmanner

License
-------

MIT, feel free to use for open source & commercial projects, but be kind and mention me ;)

Contact / More info
-------------------

Name's Antoine :)

- Website: http://www.aspyct.org
- Mail: a.dotreppe@aspyct.org
- Twitter: @aspyct
