# Studiengang-CompAIgnon – Institutionsprofil erstellen

## 1. Template kopieren

```text
profiles/institution/template/
```

nach:

```text
profiles/institution/<institution-id>/
```

## 2. `profile.yaml`

Hier werden definiert:

- Hochschulidentität
- Bundesland
- Vererbte Profile
- institutionelle Regelquellen
- institutioneller Scope

## 3. `rules.yaml`

Hier stehen konkrete hochschulspezifische Prüfregeln.

Beispiele:

- lokaler Workload-Faktor
- Pflichtfelder eines Modulhandbuchs
- maximale oder minimale Prüfungsanforderungen
- lokale Regelungen zu Studienleistungen
- lokale Regeln zu Schlüsselkompetenzen

Jede verbindliche Regel muss quellenbelegt sein.

## 4. `terminology.yaml`

Hier werden nur sprachliche Konventionen definiert.

Beispiele:

- Fachbereich statt Fakultät
- Präsidium statt Rektorat
- Abteilung statt Dezernat

Terminologie verändert keine Bewertung.

## 5. `contacts.yaml`

Hier können lokale Zuständigkeiten und Weiterleitungen hinterlegt werden.

Kontaktinformationen sind keine Regelquellen.

## 6. `knowledge/`

Hier liegen dauerhaft wiederverwendbare institutionelle Regelquellen.

Nicht dauerhaft hinterlegen sollte man einzelne zu prüfende Fachprüfungsordnungen,
wenn diese nur Analysedokumente eines konkreten Prüfverfahrens sind.
