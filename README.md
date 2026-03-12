## Sophos NIS2 Compliance Explorer

Interactive web-based workspace for **NIS2 compliance analysis and maturity assessment**.  
The app helps map the **Sophos Central Platform** (services, controls, threat intelligence, data lake and AI-assisted workflows) to **EU NIS2 Chapter IV** requirements (and Austrian **NISG** references) and supports an **interactive dialogue with the customer** about:

- current **NIS2 maturity level**,
- concrete **gaps and residual risks**, and
- the **next PDCA step** (Plan–Do–Check–Act) for risk reduction.

The explorer is designed for **presales / consulting conversations** is intended to **evolve continuously**: new requirements, insights from customer projects and Sophos platform capabilities can be iteratively added to keep the conversation about “what is the next best step?” current.

- **Key features for compliance & maturity work**
  - Interactive layer view of the Sophos Central Platform (Services, Threat Prevention & Controls, Threat Intelligence, Data Lake, AI & agentic workflows) as **control landscape** for NIS2
  - Detail panel to support **structured NIS2 compliance analysis** with:
    - mapped Sophos solutions per feature as **implementation options for controls**
    - mapped NIS2 Chapter IV articles and Austrian NISG references (RIS link) as **compliance anchor**
    - PDCA cycle view (Plan–Do–Check–Act) for the selected solution to identify the **next action in the PDCA rhythm**
    - heuristic risk reduction calculator for the next PDCA step to **estimate maturity and residual risk** (not legal/insurance advice)
    - presales collateral text (opportunity snippet) copyable to clipboard as **conversation documentation**
  - Stack mode for combining multiple solutions and viewing joint NIS2 coverage to **discuss alternative target architectures**
  - NIS2 article-centric view (start from an article and see which platform elements support it) to **start from customer requirements and goals**
  - Language toggle (DE/EN) and print-friendly layout for PDF export to **capture the current maturity discussion and next steps**

- **Technology**
  - Pure HTML, CSS and vanilla JavaScript (no build step required)
  - Single entry point: `index.html`
  - Designed to run as a static asset (e.g. GitHub Pages, internal web server, or inside other portals via iframe)

### Usage

#### Local usage

You can open `index.html` directly in a browser.

**URL parameters**

- `embed=1` – compact layout for embedded usage (smaller header, no `min-width`)
- `lang=en` – force English UI (default is German: `de`)
- `select=<id>` – pre-select a feature on load (e.g. `managed_services_mdr`)

You can combine parameters, for example:

```text
/assets/gse-platform-nis2-explorer.html?embed=1&lang=en&select=data_controls_firewall
```

**Available `select` feature IDs (excerpt)**

- `managed_services_mdr`, `managed_services_ir`, `managed_services_vuln`
- `advisory_services`, `professional_services`
- `data_controls_endpoint`, `data_controls_firewall`, `data_controls_identity`
- `data_controls_email`, `data_controls_network`, `data_controls_cloud`
- `integrations`, `secops_xdr`, `secops_edr`, `secops_itdr`, `secops_ndr`, `workspace_protection`
- `threat_intel_xops`, `threat_intel_ai`, `adaptive_attack_protection`, `active_threat_response`, `data_lake`, `ai_agentic_workflows`

### Disclaimers

- The NIS2 / NISG mappings, the heuristic risk calculator and any maturity indication are **illustrative tooling for presales / consulting**.
- Information published on the website is **not** legal advice, compliance advice, or a formal cyber risk quantification.
---

## Sophos NIS2 Compliance Explorer(Deutsch)

Interaktive, webbasierte Arbeitsoberfläche für **NIS2-Compliance-Analyse und Reifegrad-Erhebung**.  
Die Anwendung verknüpft die **Sophos Central Platform** (Services, Kontrollen, Threat Intelligence, Data Lake sowie AI- und agentische Workflows) mit den Anforderungen aus **EU NIS2 Kapitel IV** (inklusive österreichischer **NISG**-Referenzen) und unterstützt einen **strukturierten Dialog mit dem Kunden** zu:

- aktuellem **NIS2-Reifegrad**,
- konkreten **Lücken und Restrisiken** und
- dem **nächsten Schritt zur Risikoreduktion** im Sinne des Plan–Do–Check–Act- bzw. Blindow-Check-Rhythmus.

Der Explorer ist für **Presales- und Beratungsgespräche** optimiert, unterstützt eine **DE/EN-Oberfläche** und kann per `iframe` in andere Seiten eingebettet werden (inkl. `postMessage`-API). Er ist bewusst so angelegt, dass er sich **kontinuierlich weiterentwickeln** lässt – z. B. um neue regulatorische Anforderungen, Lessons Learned aus Projekten oder neue Sophos-Plattformfunktionen – damit im Kundengespräch immer der **nächste sinnvolle Schritt im Kontext der Ziele des Kunden** im Fokus steht.

- **Kernfunktionen für Compliance & Reifegrad**
  - Interaktive Layer-Ansicht der Sophos Central Platform (Services, Threat Prevention & Controls, Threat Intelligence, Data Lake, AI & agentische Workflows) als **Kontroll-Landkarte** im NIS2-Kontext
  - Detailbereich zur Unterstützung einer **strukturierten NIS2-Compliance-Analyse** mit:
    - zugeordneten Sophos-Lösungen pro Plattform-Element als **Umsetzungsoptionen für Kontrollen**
    - zugeordneten NIS2-Kapitel-IV-Artikeln und österreichischen NISG-Verweisen (inkl. RIS-Link) als **Compliance-Verankerung**
    - PDCA-Zyklus (Plan–Do–Check–Act) für die gewählte Lösung, um den **nächsten Schritt im PDCA-Rhythmus** zu identifizieren
    - heuristischem Risikoreduktions-Rechner für den nächsten PDCA-Schritt, um **Reifegrad und Restrisiko abzuschätzen** (keine Rechts-/Versicherungsberatung)
    - Presales-Textbausteinen („Opportunity Snippet“) zum Kopieren in die Zwischenablage als **Dokumentations- und Gesprächsgrundlage**
  - Stack-Ansicht zum Kombinieren mehrerer Lösungen und gemeinsamer NIS2-Abdeckung, um **Zielarchitekturen und Alternativen zu diskutieren**
  - NIS2-Artikel-zentrierte Ansicht (Start beim Artikel, Anzeige der unterstützenden Plattform-Elemente), um **ausgehend von Kundenanforderungen und -zielen** zu argumentieren
  - Sprachumschaltung (DE/EN) und druckoptimiertes Layout für PDF-Export, um die **aktuellen Reifegrad-Ergebnisse und nächsten Schritte festzuhalten**

- **Technologie**
  - Reines HTML, CSS und Vanilla JavaScript (kein Build-Prozess nötig)
  - Einziger Einstiegspunkt: `index.html`
  - Läuft als statisches Asset (z. B. GitHub Pages, interner Webserver oder Portal-Integration via iframe)

### Verwendung

#### Lokale Nutzung

`index.html` kann direkt im Browser geöffnet werden.

#### Einbettung per iframe

Die Anwendung ist für die Einbettung in andere Web-Anwendungen / Portale ausgelegt, z. B.:

```html
<iframe
  id="nis2Frame"
  src="/assets/gse-platform-nis2-explorer.html?embed=1"
  title="Sophos Central Platform – NIS2-Anforderungen"
  width="100%"
  height="800"
  style="border: none; max-width: 1280px;"
  loading="lazy"
  sandbox="allow-scripts allow-same-origin"
></iframe>
```

**URL-Parameter**

- `embed=1` – kompakter Embed-Modus (kleinerer Header, keine `min-width`)
- `lang=en` – englische Oberfläche erzwingen (Standard ist Deutsch `de`)
- `select=<id>` – Element beim Laden vorauswählen (z. B. `managed_services_mdr`)

Parameter können kombiniert werden, z. B.:

```text
/assets/gse-platform-nis2-explorer.html?embed=1&lang=en&select=data_controls_firewall
```

**Verfügbare `select`-IDs (Auszug)**

- `managed_services_mdr`, `managed_services_ir`, `managed_services_vuln`
- `advisory_services`, `professional_services`
- `data_controls_endpoint`, `data_controls_firewall`, `data_controls_identity`
- `data_controls_email`, `data_controls_network`, `data_controls_cloud`
- `integrations`, `secops_xdr`, `secops_edr`, `secops_itdr`, `secops_ndr`, `workspace_protection`
- `threat_intel_xops`, `threat_intel_ai`, `adaptive_attack_protection`, `active_threat_response`, `data_lake`, `ai_agentic_workflows`

### Hinweise / Disclaimer

- Die NIS2-/NISG-Mappings, der heuristische Risikorechner und jegliche Reifegrad-Indikationen dienen als **unterstützendes Werkzeug für Presales- und Beratungsgespräche**.
- Informationen auf der Website stellen **keine** Rechtsberatung, Compliance-Beratung oder formale Cyber-Risiko-Quantifizierung dar.
