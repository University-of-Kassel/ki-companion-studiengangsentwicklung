# Studiengang-CompAIgnon – Konfiguration

Studiengang-CompAIgnon verwendet eine mehrschichtige Konfiguration.

## Ladefolge

Empfohlene Reihenfolge:

```text
1. core/
2. regulatory/de/
3. profiles/state/<active-state>/
4. profiles/institution/<active-institution>/
5. aktive programme-features des Institutionsprofils
6. Analysedokumente
```

## Überschreibungsprinzip

Profile konkretisieren den Core.

Sie dürfen jedoch nicht:

- Quellenbindung deaktivieren
- Scope-Prüfung umgehen
- fehlende Evidenz als Konformität behandeln
- lokale Regeln als allgemeine Regeln ausgeben

## Konkrete Regeln

Quantitative Werte und Pflichtfelder gehören nicht in den Core.

Beispiel:

```yaml
quantitative_rules:
  - id: "hours_per_credit"
    trigger: "workload_credit_relation"
    value: "<VALUE>"
    source: "institutional_regulation"
    citation: "..."
```

## Quellenpflicht

Jede verbindliche Regel braucht:

- `source`
- `citation`

Fehlen diese Angaben, wird die Regel nicht als verbindlicher Prüfmaßstab verwendet.

## Nichtnormative Qualitätschecks

Lokale Qualitätsmaßstäbe können in einem Institutionsprofil hinterlegt werden.

Sie müssen klar als nichtnormativ gekennzeichnet sein und dürfen höchstens zu
einem `HINWEIS` führen.


## Programme-Features

Optionale Feature-Profile werden nach dem Institutionsprofil geladen.

Beispiel:

```yaml
programme_type: bachelor
programme_features:
  - sustainability_studies
feature_parameters:
  sustainability_studies:
    integration_mode: inas_b
```

Ein fehlender erforderlicher Feature-Parameter wird nicht geraten. Der Scope bleibt dann
`UNCLEAR`, bis der Modus aus den Analysedokumenten belastbar bestimmt werden kann.
