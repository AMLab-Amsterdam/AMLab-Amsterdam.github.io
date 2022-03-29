---
layout: page
permalink: /publications/
title: Publications
description: 
nav: true
---
<!-- _pages/publications.md -->
<div class="publications">

Check out our people page to get an impression of the research done by the people at AMLab, and of course follow us on <a href="https://twitter.com/{{ site.twitter_username }}" title="Twitter">Twitter <i class="fab fa-twitter"></i></a> to stay tuned! Below you'll find an archive our groups output in ML research, all the way back to 1994! <br><br>


<h2>2022</h2>
{% bibliography -f AMLab -q @*[year=2022]* %}

<h2>2021</h2>
{% bibliography -f AMLab -q @*[year=2021]* %}

<h2>All Publications (via Pure)</h2>

<iframe src="https://dare.uva.nl/search?org-uuid=dfefe074-153e-4c2f-94f4-e6723b28d7d5;docsPerPage=60;sort=year;smode=iframe;startDoc=1" width="100%" height="1000px"></iframe>

</div>
