# Studiengang-CompAIgnon

Studiengang-CompAIgnon ist ein modular aufgebautes Analysesystem zur hochschulrechtlichen
Konformitätsprüfung, Strukturkontrolle und Qualitätssicherung von
Studiengängen.

Ziel dieses Repositories ist eine de-lokalisierte, konfigurierbare
Studiengang-CompAIgnon-Version, die nicht an ein bestimmtes Bundesland oder eine bestimmte
Hochschule gebunden ist.

Studiengang-CompAIgnon ist ein plattform- und modellunabhängiges, quellengestütztes Prüfsystem für Studiengänge. 
Die fachliche Prüfmethodik, das Regelwerk und die Ergebnisstandards sind unabhängig von den eingesetzten Sprachmodellen und Benutzeroberflächen. 
Externe KI-Systeme dienen als austauschbare Komponenten für sprachbasierte Analyseaufgaben.

## Architektur

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
ANALYSIS DOCUMENTS
   ↓
Studiengang-CompAIgnon RESULT
```

## Repository-Struktur

```text
Studiengang-CompAIgnon/
├── README.md
├── LICENSE
├── NOTICE.md
├── CHANGELOG.md
│
├── core/
│   ├── system-prompt.md
│   ├── methodology.md
│   ├── output-specification.md
│   ├── rule-engine/
│   │   ├── norm-logic.yaml
│   │   ├── scope-matcher.yaml
│   │   ├── trigger-mapping.yaml
│   │   └── conflict-library.yaml
│   └── templates/
│       ├── review-table.md
│       ├── analysis-report.md
│       ├── exam-concept-analysis.md
│       └── objective-matrix.md
│
├── regulatory/
│   └── de/
│       ├── profile.yaml
│       └── knowledge/
│
├── profiles/
│   ├── state/
│   │   └── template/
│   └── institution/
│       └── template/
│
├── examples/
│   └── example-university/
│
├── docs/
│
└── tests/
```

## Grundprinzip

Der Studiengang-CompAIgnon-Core beantwortet die Frage:

> Wie prüft Studiengang-CompAIgnon?

Die Profile beantworten:

> Welche Regeln gelten im konkreten Kontext?

Analysedokumente beantworten:

> Was wird geprüft?

Damit bleiben Prüfmethodik, regulatorischer Rahmen, lokale Regeln und konkrete
Studiengangdokumente voneinander getrennt.

## Core

Der Core enthält:

- Rollen- und Verhaltenslogik
- Prüfmethodik
- Scope- und Normlogik
- Konfliktmuster
- Ausgabeformate
- Templates

Der Core enthält keine konkreten Landes- oder Hochschulregeln.

## Regulatory / DE

`regulatory/de/` enthält übergreifende deutsche und europäische Regel- und
Referenzquellen.

Eine dort hinterlegte Quelle ist nicht automatisch anwendbar. Der Scope Matcher
entscheidet über ihren Geltungsbereich.

## Landesprofile

Unter `profiles/state/` werden landesspezifische Regeln hinterlegt.

Das Template kann kopiert werden:

```text
profiles/state/template/
→
profiles/state/<state-id>/
```

## Institutionsprofile

Unter `profiles/institution/` werden hochschulspezifische Regeln,
Terminologie und Zuständigkeiten hinterlegt.

```text
profiles/institution/template/
→
profiles/institution/<institution-id>/
```

## Quellenbindung

Studiengang-CompAIgnon darf keine Regelaussage ohne anwendbare, verfügbare und zitierfähige
Regelquelle treffen.

Fehlende Quellen werden nicht durch Modellwissen ersetzt.

## Ergebnisstatus

Studiengang-CompAIgnon unterscheidet insbesondere:

- `KONFORM`
- `ABWEICHUNG`
- `UNKLAR`
- `NICHT PRÜFBAR`
- `NICHT ANWENDBAR`
- `HINWEIS`

Ein Hinweis ist kein Mangel.

## Beispiel

Unter `examples/example-university/` befindet sich eine vollständig fiktive
Demokonfiguration.

Sie dient ausschließlich dazu, die technische und fachliche Struktur zu
erläutern und darf nicht als reale Prüfgrundlage verwendet werden.

## Dokumentation

Siehe `docs/`:

- `architecture.md`
- `installation.md`
- `configuration.md`
- `creating-a-state-profile.md`
- `creating-an-institution-profile.md`
- `adding-knowledge-files.md`
- `programme-features.md`

## Tests

Unter `tests/` liegen kleine Referenzfälle, mit denen Änderungen an Core und
Profilen kontrolliert werden können.

## Technischer Umfang

Dieses Repository enthält Prompts, methodische Vorgaben, Regelkonfigurationen,
Quellenverzeichnisse, Profile und Referenzfälle. Es enthält derzeit **keine
eigenständig ausführbare Prüf-Engine**, keinen Kommandozeilenstarter und keinen
automatisierten Test-Runner. Für die Verwendung ist eine passende Laufzeit- bzw.
Integrationsumgebung erforderlich. Die Beispiele unter `tests/` sind
fachliche Referenzfälle.

## Lizenz- und Quellenhinweise

Die Apache-2.0-Lizenz des Repositories gilt nicht automatisch für die in
`knowledge/` eingebundenen fremden Rechts- und Hochschuldokumente. Vor einer
Weitergabe dieser Dateien sind ihre Nutzungsbedingungen gesondert zu prüfen.
Die ESG 2015 stehen unter CC BY-NC-SA 4.0 und dürfen nicht kommerziell
genutzt werden. Details enthält `NOTICE.md`.

## Entwicklungsstand

Die Repository-Struktur ist modularisiert. Ein reales Landesprofil für Hessen,
ein Institutionsprofil für die Universität Kassel und das optionale
Programme-Feature Nachhaltigkeitsstudien sind integriert.

Offen bleiben insbesondere die laufende Rechtsstandsprüfung einzelner
Knowledge-Quellen, die Ergänzung noch fehlender institutioneller Quellen und
End-to-End-Tests mit realen Analysedokumenten.
