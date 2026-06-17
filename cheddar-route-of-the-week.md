---
title: Cheddar Route of the Week
permalink: /cheddar-route-of-the-week/
layout: page
comments: false
---

{%- comment -%}
  Pick a route based on the current week number so it advances once a week.
  epoch seconds / seconds-in-a-week gives a week counter that increments every
  7 days; modulo the list length rotates through every route in turn.
{%- endcomment -%}
{%- assign routes = site.data.cheddar_routes.routes -%}
{%- assign epoch = site.time | date: "%s" | plus: 0 -%}
{%- assign week_number = epoch | divided_by: 604800 -%}
{%- assign index = week_number | modulo: routes.size -%}
{%- assign route = routes[index] -%}

This week's pick, hand drawn from local cheddar wad Alban's **[Road to gunfigher list](https://www.ukclimbing.com/logbook/ticklists/road_to_gunfighter-9649)**(week {{ week_number | modulo: 52 | plus: 1 }}):

## {{ route.name }}

- **Grade:** {{ route.grade }}
- **Stars:** {% for i in (1..route.stars) %}★{% endfor %}{% if route.stars == 0 %}—{% endif %} ({{ route.stars }}/3)
- **Side:** {{ route.side }} wall
- **Length:** {% if route.length %}{{ route.length }}{% else %}not recorded{% endif %}
- **Logbook ascents:** {{ route.ascents }}

{% if route.your_note and route.your_note != "" -%}
> {{ route.your_note }}
{%- else -%}
*No club note for this one yet — add yours by pull requesting into `_data/cheddar_routes.yml`.*
{%- endif %}

---

A fresh route chosen each week.

Please do check the access before going to climb, make sure you're a BMC member, make sure to vape in the car parks and rev your car really loudly etc etc **[Cheddar access guide](https://www.martincrockerclimbing.com/cheddar-gorge)**.
