---
Date: 2014-01-19 13:00 AM
title: Hello World Everybody! This Is a Test.
source: http://www.baidu.com/
layout: post
category: tips 
orcategory: [reviews]
tweet: Never look up a date format string again!
---

Toyota is known for their manufacturing process. People have [studied] [1].

[Steve Smith](http://www.orderedlist.com/) gave a great talk at [Great Lakes Ruby Bash](http://www.greatlakesrubybash.com/) on designing code.

My favorite quote from the article:

> My conclusion after the trip was "well, now I know that there's at least one company in the world that can succeed with the waterfall model" and I decided to stop bashing the waterfall model as hard as I usually do. 

> There are two other ways to get out of insert mode:
> 
> Ctrl-\[
> 
> and
> 
> Ctrl-C

> 1. Increase the value created
> 2. Decrease the time required to create that value
>
> [- <cite>What is productivity?</cite>][source]

I use Ctrl-C to exit insert mode. One thing I discovered is that Ctrl-C cancels any pending edits. 90% of the time this is not a problem for me. However, for that last 10%, I've added this to my `.vimrc`:

{% highlight vim %}
    inoremap <C-c> <ESC>
{% endhighlight %}


- [Notes on HTML5 Video and iPhone (Jonathan Stark)] [2]


{% highlight ruby %}
    require 'shopify_api'

    watch('(?:templates|layout|assets)/.*\.liquid') do |match|
      puts "Updating %s..." % [match[0].inspect]
      upload_template(match.to_s)
    end

    def upload_template(file)
      ShopifyAPI::Base.site =
        "http://{key}:{secret}@{domain}.myshopify.com/admin/"
      asset = ShopifyAPI::Asset.find(file)
      asset.value = File.read(file)
      asset.save
    end
{% endhighlight %}

(See <https://gist.github.com/787359> for the latest version of this script).

{% highlight vim %}
    <C-O>:set paste<CR><C-r>*<C-O>:set nopaste<CR>
{% endhighlight %}

And then mapped it to `<Leader>v` in insert mode:

{% highlight vim %}
    imap <Leader>v  <C-O>:set paste<CR><C-r>*<C-O>:set nopaste<CR>
{% endhighlight %}

N.B. this command only works in Vim 7.3 or later. It's written for insert mode, but it shouldn't be hard to create a normal mode command that works in a similar manner.

### Want to know how it works?

That should give you a good excuse to get familiar with Vim's [`:help`][help] command or [practice Googling][google]. Everything in this command is native, documented Vim. Have fun!

*[N.B.]: Note well

[^1]: Updated to clarify what I mean by "command-line" Vim

### Usage

1. Create a new directory for your Shopify app.

### Caveats

This process is a very bad idea for team development. I do not recommend it if you have multiple developers working on Shopify sites. This is equally bad if you are upgrading an existing site that needs to stay public; in that case, look into setting up a test store and do the work in there. However, if you're the sole coder this is a great way to work.

[1]: http://amzn.to/fyFezV                                   "Toyota Production System: Beyond Large Scale"
[2]: http://jonathanstark.com/blog/2010/02/15/notes-on-html5-video-and-iphone/ "Notes on HTML5 Video and iPhone"
[source]: http://www.stevepavlina.com/blog/2005/10/what-is-productivity/
[help]: http://vimdoc.sourceforge.net/htmldoc/help.html
[google]: http://bit.ly/lnA8oD
[hn]: http://news.ycombinator.com/item?id=2532350

//
<ins datetime="2011-01-15">Update (2011-01-15): Added some caveats to the book</ins>