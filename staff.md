---
layout: page
title: Staff
nav_order: 6
description: A listing of all the course staff members.
---

# Staff

Jump to [Instructors](#inst), [Teaching Assistants](#tas), or [Tutors](#tutors)

**Note:** Consult the [calendar]({{ site.baseurl }}/calendar) for the most up-to-date office hours for each GSI.

<a name = 'inst'></a>

## Instructors

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
<div class="role">
  {% for staffer in instructors %}
  {{ staffer }}
  {% endfor %}

</div>

<a name = 'tas'></a>

## Teaching Assistants

{% assign teaching_assistants = site.staffers | where: 'role', 'Teaching Assistant' %}
<div class="role">
  {% for staffer in teaching_assistants %}
  {{ staffer }}
  {% endfor %}
</div>

<!-- <a name = 'tutors'></a>

## Tutors

<div class="role">
  {% assign readers = site.staffers | where: 'role', 'Tutor' %}
  {% for staffer in readers %}
  {{ staffer }}
  {% endfor %} -->
<!-- </div> -->
