---
layout: default
title: "Rezepte"
description: "Schnelle gesunde Rezepte, meist nach Paleo orientiert"
keywords: "Rezepte"
---
- `EL` - Inhalt eines Esslöfels
- `TL` - Inhalt eines Teelöfels
- `cl` - Zentiliter, entspricht 10 ml
- `Msp.` - Messerspitze
- `Pck.` - Päckcken
- `Pr` - Prise
- `Btl.` - Beutel
- `Bd./Bn.` - Bund

{% assign sortedRezepte = site.rezepte|sort: 'category' %}
{% assign lastCategory = '' %}
{% for rezept in sortedRezepte %}{% if rezept.category %}{% if lastCategory != rezept.category %}
### {{ rezept.category }}
{% endif %}
[{{ rezept.title }}]({{ rezept.url }}) <br/>
{% assign lastCategory = rezept.category %}{% endif %}{% endfor %}
