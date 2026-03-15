---
title: Projektübersicht
---

# OE5XRX – Projektübersicht

Willkommen beim Projekt-Dashboard des **OE5XRX Amateurfunkclubs für Remote Stationen**.

Diese Seite gibt einen Überblick über alle laufenden, pausierten und geplanten Projekte der Organisation.
Die Daten werden manuell in der Datei [`_data/projects.yml`](https://github.com/OE5XRX/dashboard/blob/main/_data/projects.yml) gepflegt.

---

{% assign active_projects = site.data.projects | where: "state", "active" %}
{% assign paused_projects = site.data.projects | where: "state", "paused" %}
{% assign idea_projects = site.data.projects | where: "state", "ideas" %}

{% if active_projects.size > 0 %}
## 🟢 Aktive Projekte

{% for project in active_projects %}
### {{ project.name }}

> {{ project.short_description }}

| | |
|:--|:--|
| **Status** | {{ project.status }} |
| **Nächster Schritt** | {{ project.next_step }} |
| **Zuletzt aktualisiert** | {{ project.last_updated }} |
| **Repository** | [{{ project.repo_url | remove: "https://github.com/" }}]({{ project.repo_url }}) |
{% if project.docs_url %}| **Dokumentation** | [{{ project.docs_url }}]({{ project.docs_url }}) |{% endif %}
| **Tags** | {% for tag in project.tags %}`{{ tag }}` {% endfor %}|

{% if project.subprojects %}
**Unterprojekte:**

{% for sub in project.subprojects %}
- **{{ sub.name }}** – {{ sub.short_description }}{% if sub.status %} · _{{ sub.status }}_{% endif %}{% if sub.repo_url %} · [Repository]({{ sub.repo_url }}){% endif %}
{% endfor %}
{% endif %}

---

{% endfor %}
{% endif %}

{% if paused_projects.size > 0 %}
## ⏸️ Pausierte Projekte

{% for project in paused_projects %}
### {{ project.name }}

> {{ project.short_description }}

| | |
|:--|:--|
| **Status** | {{ project.status }} |
| **Nächster Schritt** | {{ project.next_step }} |
| **Zuletzt aktualisiert** | {{ project.last_updated }} |
| **Repository** | [{{ project.repo_url | remove: "https://github.com/" }}]({{ project.repo_url }}) |
{% if project.docs_url %}| **Dokumentation** | [{{ project.docs_url }}]({{ project.docs_url }}) |{% endif %}
| **Tags** | {% for tag in project.tags %}`{{ tag }}` {% endfor %}|

{% if project.subprojects %}
**Unterprojekte:**

{% for sub in project.subprojects %}
- **{{ sub.name }}** – {{ sub.short_description }}{% if sub.status %} · _{{ sub.status }}_{% endif %}{% if sub.repo_url %} · [Repository]({{ sub.repo_url }}){% endif %}
{% endfor %}
{% endif %}

---

{% endfor %}
{% endif %}

{% if idea_projects.size > 0 %}
## 💡 Ideen

{% for project in idea_projects %}
### {{ project.name }}

> {{ project.short_description }}

| | |
|:--|:--|
| **Status** | {{ project.status }} |
| **Nächster Schritt** | {{ project.next_step }} |
| **Zuletzt aktualisiert** | {{ project.last_updated }} |
| **Repository** | [{{ project.repo_url | remove: "https://github.com/" }}]({{ project.repo_url }}) |
{% if project.docs_url %}| **Dokumentation** | [{{ project.docs_url }}]({{ project.docs_url }}) |{% endif %}
| **Tags** | {% for tag in project.tags %}`{{ tag }}` {% endfor %}|

{% if project.subprojects %}
**Unterprojekte:**

{% for sub in project.subprojects %}
- **{{ sub.name }}** – {{ sub.short_description }}{% if sub.status %} · _{{ sub.status }}_{% endif %}{% if sub.repo_url %} · [Repository]({{ sub.repo_url }}){% endif %}
{% endfor %}
{% endif %}

---

{% endfor %}
{% endif %}
