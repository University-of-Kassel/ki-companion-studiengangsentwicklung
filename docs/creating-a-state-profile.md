# Studiengang-CompAIgnon – Landesprofil erstellen

## 1. Template kopieren

```text
profiles/state/template/
```

nach:

```text
profiles/state/<state-id>/
```

## 2. Profilidentität setzen

In `profile.yaml` mindestens anpassen:

- `id`
- `name`
- `state_code`
- `state_name`

## 3. Quellen registrieren

Typischerweise:

- Landeshochschulgesetz
- Studienakkreditierungsverordnung
- amtliche Begründung

Jede Quelle erhält:

- eindeutige ID
- Titel
- Quellentyp
- Status
- Scope
- Pfad zur Knowledge-Datei

## 4. Knowledge-Dateien hinterlegen

Die Dateien werden in `knowledge/` abgelegt.

## 5. Regeln ergänzen

Nur Regeln aufnehmen, die tatsächlich aus den hinterlegten Landesquellen
ableitbar sind.

Jede verbindliche Regel benötigt:

- `source`
- `citation`

## 6. Nicht in das Landesprofil aufnehmen

Nicht hierher gehören:

- Allgemeine Bestimmungen einer Hochschule
- hochschulspezifische Modulhandbuchvorgaben
- lokale Zuständigkeiten
- lokale Begriffe
- Ansprechpartner
