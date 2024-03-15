---
layout: post
title: Sarajevo, Bosna sevdah i rat
author: Vedran Alajbegovic
permalink: /sarajevo
category: sarajevo
---

Mozda će neko reći da sam lud za Sarajevom. Međutim, ne smatram tako. Jednostavno, povremeno, dokumentujem ono što vidim, čujem, pročitam.

Jedna od prvih stvari koja me je uvukla u ovu priču je veliki broj pjesama koje nisu nužno o Sarajevu ali pominju Sarajevo ili se na neki drugi način referenciraju na to. Za sada, taj spisak prilično ne uređen ali vrijedan je pažnje. Zastupljeni su svi mogući i ne mogući žanrovi :D



{% for post in site.categories.sarajevo %}
<table>
	<tr>
		<td>
			<small>{{ post.date | date: "%-d %B %Y" }}</small> <br>
			<a href="{{ post.url }}">{{ post.title }}</a>
			{% if post.description %}
			 	<br/> <small> {{ post.description }}</small>
			{% endif %}
			<hr style="width: 50px;">
		</td>
	</tr>
</table>
{% endfor %}