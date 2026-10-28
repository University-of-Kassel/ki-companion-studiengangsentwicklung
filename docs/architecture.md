# Studiengang-CompAIgnon – Architektur

Studiengang-CompAIgnon ist in voneinander getrennte Schichten aufgebaut.

## Grundmodell

```text
Studiengang-CompAIgnon CORE
   ↓
REGULATORY / DE
   ↓
STATE PROFILE
   ↓
INSTITUTION PROFILE
   ↓
ACTIVE PROGRAMME FEATURES (optional)
   ↓
ANALYSEDOCUMENTS
   ↓
Studiengang-CompAIgnon RESULT
```

## 1. Core

`core/` enthält ausschließlich die allgemeine Prüfmethodik und Darstellungslogik.

Dazu gehören:

- Systemverhalten
- Methodik
- Rule Engine
- Output Specification
- Templates

Der Core enthält keine konkreten Landes- oder Hochschulnormen.

## 2. Regulatory / DE

`regulatory/de/` enthält übergreifende Regel- und Referenzquellen, die für
deutsche Hochschulen grundsätzlich relevant sein können.

Nicht jede dort hinterlegte Quelle ist automatisch anwendbar.

Der Scope Matcher entscheidet, welche Quelle zum konkreten Prüfgegenstand passt.

## 3. State Profile

`profiles/state/` enthält landesspezifische Regeln.

Typische Inhalte:

- Landeshochschulgesetz
- Landesakkreditierungsverordnung
- amtliche Begründungen
- weitere landesrechtliche Vorgaben

## 4. Institution Profile

`profiles/institution/` enthält hochschulspezifische Regeln und Konventionen.

Typische Inhalte:

- Allgemeine Bestimmungen
- Rahmenprüfungsordnungen
- lokale Pflichtfelddefinitionen
- lokale quantitative Regeln
- institutionelle Terminologie
- Zuständigkeiten

## 5. Programme Features

`profiles/institution/<institution>/programme-features/` enthält optionale
Regelmodule, die innerhalb einer Institution nur für bestimmte Studiengangsmerkmale
gelten.

Beispiele:

- lehramts- oder hochschulspezifische Querschnittsmodelle
- integrierte Studienbereiche
- institutionell geregelte Nebenfächer
- besondere Curriculumsbausteine, die in mehrere Studiengänge eingebunden werden können

Ein Programme-Feature wird **nicht** automatisch deshalb aktiv, weil ein Studiengang
thematisch ähnlich ist. Die Aktivierung braucht einen belastbaren Dokumentbezug oder eine
explizite Konfiguration.

Features können Parameter besitzen, z. B. unterschiedliche Integrationsmodi. Diese werden
unter `feature_parameters` im Prüfkontext geführt.

## 6. Analysedokumente

Analysedokumente sind der konkrete Prüfgegenstand.

Beispiele:

- Fachprüfungsordnung
- Modulhandbuch
- Studiengangskonzept
- Studienverlaufsplan

Sie gehören grundsätzlich nicht in den dauerhaften Regelungsbestand.

## 7. Regelanwendung

Die Rule Engine trennt vier Aufgaben:

- `norm-logic.yaml` – Normauswahl und Konfliktauflösung
- `scope-matcher.yaml` – Geltungsbereich
- `trigger-mapping.yaml` – Aktivierung fachlicher Prüfungen
- `conflict-library.yaml` – wiederkehrende Problem- und Konfliktmuster

## 8. Architekturprinzip

Ein Wechsel von Hochschule oder Bundesland soll nur Änderungen an Profilen und
Knowledge-Dateien erfordern.

Der Studiengang-CompAIgnon-Core soll unverändert bleiben.


## Beispiel: Universität Kassel / Nachhaltigkeitsstudien

Die AB NaS ist keine einzelne Studiengangsordnung, sondern eine institutionsweit
verwendbare Regelquelle mit mehreren Anwendungsformen. Sie liegt deshalb unter:

`profiles/institution/university-kassel/programme-features/nachhaltigkeitsstudien/`

und wird nur für Studiengänge geladen, die dieses Feature tatsächlich verwenden.
