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
* {{ education.area }}, {{ education.institution }}{% if education.endDate %} ({{ education.endDate }}){% endif %}
{% if education.courses %}
  * Courses: {{ education.courses | join: ", " }}
{% endif %}
{% endfor %}

Work experience
======
{% for work in site.data.cv.work %}
* {{ work.startDate | date: "%B %Y" }}{% if work.endDate %} - {{ work.endDate | date: "%B %Y" }}{% else %} - Present{% endif %}: {{ work.position }}
  * {{ work.company }}
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
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
