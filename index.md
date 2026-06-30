---
title: Olivia Hsu
layout: home
---

<table border="0" cellpadding="0">
<td valign="top" style="min-width:140px;">
<img src="/assets/owhsu.jpg" width="160">
</td>
<td valign="top">
Assistant Professor<br/>
Carnegie Mellon University<br/>
ECE and courtesy CS<br/> 
Office: CIC 4121<br/>
<a href="mailto:owh@cmu.edu">owh [at] cmu [dot] edu</a><br/>
<a href="/assets/owhsu-cv.pdf">Curriculum Vitae</a>
<div id=siteUpdate> </div>
<script>
const desiredRepo = "weiya711.github.io"
const monthNames = ["January", "February", "March", "April", "May", "June",
  "July", "August", "September", "October", "November", "December"
];

var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    let repos = JSON.parse(this.responseText);
    repos.forEach((repo)=>{
      if (repo.name == desiredRepo)
      {
        var lastUpdated = new Date(repo.pushed_at);
        var day = lastUpdated.getUTCDate();
        var month = lastUpdated.getUTCMonth();
        var year = lastUpdated.getUTCFullYear();
        siteUpdate.innerHTML += (`<em>Site Last Updated ${monthNames[month]} ${year}</em><br>`);
      }
    });
  }
};
xhttp.open("GET", "https://api.github.com/users/weiya711/repos", true);
xhttp.send();
</script>
</td>
</table>

> <mark><strong>Update</strong></mark> <span class="text-grey">April 29, 2026
>
> My friend and collaborator, [Kalhan Koul](https://www.linkedin.com/in/kalhan-koul/), and I recently wrote an IEEE Spectrum
> feature article on our research in hardware for sparse AI. It's a quick
> read and has some very interesting artwork, take a look [here](https://spectrum.ieee.org/sparse-ai) 

I am an assistant professor at Carnegie Mellon University in the department of Electrical and Computer Engineering and, by courtesy, Computer Science. Previously, I received my PhD from Stanford University, 
advised by Professors
[Kunle Olukotun](https://profiles.stanford.edu/kunle-olukotun?tab=bio) 
and [Fredrik Kjolstad](http://fredrikbk.com). 

My vision is a world where domain-specific hardware is used efficiently,
easily, and to its full potential. Hardware adoption should be limited by its
design, not its programming system, and new architecture ideas should be ready to use
well at the time of its introduction. Toward this goal, I work on hardware and
software systems that efficiently run complex, data-dependent applications
(think sparse and dynamic ML workloads) on next-generation, domain-specific
hardware (think heterogeneous, distributed, and accelerator architectures).
During my PhD, I worked on one instance of this problem by studying 
[Programming Systems for Sparse Accelerators](https://weiya711.github.io/assets/owhsu-thesis.pdf).

My research interests broadly lie at the intersection of computer architecture,
programming systems, compilers, programming languages/models, and digital
circuits/VLSI.


<h2 class="tableheading">Publications</h2>

<table border="0">
  {% for pub_keyval in site.data.publications %}
    <tr>
      {%- assign pub = pub_keyval[1] -%}
      <td>
        <b><a href="pub_md/{{pub_keyval[0]}}.html" style="color: #464646">{{ pub.title }}</a></b><br/>
        {%- for author in pub.authors -%}
          {%- if forloop.last == true and forloop.length > 1 %}
            and
          {%- endif %}
          {%- if author == "hsu" %}
            <b><font color="#000000">{{ site.data.authors[author].name }}</font></b>
          {%- else %}
            <a href="{{- site.data.authors[author].site -}}" style="color: #464646">{{ site.data.authors[author].name }}</a>
          {%- endif -%}
          {%- if forloop.last == false and forloop.length > 2 -%}
            ,
          {%- endif %}
        {%- endfor -%}<br/>
        <i>{{ pub.venue }}
        {%- if pub.venuenote %}
        ({{ pub.venuenote }})
        {%- endif -%}
        {%- if pub.volume -%}
        , Volume {{ pub.volume }}
        {%- endif -%}
        {%- if pub.issue -%}
        , Issue {{ pub.issue }}
        {%- endif -%}
        </i>, {{ pub.month }} {{ pub.year }}<br/>
        {%- if pub.award -%}
          <span style="color:#0096FF"><b>{{ pub.award }}</b></span><br/>
        {%- endif -%}
      </td>
      <td valign="top" width="20">
        {% if pub.pdf %}
            <a href="{{ pub.pdf }}"><img src="/assets/PDF_icon.svg" alt="pdf" /></a>
	{% elsif pub.url %}
            <a href="{{ pub.url }}"><img src="/assets/PDF_icon.svg" alt="pdf" /></a>
        {% endif %}
        {% if pub.movie %}
          <a href="{{ pub.movie }}"><img src="/assets/movie.png" alt="youtube" /></a>
        {% endif %}
      </td>
    </tr>
{% endfor %}
</table>

<h2 class="tableheading">Press</h2>

<table border="0">
{%- for press_keyval in site.data.press %}
  {%- assign press= press_keyval[1] -%}
  <tr>
  <td> 
    <b><a href="{{press.url}}">{{press.title}}</a></b><br/>{{press.venue}}
  </td>
  </tr>
{% endfor %}
</table>
