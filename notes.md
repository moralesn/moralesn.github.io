---
<<<<<<< HEAD
layout: pagetitle: Notes---

 {% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}
=======
layout: default
pagetitle: 
--- 
{{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{post.url }})
>>>>>>> e2ee356503175b5a44750dcce36ad2949a698212
