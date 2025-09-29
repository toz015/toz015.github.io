---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
{% for education in site.data.cv.education %}
* **{{ education.area }}** - {{ education.institution }}
  * {{ education.startDate | date: "%B %Y" }}{% if education.endDate and education.endDate != "current" %} - {{ education.endDate | date: "%B %Y" }}{% elsif education.endDate == "current" %} - Present{% endif %}
{% if education.courses %}
  * Courses: {{ education.courses | join: ", " }}
{% endif %}
{% endfor %}

Work experience
======
{% for work in site.data.cv.work %}
**{{ work.position }}** at **{{ work.company }}**  
{{ work.startDate | date: "%B %Y" }}{% if work.endDate %} - {{ work.endDate | date: "%B %Y" }}{% else %} - Present{% endif %}
{% if work.highlights %}
{% for highlight in work.highlights %}
* {{ highlight }}
{% endfor %}
{% endif %}

{% endfor %}
Skills
======
{% for skill in site.data.cv.skills %}
* {{ skill.name }}: {{ skill.keywords | join: ", " }}
{% endfor %}

Publications
======
{% for publication in site.data.cv.publications %}
* **{{ publication.name }}**  
  * {{ publication.publisher }}, {{ publication.releaseDate | date: "%B %Y" }}
  {% if publication.website %}
  * [Link]({{ publication.website }})
  {% endif %}
  {% if publication.summary %}
  * {{ publication.summary }}
  {% endif %}

{% endfor %}
  
<!-- Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul> -->
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
