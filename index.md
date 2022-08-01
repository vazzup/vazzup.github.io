---
title: Home
layout: default_noimg_homepage
---

<h1 id="web3-blog">
  <button type="button" class="collapsible active" data-target-plus="web3-plus" data-target-collapse="web3-content" style="font-size:inherit;font-family:inherit;font-weight:inherit;">
    <div style="display:inline-block;float:left;">Web3 Blogs</div>
    <div style="display:inline-block;float:right;" id="web3-plus">-</div>
  </button>
</h1>
<div class="content-default" id="web3-content" style="display:block;">
  <h2 id="recent-posts">Recent Posts</h2>
  <ul>
    {% assign t = 'web3' %}
    {% for post in site.posts limit:10 %}
    {% if post.tags contains t %}
    <li> <a href="{{ post.url }}">{{ post.title }}</a> </li>
    {% endif %}
    {% endfor %}
  </ul>
  <a href="web3.html">Read all Web3 Blogs</a>
</div>
<div></div><br>
<h1 id="blog">
  <button type="button" class="collapsible" data-target-plus="misc-plus" data-target-collapse="misc-content" style="font-size:inherit;font-family:inherit;font-weight:inherit;">
    <div style="display:inline-block;float:left;">Miscellaneous Blogs</div>
    <div style="display:inline-block;float:right;" id="misc-plus">+</div>
  </button>
</h1>
<div class="content" id="misc-content">
  <h2 id="recent-posts">Recent Posts</h2>
  <ul>
    {% assign t2 = 'misc' %}
    {% for post in site.posts limit:10 %}
    {% if post.tags contains t2 %}
    <li> <a href="{{ post.url }}">{{ post.title }}</a> </li>
    {% endif %}
    {% endfor %}
  </ul>
  <a href="blog.html">Read all Other Blogs</a>
</div>

<div style="width:100%; height:auto; margin-top:1rem; margin-bottom:1rem">
  <center>
    <a href="https://vazzup.substack.com">
      <button style="font-size:14px; padding: 0 12px; height:40px;
        border: 0px; border-radius: 4px; background-color:#121bfa;
        color:#fff; text-decoration: none!important; display:inline-block;">
        Subscribe to my Newsletter!
      </button>
    </a>
  </center>
</div>

# What's all this then?
---
I write about my personal experiences in the venture capital world, Web3, Emerging Techologies,
past experiences from engineering school, movies, books, art, economics, finance, and in general anything
and everything I find interesting.

I am currently the Principal and CTO of [100X.VC](https://100x.vc), a new India focused venture fund looking to be the
launching pad for the next 500 moonshots coming out of India. I'm also Web3 Investor at [2AM VC](www.2amvc.com) and
partner at my Family Office [Mehta Ventures](https://mehtaventures.co)

Pitch to 100X.VC at [100x.vc/class08](https://100x.vc/class08). Want to talk to me
about something? Write to me at [vatsal@100x.vc](mailto:vatsal@100x.vc)

<!-- Planned posts [VatsalBaba Speaks - An Introduction]()
* [VatsalBaba Speaks - ACM ICPC and Competitive Programming]()
* [VatsalBaba Speaks - Srujana Center for Innovation or How I Got Lucky Part 1]()
* [VatsalBaba Speaks - Morgan Stanley or How I Got Lucky Part 1]()
* [VatsalBaba Speaks - Exploring Other Fields (Machine Learning)]()
* [VatsalBaba Speaks - Exploring Other Fields (Robotics)]()
* [VatsalBaba Speaks - Exploring Other Fields (FinTech)]()
* [VatsalBaba Speaks - The definitive guide to surviving KTs]()    -->

<!-- # More About Me
---
> "... medicine, law, business, engineering, these are noble pursuits and necessary to sustain life. But poetry, beauty,
> romance, love, these are what we stay alive for."   
> \- Robin Williams, Dead Poets Society

Apart from my work, I'm a huge literature, music and movie buff. On the big screen, I love the works of Woody
Allen, Quentin Tarantino, Cristopher Nolan and Wes Anderson. I particularly love the works of Wes Anderson, not least
due to the color and symmetry in his work. In literature I have a long list of fiction and non fiction writers I adore.
One I must mention here is Douglas Adams for his philosophical satire "The HitchHiker's Guide to the galaxy." I aspire
to write poems as raw as Robert Frost's.  Lastly, in the music department, I wonder at the genius that are the artists
Pink Floyd, Radiohead, Nirvana, Steven Wilson, A. R. Rahman, Miles Davis, Dave Brubeck, Chopin and Debussy to name a few. -->
