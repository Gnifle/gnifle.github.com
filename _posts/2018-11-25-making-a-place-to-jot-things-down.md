---
layout: post
title: Making a place to jot things down
categories: [Learnings]
tags: [blog, jekyll, github, github pages]
fullview: false
comments: true
---

Finally! I took some time out, to do some of my own hobby projects, that I
promised myself I would get done one day. I had a bunch of sparetime going
on a family trip by train, an with a bit of preliminary looking into how big
of a task this should be, I stuck some
[_Darker Days_](https://open.spotify.com/album/5K2iwLVDEjF19yoW5MkRl6) by
[Peter, Bjorn and John](https://open.spotify.com/artist/6u11Qbko2N2hP4lTBYjX86)
(great, newly released album - highly recommend it) in my ears and delved in.

What I ended up doing, was following through on creating a simple blog for
myself. Not necessarily for the purpose of giving someone else something super
interesting to read, but more for the sake of documenting my own learnings for
future reference. A little backstory:

The other day at the office, I walked in on two of my colleagues having a talk
about past and personal projects. One of said colleagues, Jacob, happened to
have [a personal blog](http://www.emcken.dk) for his own scribbles. While he
wasn't currently writing to it actively, he did use it occasionally for when he
had a stroke of a good idea. He explained that it was a static generated blog
using GitHub Pages. Curious, I asked into a bit more detail as to how such a
blog works, and he shipped me a couple links on the chat.

## My introduction to GitHub Pages

Jacob mentioned a couple of key-points, that I found super interesting:

- Making the site statically generated
- Using a custom domain
- Writing articles using plain markdown

This sounded like exactly what I'd hoped to accomplish someday myself. Sure, I
could throw a quick WordPress installation together, apply a minimalistic theme
and call it a day. But from my past work and experience with WordPress, it's
just never that simple. Flashback to my times of having customers complaining
about the smallest of issues on their WordPress blogs and webshops. Ugh...

It took me 3 minutes of reading to sell me on
[GitHub pages](https://pages.github.com/). Wow, how had I never come across
these before? Intrigued, I kept reading until I figured I had the grasp of the
basic idea. Seemed super simple to get started:

1. Create new GitHub repo named `gnifle.github.io`. **Childs play.**
2. Clone the repo **Programming is so easy, dude**
3. Start writing articles. **Great, easy-peasy, let's go!**

That's it in short. I was online on
[blog.gnifle.com](http://blog.gnifle.com). Well, that was simple.

## A generated static blog of... Nothing

Man, was I stoked. You ever have those moments, where you feel like the god of
the programming world? Well, that was one of those moments. That was right until
I got to the next question. *What now?*

Well, I guess the page is static, but it doesn't have any content, and it
really looks, well, plain. Literally, all I had was a page with contents of the
demo README.md file, nothing else. So as I scrolled down further on the
[getting started pages](https://pages.github.com/), a CTA button with the words
*"Blogging with Jekyll"* came up. And suddenly it hit me, that I had just
scratched the tip of the iceberg. I didn't have a blog *yet*, I only had one
static HTML page with no content, no nothing.

For some reason, I had assumed that GitHub pages took care of all the
staticifying (that's a word now!) of my blog. Well, turns out it *can*, but not
without instructions. Silly computers, further proof AI is still waaaay off in
the future. Anyhow, I digress.

As soon as I start looking up Jekyll, I realized I was in for a much longer ride
than first anticipated. But I was having fun, and I was determined to get just
about anything going, in a way I could scale *somehow*.

## And thus, my journey into Jekyll was underway

I followed the
[step-by-step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) on
Jekyll's website. So far so good, I already had all the prerequisites installed
on my machine, so I was good to go. Going
[one step further in](https://jekyllrb.com/docs/step-by-step/02-liquid/), and I
spot something quite familiar, as *Liquid* is oddly familiar to *Twig* as a
templating engine, which I've used before in Drupal 8.
[Front Matter](https://jekyllrb.com/docs/step-by-step/03-front-matter/) seems
easy and
[layouts and includes](https://jekyllrb.com/docs/step-by-step/04-layouts/) is
something I've seen a lot with *Blade* from Laravel development. Alright, I
could get that working, but I still needed som layout. And that's when I
realized I was about to start all over again.

The thing with WordPress, at least with standard compliant themes, is that you
can just activate a theme and thus deactivate another, and you're set on a new
design. Since Jekyll uses somewhat hardcoded variables, installing a theme isn't
just plug-and-play. I mean, it's somewhat close, but the problem comes if you
have existing content, where the files needs migration to some degree. For me,
well, I got luck and could just pull a theme and replace my current installation
before adding any content. I ended up with a theme called
[*dbyll*](https://github.com/dbtek/dbyll).

And there we go, I finally have a functional statically generated blog! Swell!

## Appying a custom domain

Seriously, big kudos to GitHub and their pages system. As simple a URL as
[http://gnifle.github.io](http://gnifle.github.io) is pretty awesome out of the
box. But seeing as I already own my wn domain, [gnifle.com](http://gnifle.com),
I'd really like to use that.

Turns out, this is super easy to setup:

- Add a file simply called `CNAME` to the root level of the project, and paste
  the URL you want to use. Nothing else.
- Add a CNAME record in my hosts' DNS settings to the URL i want
  In this case, I wanted to use a subdomain,
  [blog.gnifle.com](http://blog.gnifle.com).

That's it, commit and push the `CNAME` file, and it just works. We're now live
on [blog.gnifle.com](http://blog.gnifle.com). Write an article (litterally, as
I'm writing these words right here) and push it, and we have officialy started
my blog. A couple design changes, to fit my needs, and I'm happy as can be.

## Some final configuration and thoughts

While toying around with Jekyll, I did make some configuration changes as well,
along with stumbling into some further reading.

### Permalinks and SEO

While SEO isn't my main focus for this blog by any means, putting some thought
into scaling isn't really a bad thing for future reference, aye? So I looked up
some articles on how I should set up my article permalinks. Turns out there's
tons of information on such things out there:

- [https://www.digitalocean.com/community/tutorials/controlling-urls-and-links-in-jekyll](https://www.digitalocean.com/community/tutorials/controlling-urls-and-links-in-jekyll)
- [https://moz.com/blog/dynamic-urls-vs-static-urls-the-best-practice-for-seo-is-still-clear](https://moz.com/blog/dynamic-urls-vs-static-urls-the-best-practice-for-seo-is-still-clear)
- [https://neilpatel.com/blog/complete-guide-structuring-urls/](https://neilpatel.com/blog/complete-guide-structuring-urls/)

While the conclusions of said articles weren't all the same, I did manage to
make an assessment of how I wanted to go about it. I ended up with a permalink
template of `/:categories/:title:output_ext` which I added to my `_config.yml`
file.

Particularly,
[this section](https://jekyllrb.com/docs/liquid/tags/#linking-to-posts), of the
Jekyll documentation about linking internally to other posts, could prove very
useful. Essentially, just use the Liquid syntax and give it a file name
(without extension) like so:

{% highlight php %}
{% raw %}
{{ site.baseurl }}{% post_url YYYY-MM-DD-raw-post-file-name-without-extension %}
{% endraw %}
{% endhighlight %}

### Tags and categories

I also had to brush up on how to
[properly use categories and tags](https://www.elegantthemes.com/blog/tips-tricks/best-practices-for-using-categories-and-tags-in-wordpress),
since I have barely done any content work for 14 months. Didn't take too long
though, so I felt pretty confortable going forward with this.

### Disqus integration

Disqus integrates extremely easy with Jekyll, so setting it up was a breeze. It
just worked on the first try, whaddaya know?!

I went to my Disqus account, added a new site through their admin panel, copied
and pasted the site-identifier into my `_config.yml` file, and the comment
integration just started working. While I usually prefer to avoid third-party
plugins like Disqus (I'm a roll-your-own kind of guy when it comes to stuff
like this), having something work so seemlessly on the first go was rather
convincing. So I'll give it a spin on here just for the sake of trying it.

### Code highlighting (rouge configuration)

Jekyll comes built-in with Rouge for code highlighting. I wanted to use the
Monokai theme. So I simply downloaded the corresponding CSS file from
[pygments-css on GitHub](https://github.com/richleland/pygments-css) and
imported it in my CSS file for the theme. Done deal.

### List of smaller pages and tutorials that helped during setup

- [https://github.com/jacobemcken/jacobemcken.github.io](https://github.com/jacobemcken/jacobemcken.github.io)
- [https://tosbourn.com/liquid-raw-syntax/](https://tosbourn.com/liquid-raw-syntax/)
- [https://www.searchenginenews.com/sample/content/should-i-remove-the-dates-in-my-blog-urls-yes](https://www.searchenginenews.com/sample/content/should-i-remove-the-dates-in-my-blog-urls-yes)
