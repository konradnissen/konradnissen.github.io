---
layout: default
title: Start
---

<!-- ================================================================
     ANPASSEN: Ersetze Text, Bild und Links unten mit deinen eigenen
     Angaben. Alles zwischen den Kommentaren ist Beispielinhalt.
     ================================================================ -->

<div class="hero">
  <div class="prose">
    <p>
      Ich bin Wissenschaftler:in im Bereich <strong>[Fachgebiet, z. B. Materialwissenschaften]</strong>
      an der <strong>[Institution]</strong>. Mein Forschungsschwerpunkt liegt auf
      <em>[kurze Beschreibung deines Forschungsinteresses in 1–2 Sätzen]</em>.
    </p>
    <p>
      Aktuell arbeite ich an <strong>[aktuelles Projekt oder Fragestellung]</strong>,
      gefördert durch <strong>[Förderorganisation, optional]</strong>. Zuvor war ich
      <strong>[frühere Station, z. B. Postdoc an der Universität X]</strong>.
    </p>
    <p>
      Auf dieser Seite findest du meine <a href="{{ '/publikationen/' | relative_url }}">Publikationen</a>,
      meinen <a href="{{ '/lebenslauf/' | relative_url }}">Lebenslauf</a> sowie
      <a href="{{ '/blog/' | relative_url }}">Beiträge</a> zu Forschung und Wissenschaftsalltag.
    </p>

    <ul class="stamp-links">
      {% if site.orcid and site.orcid != "" %}<li><a href="https://orcid.org/{{ site.orcid }}">ORCID</a></li>{% endif %}
      {% if site.google_scholar and site.google_scholar != "" %}<li><a href="{{ site.google_scholar }}">Google Scholar</a></li>{% endif %}
      {% if site.github_username and site.github_username != "" %}<li><a href="https://github.com/{{ site.github_username }}">GitHub</a></li>{% endif %}
      {% if site.linkedin and site.linkedin != "" %}<li><a href="{{ site.linkedin }}">LinkedIn</a></li>{% endif %}
      <li><a href="mailto:{{ site.email }}">E-Mail</a></li>
    </ul>
  </div>

  <!-- Porträtfoto: Datei nach /assets/img/portrait.jpg legen und die
       Zeile unten von "hero-portrait-placeholder" auf ein echtes
       <img>-Tag umstellen (Beispiel als Kommentar darunter). -->
  <div class="hero-portrait-placeholder">
    Porträtfoto hier einfügen<br>(/assets/img/portrait.jpg)
  </div>
  <!--
  <img class="hero-portrait" src="{{ '/assets/img/portrait.jpg' | relative_url }}" alt="Porträt von [Name]">
  -->
</div>

<section class="recent-posts">
  <h2>Neueste Beiträge</h2>
  <ul>
    {% for post in site.posts limit: 4 %}
    <li>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %Y" }}</time>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
  <p><a href="{{ '/blog/' | relative_url }}">Alle Beiträge ansehen &rarr;</a></p>
</section>

<p class="field-note">Zuletzt aktualisiert: {{ site.time | date: "%B %Y" }}</p>
