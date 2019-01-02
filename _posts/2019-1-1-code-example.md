---
layout: post
title:  "Code example"
date:   2019-01-01
---

~~~~
  function embed(id) {
    var s = '<iframe width="200" src="https://www.youtube.com/embed/';
    s = s + id + '" showinfo="0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>';
    return(s);
  }
~~~~