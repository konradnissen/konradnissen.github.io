---
layout: default
title: Start
---

<div class="hero">
  <div class="prose">
    <p>
      Willkommen auf meiner Internetseite! Since January 2026, I work at the Mercator Forum Migration and Democracy (MIDEM) at the Dresden University of Technology. As a sociologist by training, I somewhat stumbled into a political science. I am fairly new to political polarization research and still at an early stage of my PhD. So this website (and the human who created this website) is still in progress. If you have questions, please reach out. I am always interested in other perspectives on polarization and always down for a chat.     </em>.
    </p>
    <p>
      During my studies, I excessively focused on cultural sociology and sociology of culture, especially in research on culture and cognition (schemas, frames, internalization, and all sorts of this blabla), concepts and categories (the Hannan et al. stuff), taste (Bourdieu and the confusion since then) and cultural object (it's not just socially charged?!). As a political sociologist, I am currently seek to combine my knowledge with Cleavage and polariaztion research to answer questions like "Is there more in-group bias (vis a vis affective polarization) between less ambiguous social groups?", "How aligned are cleavages?" or "Are values important in political sociology or is it just garbage?" Prior to joining MIDEM, I had the rare experience to see what's life outside academia and worked at company to analyze large-scale text data. So I am planning to hop on the CSS bandwagon somewhere in the future.  </strong>.
    </p>
    <p>
      Here you can find my <a href="{{ '/publikationen/' | relative_url }}">CV</a>,
      I don't really have much to offer, yet.g.
    </p>

    <ul class="stamp-links">
      {% if site.orcid and site.orcid != "" %}<li><a href="https://orcid.org/{{ site.orcid }}">ORCID</a></li>{% endif %}
      {% if site.google_scholar and site.google_scholar != "" %}<li><a href="{{ site.google_scholar }}">Google Scholar</a></li>{% endif %}
      {% if site.github_username and site.github_username != "" %}<li><a href="https://github.com/{{ site.github_username }}">GitHub</a></li>{% endif %}
      {% if site.linkedin and site.linkedin != "" %}<li><a href="{{ site.linkedin }}">LinkedIn</a></li>{% endif %}
      {% if site.bluesky and site.bluesky != "" %}<li><a href="{{ site.bluesky }}">Bluesky</a></li>{% endif %}
      <li><a href="mailto:{{ site.email }}">E-Mail</a></li>
    </ul>
  </div>

  <!-- Porträtfoto: Datei nach /assets/img/portrait.jpg legen und die
       Zeile unten von "hero-portrait-placeholder" auf ein echtes
       <img>-Tag umstellen (Beispiel als Kommentar darunter). -->
  <div class="hero-portrait-placeholder">
    A professional but not too serious photo will be inserted here somewhere in the future <br>(/assets/img/Missing :(.jpg)
  </div>
  <!--
  <img class="hero-portrait" src="{{ '/assets/img/portrait.jpg' | relative_url }}" alt="That's me">
  -->
</div>

<section class="recent-posts">
  <h2>Maybe I will write things that no one cares about in the future (aka the Blog-section)</h2>
  <ul>
    {% for post in site.posts limit: 4 %}
    <li>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %Y" }}</time>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
  <p><a href="{{ '/blog/' | relative_url }}">See contributions &rarr;</a></p>
</section>

<p class="field-note">Zuletzt aktualisiert: {{ site.time | date: "%B %Y" }}</p>
