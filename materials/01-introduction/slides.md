---
marp: true
paginate: true
size: 16:9
title: "Façade-X Tutorial — Introduction"
footer: "Façade-X Tutorial · ISWC 2026 · Bari"
style: |
  :root {
    --navy: #023558;
    --navy-2: #0a4a76;
    --accent: #e8703a;
    --accent-2: #f2a154;
    --ink: #1c2530;
    --muted: #5b6b7a;
    --line: #e2e8ee;
    --bg-soft: #f5f8fb;
  }
  section {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    color: var(--ink);
    background: #fff;
    padding: 60px 70px;
    font-size: 26px;
    line-height: 1.5;
    border-top: 10px solid var(--navy);
  }
  h1, h2 { color: var(--navy); font-weight: 700; line-height: 1.15; }
  h2 { font-size: 1.6em; margin: 0 0 .6em; padding-bottom: .25em; border-bottom: 3px solid var(--accent); display: inline-block; }
  a { color: var(--navy-2); text-decoration: none; }
  strong { color: var(--navy); }
  footer { color: var(--muted); font-size: .55em; }
  section::after { color: var(--muted); font-size: .55em; }

  /* Hero (title / closing) */
  section.hero {
    background: linear-gradient(135deg, var(--navy) 0%, var(--navy-2) 100%);
    color: #fff;
    border-top: none;
    justify-content: center;
  }
  section.hero h1 { color: #fff; font-size: 2.1em; margin: 0 0 .2em; }
  section.hero h2 { color: #fff; border-bottom-color: var(--accent-2); }
  section.hero p { color: #cfe0ee; }
  section.hero strong { color: #fff; }
  section.hero footer, section.hero::after { color: #cfe0ee; }
  .eyebrow {
    text-transform: uppercase; letter-spacing: .14em;
    font-size: .6em; font-weight: 600; color: var(--accent-2);
    margin: 0 0 .8em;
  }
  .meta { font-size: .75em; color: #e6eef5; margin-top: 1.4em; }
  .badges { margin-top: 1em; }
  .badge {
    display: inline-block; margin: 0 .35em .35em 0;
    background: rgba(255,255,255,.12); border: 1px solid rgba(255,255,255,.25);
    color: #fff; padding: .2em .8em; border-radius: 1em; font-size: .55em;
  }

  /* Agenda table */
  table { border-collapse: collapse; width: 100%; font-size: .68em; }
  th { background: var(--navy); color: #fff; text-align: left; padding: .45em .7em; }
  td { padding: .35em .7em; border-bottom: 1px solid var(--line); }
  tr.slot td { background: var(--bg-soft); color: var(--navy); font-weight: 700; }
  tr.break td { background: #fdf1ea; color: var(--accent); font-weight: 600; }
  td.who { color: var(--muted); white-space: nowrap; }

  /* Presenter cards */
  .people { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; margin-top: .4em; }
  .card {
    background: var(--bg-soft); border: 1px solid var(--line);
    border-left: 5px solid var(--accent); border-radius: 8px;
    padding: .55em .8em; font-size: .62em; line-height: 1.35;
  }
  .card b { color: var(--navy); font-size: 1.2em; display: block; }
  .card .aff { color: var(--muted); display: block; margin-bottom: .3em; }
  
  /* Diagrams: blue = re-engineering, orange = re-modelling */
  .flow { display: flex; align-items: center; justify-content: center; gap: 14px; margin: .8em 0; font-size: .75em; }
  .box { background: var(--bg-soft); border: 2px solid var(--line); border-radius: 10px; padding: .5em .9em; text-align: center; }
  .box b { display: block; color: var(--navy); }
  .box.re { border-color: var(--navy-2); background: #e8f0f7; }
  .box.rm { border-color: var(--accent); background: #fdf1ea; }
  .box.both { background: linear-gradient(90deg, #e8f0f7 50%, #fdf1ea 50%); border-color: var(--muted); }
  .box small { color: var(--muted); display: block; }
  .arr { color: var(--muted); font-size: 1.4em; }
  .re-t { color: var(--navy-2); font-weight: 700; }
  .rm-t { color: var(--accent); font-weight: 700; }
  pre.q { font-size: .62em; line-height: 1.45; background: #f7f9fb; border: 1px solid var(--line); border-radius: 8px; padding: .8em 1em; }
  pre.q .re { background: #e8f0f7; color: var(--navy-2); }
  pre.q .rm { background: #fdf1ea; color: #b34d1c; }
  .cards { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; margin-top: .6em; }
  .cards.two { grid-template-columns: 1fr 1fr; }
  .cards > div { background: var(--bg-soft); border: 1px solid var(--line); border-top: 4px solid var(--accent); border-radius: 8px; padding: .6em .8em; font-size: .62em; line-height: 1.4; }
  .cards > div b { color: var(--navy); font-size: 1.25em; display: block; margin-bottom: .3em; }
  .cite { color: var(--muted); font-size: .55em; position: absolute; bottom: 70px; left: 70px; }
  .mm { display: flex; align-items: center; justify-content: center; gap: 10px; font-size: .72em; margin: .8em 0; }
  .mm .c { border: 2px solid var(--navy-2); border-radius: 10px; padding: .6em .9em; background: #e8f0f7; text-align: center; }
  .mm .s { color: var(--accent); font-family: monospace; font-weight: 700; white-space: nowrap; }
  .mm .s::after { content: " →"; color: var(--muted); }
  .mm .v { background: #fff; border: 1px dashed var(--muted); border-radius: 20px; padding: .2em .8em; font-family: monospace; }
  .mm .rows > div { display: flex; align-items: center; gap: 10px; margin: .4em 0; }

---

<!-- _class: hero -->
<!-- _paginate: false -->

<p class="eyebrow">ISWC 2026 · Half-Day Tutorial</p>

# Façade-X: Querying Any Format as a Knowledge Graph

Integrate CSV, JSON, XML, spreadsheets and more using SPARQL alone.

<div class="meta">📍 Bari, Italy &nbsp;·&nbsp; 📅 25 October 2026 &nbsp;·&nbsp; ⏱️ 14:10–18:00</div>

<div class="badges"><span class="badge">SPARQL</span><span class="badge">Knowledge Graphs</span><span class="badge">Data Integration</span><span class="badge">Hands-on</span></div>

<!--
Welcome. Organised by the W3C Data Façades Community Group.
-->

---

## The afternoon in one line

**Any data format → a knowledge graph → SPARQL alone.**

- The Façade-X idea and its foundations
- Hands-on with SPARQL Anything
- (coffee break)
- How it is used in practice, taught, and standardised

<!--
~30 s. Keep it flat: what this afternoon is for.
-->


---

## Agenda

<table>
<tr><th>Time</th><th>Session</th><th>Who</th></tr>
<tr class="slot"><td>14:10–14:50</td><td colspan="2">Slot 1 · The Problem and the Idea</td></tr>
<tr><td>14:10–14:30</td><td>Introduction to Façade-X</td><td class="who">Enrico</td></tr>
<tr><td>14:30–14:50</td><td>Foundations: towards a theory of façade-based data access</td><td class="who">Luigi</td></tr>
<tr class="slot"><td>14:50–16:10</td><td colspan="2">Slot 2 · Hands-on with SPARQL Anything</td></tr>
<tr><td>14:50–15:20</td><td>Live querying of CSV, JSON and XML</td><td class="who">Luigi</td></tr>
<tr><td>15:20–15:45</td><td>Functions and magic properties</td><td class="who">Luigi</td></tr>
<tr><td>15:45–16:10</td><td>Guided exercises with real datasets</td><td class="who">Enrico</td></tr>
<tr class="break"><td>16:10–16:30</td><td>Break · SPARQL Anything Clinic — bring your data</td><td class="who">All</td></tr>
<tr class="slot"><td>16:30–18:00</td><td colspan="2">Slot 3 · From Practice to Standards</td></tr>
<tr><td>16:30–17:30</td><td>Industry talks: railway KG · TriplyDB deployment · Public Procurement Data Space</td><td class="who">Mathias, Martin, Ivo</td></tr>
<tr><td>17:30–17:40</td><td>Teaching KG management with SPARQL Anything</td><td class="who">Ryan</td></tr>
<tr><td>17:40–18:00</td><td>W3C Data Façades CG: roadmap and discussion</td><td class="who">Enrico</td></tr>
</table>

<!--
~1 min. Point at the three slots; the break doubles as a clinic.
-->


---

## Presenters

<div class="people">
<div class="card"><b>Luigi Asprino</b><span class="aff">Università Telematica San Raffaele, Roma (IT)</span>Co-founder of SPARQL Anything · chair, W3C Data Façades CG</div>
<div class="card"><b>Enrico Daga</b><span class="aff">KMi, The Open University (UK)</span>Co-founder of SPARQL Anything · chair, W3C Data Façades CG</div>
<div class="card"><b>Martin van Harmelen</b><span class="aff">Triply (NL)</span>SPARQL engine design and ELT pipelines on TriplyDB</div>
<div class="card"><b>Mathias Vanden Auweele</b><span class="aff">MATDATA (BE)</span>Railway infrastructure data and production KGs</div>
<div class="card"><b>Ryan Shaw</b><span class="aff">UNC Chapel Hill (US)</span>Teaches KG management with SPARQL Anything</div>
<div class="card"><b>Ivo Velitchkov</b><span class="aff">Kvistgaard (BG)</span>Consultant and trainer in semantic technologies</div>
</div>

<!--
~1.5 min. Each presenter stands up / waves; one sentence each.
-->

---

## Show of hands ✋

<style scoped>
ol { font-size: .95em; }
ol li { margin: .35em 0; }
.aside { color: var(--muted); font-size: .7em; margin-top: 1em; }
</style>

Raise your hand if you…

1. have **heard of** Façade-X or SPARQL Anything before today
2. have **tried** SPARQL Anything, even once
3. **use** it in your work: research, a project, a product, teaching
4. have built a knowledge graph from CSV, JSON or XML **some other way**: RML/YARRRML, SPARQL Generate, scripts…

<p class="aside">And: what data gives you the most trouble? Keep it for the clinic.</p>

<!--
~1.5 min. Keep hands up and lower them step by step: 1 → 2 → 3.
Q1 low: spend more time on the idea in the intro.
Q3 high: ask one or two people what they use it for.
Q4 high: the comparison with mapping languages will land; mention it explicitly.
-->

---

## What you will learn today

<style scoped>
.cols { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; margin-top: .3em; }
.col h3 { color: var(--accent); font-size: .8em; text-transform: uppercase; letter-spacing: .1em; margin: 0 0 .4em; }
.col ul { font-size: .78em; margin: 0; padding-left: 1.1em; }
.col li { margin: .35em 0; }
</style>

<div class="cols">
<div class="col">

### In practice

- Query **CSV, JSON, XML, Markdown, APIs** as a knowledge graph, with SPARQL alone
- Map any source to **your own vocabulary** in one `CONSTRUCT`
- **Join formats** in a single query
- Turn queries into **pipelines**: templates, parameters, reuse
- Use **SPARQL Anything** from the command line and from Python

</div>
<div class="col">

### Beyond practice

- The **Façade-X idea**: one minimal model (containers, slots, values) for any format
- Its **theory**: what we can know about a query before touching the data
- How it is **deployed** in production: railways, procurement, TriplyDB
- How it is **taught** in KG courses
- How it is becoming a **standard**, and how to join the W3C CG

</div>
</div>

<!--
~1 min. Left column: what you take home and use on Monday.
Right column: why it works, where it is used, where it is going.
-->

---

## Before we start

- **SPARQL Anything** downloaded, or **PySPARQL Anything** in Python / Jupyter
- No local setup? A **Google Colab** notebook is available
- Slides, notebooks and exercises: **w3c-facade-x.github.io/iswc2026-tutorial**
- Questions any time — and keep your own data for the clinic during the coffee break.

<!--
~1 min. Check who has the tool running; point to Colab fallback.
-->

---

<!-- _class: hero -->
<!-- _paginate: false -->

<p class="eyebrow">Slot 1 · The Problem and the Idea</p>

# Let's start.

**w3c-facade-x.github.io/iswc2026-tutorial**

---

## Building a knowledge graph: the usual way

<style scoped>
.stack { display: flex; flex-direction: column; gap: 8px; }
.stack .box { padding: .35em .8em; }
.cards > div { border-top-color: #c0392b; }
</style>

<div class="flow">
  <div class="stack">
    <div class="box"><b>CSV</b></div>
    <div class="box"><b>JSON</b></div>
    <div class="box"><b>XML</b></div>
  </div>
  <span class="arr">→</span>
  <div class="stack">
    <div class="box both"><b>CSV mapping</b><small>columns + ontology</small></div>
    <div class="box both"><b>JSON mapping</b><small>JSONPath + ontology</small></div>
    <div class="box both"><b>XML mapping</b><small>XPath + ontology</small></div>
  </div>
  <span class="arr">→</span>
  <div class="box"><b>Knowledge graph</b></div>
</div>

<span class="re-t">Re-engineering</span> and <span class="rm-t">re-modelling</span> in the same artefact. Why is it a problem?

<div class="cards">
  <div><b>One mapping per format</b>New format, or a format change: rewrite the mapping.</div>
  <div><b>Two skills, one artefact</b>Format expert and domain expert must edit the same rules.</div>
  <div><b>A second language</b>RML, R2RML, XSPARQL… next to SPARQL, with their own tools.</div>
  <div><b>Hard to maintain</b>Change the ontology: touch format code. Change the format: touch the ontology.</div>
</div>

<!--
~1.5 min. Same ontology, three mappings, each mixing blue and orange.
-->

---

## Building a knowledge graph: with Façade-X

<style scoped>
.stack { display: flex; flex-direction: column; gap: 8px; }
.stack .box { padding: .35em .8em; }
</style>

<div class="flow">
  <div class="stack">
    <div class="box"><b>CSV</b></div>
    <div class="box"><b>JSON</b></div>
    <div class="box"><b>XML</b></div>
  </div>
  <span class="arr">→</span>
  <div class="box re" style="align-self:stretch;display:flex;flex-direction:column;justify-content:center"><b>Façade</b><small>re-engineering<br>by the engine</small></div>
  <span class="arr">→</span>
  <div class="box"><b>RDF</b><small>one generic shape</small></div>
  <span class="arr">→</span>
  <div class="box rm"><b>SPARQL CONSTRUCT</b><small>re-modelling<br>by you</small></div>
  <span class="arr">→</span>
  <div class="box"><b>Knowledge graph</b></div>
</div>

<div class="cards">
  <div style="border-top-color:var(--navy-2)"><b>Formats handled once</b>In the engine, for everyone. No format code in your mapping.</div>
  <div><b>One skill per step</b>You write only the re-modelling: your domain, your ontology.</div>
  <div><b>SPARQL only</b>The language you already know, with all its features.</div>
  <div><b>Easy to maintain</b>Change the source: keep the mapping. Change the ontology: keep the source.</div>
</div>

<p class="cite">Daga et al., SEMANTiCS 2021 · Asprino et al., ACM TOIT 2023</p>

<!--
~1.5 min. Point-by-point answer to the previous slide: the four cards line up with the four problems.
-->
---

## Most approaches merge them

<div class="flow">
  <div class="box"><b>JSON file</b></div>
  <span class="arr">→</span>
  <div class="box both" style="padding:.8em 1.4em"><b>One mapping rule</b><small>format access + ontology, together</small></div>
  <span class="arr">→</span>
  <div class="box"><b>Knowledge graph</b></div>
</div>

<pre class="q">mappings:
  artist:
    sources:
      - [<span class="re">artists.json~jsonpath</span>, <span class="re">'$[*]'</span>]
    s: <span class="rm">ex:</span><span class="re">$(name)</span>
    po:
      - [<span class="rm">a</span>, <span class="rm">schema:Person</span>]
      - [<span class="rm">schema:name</span>, <span class="re">$(name)</span>]</pre>

Same for R2RML, RML, XSPARQL, scripts. **New format → new rule.** And a second language next to SPARQL.

<!--
~1 min. YARRRML as an example, not as a target. Point at how blue and orange are interleaved in every line.
-->

---

## Façade-X: keep them apart

<div class="flow">
  <div class="box"><b>Any source</b><small>CSV, JSON, XML,<br>HTML, XLSX, text…</small></div>
  <span class="arr">→</span>
  <div class="box re"><b>Façade</b><small>generic RDF view<br><b>done by the engine</b></small></div>
  <span class="arr">→</span>
  <div class="box rm"><b>SPARQL CONSTRUCT</b><small>to your ontology<br><b>done by you</b></small></div>
  <span class="arr">→</span>
  <div class="box"><b>Knowledge graph</b></div>
</div>

<div class="cards two" style="margin-top:1em">
  <div style="border-top-color:var(--navy-2)"><b>Re-engineering → the façade</b>One generic structure for every format. No format knowledge in your queries.</div>
  <div><b>Re-modelling → SPARQL</b>The language you already know. Joins, filters and functions come for free.</div>
</div>

<p class="cite">Daga, Asprino, Mulholland, Gangemi. Facade-X: an opinionated approach to SPARQL Anything. SEMANTiCS 2021.</p>

<!--
~1 min. The core message of the tutorial.
-->

---

## The meta-model: containers, slots, values

<div class="mm">
  <div class="c">container<br><code>fx:root</code></div>
  <span class="s">rdf:_1</span>
  <div class="c">container</div>
  <div class="rows">
    <div><span class="s">xyz:name</span><span class="v">"Turner"</span></div>
    <div><span class="s">xyz:born</span><span class="v">"1775"</span></div>
  </div>
</div>

<div class="cards">
  <div style="border-top-color:var(--navy-2)"><b>Container</b>A file, a row, an object, an array, an element.</div>
  <div><b>Slot · by number</b><code>rdf:_1</code>, <code>rdf:_2</code>… order: rows, array items, children.</div>
  <div><b>Slot · by name</b><code>xyz:name</code>… keys, headers, attributes.</div>
  <div style="border-top-color:var(--muted)"><b>Value</b>A literal. A container may also have a <b>type</b>.</div>
</div>

<!--
~1.5 min. Four notions, nothing format-specific. Walk the diagram left to right.
-->

---

## Same data, same façade

<style scoped>
.three { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; font-size: .55em; }
.three pre { margin: .3em 0; }
.three h4 { color: var(--navy); margin: 0; font-size: 1.3em; }
.diff { background: #fdf1ea; color: #b34d1c; font-weight: 700; }
</style>

<div class="three">
<div>
<h4>CSV</h4>
<pre>name,born
Turner,1775</pre>
<pre>[] a fx:root ;
  rdf:_1 [
    xyz:name "Turner" ;
    xyz:born "1775" ] .</pre>
</div>
<div>
<h4>JSON</h4>
<pre>[ {"name": "Turner",
   "born": 1775} ]</pre>
<pre>[] a fx:root ;
  rdf:_1 [
    xyz:name "Turner" ;
    xyz:born <span class="diff">"1775"^^xsd:decimal</span> ] .</pre>
</div>
<div>
<h4>XML</h4>
<pre>&lt;artists&gt;
  &lt;artist name="Turner" born="1775"/&gt;
&lt;/artists&gt;</pre>
<pre>[] a fx:root, <span class="diff">xyz:artists</span> ;
  rdf:_1 [ a <span class="diff">xyz:artist</span> ;
    xyz:name "Turner" ;
    xyz:born "1775" ] .</pre>
</div>
</div>

**Three formats, one shape.** The highlighted parts are the only differences.

<!--
~1.5 min. Ask: what's different? JSON keeps the number type; XML keeps element names as types.
-->
---

## One query, both jobs

<pre class="q"><span class="rm">CONSTRUCT {</span>
<span class="rm">  ?artist a schema:Person ; schema:name ?name ; schema:birthDate ?born .</span>
<span class="rm">}</span> WHERE {
<span class="re">  SERVICE &lt;x-sparql-anything:location=artists.csv,csv.headers=true&gt; {</span>
<span class="re">    ?row xyz:name ?name ; xyz:born ?born .</span>
<span class="re">  }</span>
<span class="rm">  BIND (fx:entity(ex:, ?name) AS ?artist)</span>
}</pre>

<div class="flow" style="font-size:.7em">
  <div class="box re"><b>artists.csv</b></div>
  <span class="arr">⇄</span>
  <div class="box re"><b>artists.json</b></div>
  <span class="arr">⇄</span>
  <div class="box re"><b>artists.xml</b>*</div>
  <span style="margin-left:1em">Change the <span class="re-t">format</span>: the <span class="rm-t">mapping</span> stays.</span>
</div>

<!--
~1 min. Prefixes omitted. *XML has a different shape (attribute + text), so that pattern needs one small change: honest point.
-->

---

## Why "opinionated"

<div class="cards">
  <div><b>Minimal</b>Four notions. Learn one model, not one per format.</div>
  <div><b>SPARQL only</b>No second language. All of SPARQL is available.</div>
  <div><b>Virtual or materialised</b>Query sources directly, or save the result as RDF.</div>
  <div style="border-top-color:var(--muted)"><b>The price</b>Some format details are left out, by design.</div>
</div>

<!--
~45 s. Be honest about the trade-off.
-->

---

## Read more

<style scoped>
.cards > div .contrib { display: block; margin-top: .6em; padding-top: .5em; border-top: 1px solid var(--line); color: var(--accent); font-weight: 600; }
</style>

<div class="cards two">
  <div><b>The idea</b>Daga, E., Asprino, L., Mulholland, P., Gangemi, A.<br><i>Facade-X: an opinionated approach to SPARQL Anything.</i><br>SEMANTiCS 2021. Studies on the Semantic Web 53: 58–73.<span class="contrib">Introduces the Façade-X meta-model and SPARQL Anything.</span></div>
  <div><b>The method</b>Asprino, L., Daga, E., Gangemi, A., Mulholland, P.<br><i>Knowledge graph construction with a façade: a unified method to access heterogeneous data sources on the web.</i><br>ACM Transactions on Internet Technology 23(1): 1–31, 2023.<span class="contrib">Formalises Façade-X and shows its expressive power: demonstrates it can represent any format defined by a context-free grammar.</span></div>
</div>

Next, the theory: Asprino & Daga, *Towards a theory of Façade-X data access*, TGDK 2026.

<!--
~15 s. Don't read them; they're on the website.
-->

---

## What comes next

<div class="flow">
  <div class="box re"><b>Luigi</b><small>theory: what can we know<br>about a query before<br>touching the data?</small></div>
  <span class="arr">→</span>
  <div class="box rm"><b>Hands-on</b><small>CSV, JSON, XML,<br>functions, exercises</small></div>
  <span class="arr">→</span>
  <div class="box"><b>After the break</b><small>production, teaching,<br>W3C CG</small></div>
</div>

<!--
~15 s. Hand over to Luigi.
-->