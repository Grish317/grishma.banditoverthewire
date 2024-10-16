<ul>
  {% assign sorted_pages = site.pages | sort: 'title' %}
  {% for page in sorted_pages %}
    <li><a href="{{ page.url }}">{{ page.title }}</a></li>
  {% endfor %}
</ul>
