## Sophos NIS2 Explorer

Interactive web-based explorer that maps the **Sophos Central Platform** (services, controls, threat intelligence, data lake and AI-assisted workflows) to **EU NIS2 Chapter IV** requirements (and Austrian **NISG** references).  
The app is optimized for **presales / consulting conversations**, supports **DE/EN UI**, and can be embedded into other pages via `iframe` including a `postMessage` API.

- **Key features**
  - Interactive layer view of the Sophos Central Platform (Services, Threat Prevention & Controls, Threat Intelligence, Data Lake, AI & agentic workflows)
  - Detail panel with:
    - mapped Sophos solutions per feature
    - mapped NIS2 Chapter IV articles and Austrian NISG references (RIS link)
    - PDCA cycle view (Plan–Do–Check–Act) for the selected solution
    - heuristic risk reduction calculator for the next PDCA step (not legal/insurance advice)
    - presales collateral text (opportunity snippet) copyable to clipboard
  - Stack mode for combining multiple solutions and viewing joint NIS2 coverage
  - NIS2 article-centric view (start from an article and see which platform elements support it)
  - Language toggle (DE/EN) and print-friendly layout for PDF export

- **Technology**
  - Pure HTML, CSS and vanilla JavaScript (no build step required)
  - Single entry point: `index.html`
  - Designed to run as a static asset (e.g. GitHub Pages, internal web server, or inside other portals via iframe)

### Usage

#### Local usage

You can open `index.html` directly in a browser, but for full functionality (and modern browser security defaults) it is recommended to serve it via a small HTTP server:

```bash
cd Sophos-NIS2-Explorer
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/index.html
```

#### Embedding via iframe

The explorer is designed to be embedded into other web applications / portals, e.g.:

```html
<iframe
  id="nis2Frame"
  src="/assets/gse-platform-nis2-explorer.html?embed=1"
  title="Sophos Central Platform – NIS2 requirements"
  width="100%"
  height="800"
  style="border: none; max-width: 1280px;"
  loading="lazy"
  sandbox="allow-scripts allow-same-origin"
></iframe>
```

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

#### postMessage API

When embedded, the explorer sends messages to the parent window:

- `ready` – once initialized, with a list of available feature IDs
- `select` – when a feature is selected, with its id, label, solution and NIS2 articles
- `resize` – when the internal height changes, so the parent can resize the iframe

Example listener in the embedding page:

```html
<script>
  window.addEventListener('message', (e) => {
    if (e.data?.source !== 'nis2-explorer') return;
    if (e.data.type === 'resize') {
      document.getElementById('nis2Frame').style.height =
        e.data.data.height + 'px';
    }
    if (e.data.type === 'select') {
      console.log('Selected:', e.data.data.label, e.data.data.nis2_articles);
    }
  });
</script>
```

### Disclaimers

- The NIS2 / NISG mappings and the heuristic risk calculator are **illustrative tooling for presales / consulting**.
- Information published on the website is **not** legal advice, compliance advice, or a formal cyber risk quantification.
---

## Sophos NIS2 Explorer (Deutsch)

Interaktiver, webbasierten Explorer, der die **Sophos Central Platform** (Services, Kontrollen, Threat Intelligence, Data Lake sowie AI- und Agenten-Workflows) mit den Anforderungen aus **EU NIS2 Kapitel IV** verknüpft (inklusive österreichischer **NISG**-Referenzen).  
Die Anwendung ist für **Presales- und Beratungsgespräche** optimiert, unterstützt **DE/EN-Oberfläche** und kann per `iframe` in andere Seiten eingebettet werden (inkl. `postMessage`-API).

- **Kernfunktionen**
  - Interaktive Layer-Ansicht der Sophos Central Platform (Services, Threat Prevention & Controls, Threat Intelligence, Data Lake, AI & agentische Workflows)
  - Detailbereich mit:
    - zugeordneten Sophos-Lösungen pro Plattform-Element
    - zugeordneten NIS2-Kapitel-IV-Artikeln und österreichischen NISG-Verweisen (inkl. RIS-Link)
    - PDCA-Zyklus (Plan–Do–Check–Act) für die gewählte Lösung
    - heuristischem Risikoreduktions-Rechner für den nächsten PDCA-Schritt (keine Rechts-/Versicherungsberatung)
    - Presales-Textbausteinen („Opportunity Snippet“) zum Kopieren in die Zwischenablage
  - Stack-Ansicht zum Kombinieren mehrerer Lösungen und gemeinsamer NIS2-Abdeckung
  - NIS2-Artikel-zentrierte Ansicht (Start beim Artikel, Anzeige der unterstützenden Plattform-Elemente)
  - Sprachumschaltung (DE/EN) und druckoptimiertes Layout für PDF-Export

- **Technologie**
  - Reines HTML, CSS und Vanilla JavaScript (kein Build-Prozess nötig)
  - Einziger Einstiegspunkt: `index.html`
  - Läuft als statisches Asset (z. B. GitHub Pages, interner Webserver oder Portal-Integration via iframe)

### Verwendung

#### Lokale Nutzung

`index.html` kann direkt im Browser geöffnet werden. Empfohlen ist ein kleiner HTTP-Server:

```bash
cd Sophos-NIS2-Explorer
python3 -m http.server 8000
```

Dann im Browser aufrufen:

```text
http://localhost:8000/index.html
```

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

#### postMessage-API

Im eingebetteten Betrieb sendet der Explorer Nachrichten an das Parent-Fenster:

- `ready` – nach der Initialisierung, inkl. Liste der Feature-IDs
- `select` – bei Auswahl eines Features (id, Label, Lösung, NIS2-Artikel)
- `resize` – bei Layout-Änderungen, damit das Parent die iframe-Höhe anpassen kann

Beispiel-Listener in der einbettenden Seite:

```html
<script>
  window.addEventListener('message', (e) => {
    if (e.data?.source !== 'nis2-explorer') return;
    if (e.data.type === 'resize') {
      document.getElementById('nis2Frame').style.height =
        e.data.data.height + 'px';
    }
    if (e.data.type === 'select') {
      console.log('Ausgewählt:', e.data.data.label, e.data.data.nis2_articles);
    }
  });
</script>
```

### Hinweise / Disclaimer

- Die NIS2-/NISG-Mappings und der heuristische Risikorechner dienen als **unterstützendes Werkzeug für Presales- und Beratungsgespräche**.
- Informationen auf der Website stellen **keine** Rechtsberatung, Compliance-Beratung oder formale Cyber-Risiko-Quantifizierung dar.
