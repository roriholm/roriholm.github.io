---
layout: post
title:  "Code example"
date:   2019-01-01
---

I thought it would be fun to make a "video roulette" every time you load my site.

When you go to embed a YouTube video, they give you code that looks like this:

~~~~
  <iframe width="200" src="https://www.youtube.com/embed/aq76zcJfUGc" showinfo="0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
~~~~

The obvious solution would be to save a big list of these, and select one at random when the page loads. But that's an ugly list for me to maintain! Notice that the contents will be the same for every video, except for its unique ID.

So the nicer solution is to include a helper function:

~~~~
  function embed(id) {
    return("<iframe..." + id + "...</iframe>");
  }
~~~~

Now I can just maintain a list of video IDs, and generate the embedding code. I decided to be a little fancier and include the title, so I need a list of lists:

~~~~
musicChoices = [["Christian Vander - Les Oiseaux en Colere", "Ci6oi2Kv_2Y"],
 ["Magma - Otis", "GNkWac-Nm0A"],
 ["Popol Vuh - Aguirre", "zdeIN3sYcfk"]]
~~~~

Now when I want to make my choice, it basically looks like:

~~~~
[title, id] = musicChoices.randomElement();
embeddingCode = title + ": " + embed(id);
~~~~

Piece of cake! It's super basic but gives me that warm, fuzzy feeling.
