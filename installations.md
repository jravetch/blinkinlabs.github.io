---
layout: project
permalink: /installations/index.html
category: frontpage
title: Installations
img: domestar
---
<ul class="block-grid five-up project_preview">
  {% for project in site.posts %}
	{% if project.category contains 'installation' %}
	  <li class="{{project.type}} ">
		<a href="{{ project.url | replace:'index.html','' }}">

			<img src="/images/{{project.img|downcase}}/preview.jpg" alt="{{project.title}} project"/>
		  <p> {{project.title }}  </p>
		  <div class="project_preview_desc project_preview_desc hide-on-phones hide-on-desktops hide-on-tablets">  <!-- {{project.desc}} --> </div>
		</a>
	  </li>
	{% endif %}
  {% endfor %}
</ul>
