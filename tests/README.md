# Studiengang-CompAIgnon – Tests

Die Tests prüfen, ob Änderungen am Core oder an Profilen die erwartete
Prüflogik verändern.

## Struktur

```text
tests/
├── cases/
│   ├── workload/
│   ├── module-description/
│   ├── examination-design/
│   └── scope/
└── expected-results/
```

## Grundsatz

Testfälle sollen möglichst klein sein und genau einen Prüfmechanismus isolieren.

Sie dürfen keine reale Hochschule oder reale Rechtsquelle vortäuschen.

Für normative Tests werden fiktive Testprofile verwendet.

## Testarten

### Core-Tests

Prüfen allgemeine Methodik:

- fehlende Evidenz
- Scope-Fehler
- Dokumentwidersprüche
- Trennung von Hinweis und Mangel

### Profiltests

Prüfen Regeln eines konkreten Profils:

- quantitative Schwellenwerte
- Pflichtfelder
- lokale Trigger
- institutionelle Terminologie

## Erwartete Ergebnisse

Jeder Testfall sollte ein erwartetes Ergebnis besitzen.

Beispiel:

```text
cases/workload/mismatch.yaml
expected-results/workload-mismatch.expected.yaml
```
