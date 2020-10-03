---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Mala Škola Programiranja sa micro:bit-om
permalink: /microbit
category: microbit
---

# Micro:bit - Osnove programiranja uz pomoć micro:bit platforme
[Za nastavnike i učenike]

<iframe width="550" height="315" src="https://www.youtube.com/embed/videoseries?list=PLZPDmC17_cP3_OzsRrFRlhRwb3_hbfjpZ" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Programiranje sa micro:bit-om je kratki serijal koji sam napravio sa namjerom da koliko toliko olakšam učenicima i nastavnicima učenje sa ovom zabavnom platformom.

Iako je micro:bit izuzetno popularan te shodno tome na internetu je moguće naći pregršt materijala i primjera za učenje, oni uglavnom nisu dostupni na našem jeziku.

Unaprijed se izvinjavam za sve greške koje postoje u klipovima. Nažalost, nisam bio u prilici više da se posvetim ovom sadržaju te je sav materijal napravljen bez priprema i u jednom snimku.  
  
Sve sugestije, greške, komentare ili pitanja može te slati na [vedran@nardev.org](vedran@nardev.org)  
  
Kafu mi može te kupiti ovdje: [https://www.buymeacoffee.com/usci8e4yG](https://www.buymeacoffee.com/usci8e4yG)  
  
Kompletna play lista: [PROGRAMIRANJE MICRO:BIT](https://www.youtube.com/playlist?list=PLZPDmC17_cP3_OzsRrFRlhRwb3_hbfjpZ)  


### Sadržaj:

**#1 -** [INTRO:](https://youtu.be/X7pSszGjsT8)  
**#2 -** [WORKFLOW:](https://youtu.be/7gqTXYQyZqA)  
**#3 -** [PROGRAM ELEMENTS:](https://youtu.be/50Es1zeFGdQ)  
**#4 -** [VARIABLE: https:/](https://youtu.be/vDFhKc5v-zg)  
**#5 -** [IF STATEMENT:](https://youtu.be/BLvNZA9U6pY)  
**#6 -** [FOR and WHILE LOOPS:](https://youtu.be/GQb4oks65yQ)  
**#7 -** [INPUTS:](https://youtu.be/ufqtD4aeufo)  
**#8 -** [MATH:](https://youtu.be/mnmwU_hr8DM)  
**#9 -** [MUSIC:](https://youtu.be/oMyVPygxWFA)  
**#10 -** [LED:](https://youtu.be/6oIk5YM_1lQ)  
**#11 -** [FUNCTIONS:](https://youtu.be/mn5aJJt5zps)  
**#12 -** [INPUTS:](https://youtu.be/UoRYZR3srF4)  
**#13 -** [EXTRAS (savjeti za kupovinu isl.):](https://youtu.be/xZi3XdDQa_w)  
**#14 -** [Kitronik dodatci:](https://www.youtube.com/watch?v=heC-YP34hLM)  
  
**Linkovi za kupovinu micro:bit-a:**
- [www.kitronik.co.uk](https://www.kitronik.co.uk/microbit.html)
- [www.sparkfun.com](https://www.sparkfun.com/categories/284)

Sve sugestije, komentare ili pitanja može te slati na [vedran@nardev.org](vedran@nardev.org)


{: .content }

### Dodatni zadaci
<hr>
{% for post in site.categories.microbit %}
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