---
layout: default
title: home
---
# thinking out loud
I sync this site with a portion of my personal notes to share with others. This includes instructional posts, research or WIP thinking, usually around making digital creative work.

You can find my main site over at <a href="https://rory.green">rory.green</a>.

## recent notes

 <ul>
        {%- for post in collections.all reversed limit:10 -%}
          <li><a href="{{ post.url }}">{{ post.data.title }}</a></li>
        {%- endfor -%}
        </ul>