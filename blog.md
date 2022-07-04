---
layout: page
title: "Blog: Unsolicited Advice"
menu: true
order: 4
---

I made mistakes so you don’t have to.

* [Things I Wish I Knew When Starting Chemistry PhD Program](https://docs.google.com/document/d/1T_B5YmAs52YeBspKeGfBGPh5unkrYapsRPP8zREzq1M/edit?usp=sharing)
* [Tips for Renting](https://docs.google.com/document/d/1K3MEFJ1uxn_hDjhiIuaXFFu2ZLr5XVHx/edit?usp=sharing&ouid=103483328524000797617&rtpof=true&sd=true)
* [Grad school questions](https://docs.google.com/document/d/1Z_p19vGFH7bB6NiDVKba-_dlsckL_XICc9MCVGhQwkQ/edit?usp=sharing)

<div class="blog-posts">
        {% for post in site.posts %}

                {% if post.tags.size > 0 %}
                {% capture tags_content %}Tags: {% endcapture %}
                        {% for post_tag in post.tags %}
                                {% assign tag = site.data.tags[post_tag] %}
                                {% if tag %}
                                        {% capture tags_content_temp %}{{ tags_content }}<a href="{{ site.baseurl }}/{{ site.tag_page_dir }}/{{ post_tag | slugify: 'pretty' }}">{{ tag.name }}</a>{% if forloop.last == false %}<span>, </span>{% endif %}{% endcapture %}
                                        {% assign tags_content = tags_content_temp %}
                                {% endif %}
                        {% endfor %}
                {% else %}
                        {% assign tags_content = "" %}
                {% endif %}

                <div class="blog-post spacing">
                        <h3><a href="{{ site.baseurl }}/{{ post.url }}">{{ post.title }}</a></h3>
                        <h5>{{ post.date | date_to_long_string }}</h5>
                        {{ post.excerpt }}
                        <br>
                        <span>{{ tags_content }}</span>
                </div>
                <hr>
        {% endfor %}
</div>

<!-- {% include pagination.html %} -->
