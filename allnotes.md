---
layout: default
title: All notes
---
# All notes

 <ul>
        {%- for post in collections.all reversed -%}
          <li><a href="{{ post.url }}">{{ post.data.title }}</a></li>
        {%- endfor -%}
        </ul>