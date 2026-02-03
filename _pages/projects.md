---
layout: page
title: projects
permalink: /projects/
description: Applied AI systems and data products built end-to-end—speech analytics, ML, and decision intelligence.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

---

## 🧠 Featured work

These projects reflect how I build **applied AI systems**: clear problem framing, measurable evaluation, pragmatic engineering choices, and outputs that support real decisions.

### VoxSentiment — Applied Speech Intelligence (End-to-End)
**Tech:** Python · Faster-Whisper (ASR) · Pyannote (diarisation) · Transformers · Streamlit · MongoDB  
Built a full speech analytics pipeline that transforms raw call audio into **speaker-attributed transcripts**, **concise summaries**, and **sentiment signals**.

**What it delivers**
- Faster QA and escalation triage via structured call intelligence
- Separation of **agent vs customer** signals for clearer root-cause analysis
- Modular design to extend into regulated/high-stakes workflows (insurance ops, service triage)

---

### AI-Driven Lead Prioritisation — Decision Intelligence System
**Tech:** Python · ML · CRM analytics · Audio-derived signals  
Designed a lead-ranking framework that combines **behavioural + conversational signals** to prioritise leads by conversion likelihood.

**What it delivers**
- Evaluation-first protocol (baselines, metrics, validation strategy)
- Explainable ranking outputs built for stakeholder adoption
- Reproducibility plan using public datasets when private data access is restricted

---

### Geospatial Dashboard — Transport, PM2.5 & Respiratory Health (2010–2020)
**Tech:** Python · Panel · Folium · Matplotlib  
Built an interactive dashboard to analyse relationships between **transport density**, **PM2.5 pollution**, and **respiratory outcomes** across Indian states.

**What it delivers**
- Normalised metrics (per 100k) for fair cross-state comparison
- Gender-wise + total outcomes with clear narrative visuals
- Designed for non-technical stakeholders (simple filters, readable insights)

---

### CNN Heritage Classification — Imbalanced Multi-Class Vision
**Tech:** PyTorch · Custom CNNs · Transfer learning (e.g., ResNet18)  
Implemented and compared custom vs pretrained CNN approaches on a 10-class imbalanced dataset with robust validation.

**What it delivers**
- K-fold cross-validation for reliable performance estimates
- Fine-tuning vs feature-extractor strategies with justification
- Confusion matrices + class-wise metrics for diagnosis (not just accuracy)
