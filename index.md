# Publicaciones

<ul>
{% for cat in site.categories %}
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <li><a href="{{ category_name }}">{{ category_name }}</a></li>
{% endfor %}
</ul>

{% for post in site.posts %}
  <article>
    <b><a href="{{ post.url }}">{{ post.title }}</a></b> - 
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%d/%m/%Y" }}</time>
  </article>
{% endfor %}