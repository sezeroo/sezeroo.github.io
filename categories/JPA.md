layout	title	permalink
page
JPA
/blog/categories/etc/
Posts by Category : {{ page.title }}
{% for post in site.categories.JPA %}
{{ post.date | date_to_string }}   {{ post.title }}
{% endfor %}
