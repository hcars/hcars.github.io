---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
permalink: 
layout: home
---


<ul id="blog-list">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}" class="blog-link">{{ post.title }}</a>
    </li>
    
            
           <h6> Tags: </h6> <ul  class="tag">
	   {% for tag in post.tags %}
	    <li style="padding:10px;">
		{{tag}}
	    </li>
	    
	  {% endfor %} 
	</ul>
  {% endfor %}
</ul>
