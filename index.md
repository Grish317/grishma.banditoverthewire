Bandit overthewrire walkthrough
<ul>
  {% assign sorted_posts = site.posts | sort: 'path' %}
  {% for post in sorted_posts %}
    <li>
      <a href="{{ post.url }}">{{ post.path | split: '/' | last | replace: '.md', '' }}</a>
    </li>
  {% endfor %}
</ul>

