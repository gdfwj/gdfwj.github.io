{% assign publications = site.publications | sort: "date" | reverse %}

## Publications & Accepted Papers

{% for post in publications %}
{% if post.status == 'published' or post.status == 'accepted' %}
{% include publication-summary.html %}
{% endif %}
{% endfor %}

## Preprints & Manuscripts

{% for post in publications %}
{% if post.status == 'preprint' or post.status == 'under review' %}
{% include publication-summary.html %}
{% endif %}
{% endfor %}
