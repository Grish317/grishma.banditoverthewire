#bandit overthewrire walkthrough
<ul>
  {% assign sorted_posts = site.posts | sort: 'title' %}
  {% for post in sorted_posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %d, %Y" }}
    </li>
  {% endfor %}
</ul>

