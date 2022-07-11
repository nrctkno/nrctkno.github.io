# Publicaciones

{% for cat in site.categories %}
<ul>
    <a href="{{ post.url }}">
        {{ cat.title }}
    </a>
</ul>
{% endfor %}

{% for post in site.posts %}
  <article>
    <b><a href="{{ post.url }}">{{ post.title }}</a></b> - 
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%d/%m/%Y" }}</time>
  </article>
{% endfor %}