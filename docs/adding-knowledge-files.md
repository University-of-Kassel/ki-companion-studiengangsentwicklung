# Studiengang-CompAIgnon – Knowledge-Dateien hinzufügen

## Grundsatz

Eine Knowledge-Datei ist eine dauerhaft oder wiederholt verwendbare
Regel- oder Referenzquelle.

Sie ist nicht automatisch anwendbar, nur weil sie im Repository liegt.

## 1. Datei ablegen

Lege die Datei im passenden `knowledge/`-Ordner ab.

## 2. Quelle registrieren

Ergänze die Quelle in der zugehörigen `profile.yaml`.

Mindestens erforderlich:

```yaml
- id: "unique_source_id"
  title: "Offizieller Titel"
  regulatory_level: "..."
  source_type: "..."
  status: "..."
  scope:
    ...
  knowledge_file: "knowledge/example.pdf"
```

## 3. Geltungsbereich definieren

Der Scope sollte so eng wie nötig sein.

Mögliche Dimensionen:

- Jurisdiktion
- Institution
- Studiengangtyp
- Abschlussart
- Regelungsbereich
- Dokumenttyp
- Programmmerkmal
- zeitlicher Geltungsbereich

## 4. Fundstellen nutzen

Regeln in `rules.yaml` sollten auf konkrete Fundstellen verweisen.

## 5. Dateinamen

Empfohlen:

- kleingeschrieben
- keine Leerzeichen
- stabile Bezeichnungen
- keine internen Laufwerks- oder Ablagenamen

Beispiel:

```text
general-regulations-bama.pdf
```

## 6. Versionen

Bei neuer Fassung einer Quelle:

- Metadaten aktualisieren
- zeitlichen Geltungsbereich prüfen
- Vorgänger-/Nachfolgerbeziehung dokumentieren
- Tests erneut ausführen

## 7. Keine stillschweigende Substitution

Fehlt eine referenzierte Datei, wird sie nicht durch allgemeines Modellwissen
ersetzt.

Studiengang-CompAIgnon kennzeichnet die Prüfung an dieser Stelle als eingeschränkt oder nicht
prüfbar.
