# Institutionsprofil – Template

Dieser Ordner enthält die Vorlage für eine hochschulspezifische Studiengang-CompAIgnon-Konfiguration.

## Verwendung

Den Ordner `template/` kopieren und nach der Institution benennen, z. B.:

```text
profiles/institution/example-university/
profiles/institution/university-kassel/
```

Anschließend werden die Dateien befüllt:

- `profile.yaml` – Identität, Quellen und Geltungsbereich
- `rules.yaml` – hochschulspezifische Prüfregeln
- `terminology.yaml` – lokale Begriffe
- `contacts.yaml` – optionale Zuständigkeiten und Weiterleitungen
- `knowledge/` – institutionelle Regelquellen

## Hierher gehören

- Allgemeine Bestimmungen der Hochschule
- Rahmenprüfungsordnungen
- hochschulspezifische Praxismodulregelungen
- institutionelle Modulhandbuchvorgaben
- institutionelle Studiengangskonzept-Formulare
- offizielle interne Auslegungshinweise
- lokale Zuständigkeiten
- hochschulspezifische Terminologie

## Hierher gehören nicht

- Landeshochschulgesetz
- Landesakkreditierungsverordnung
- bundesweite KMK-Dokumente
- ESG / European Approach
- konkrete zu prüfende Fachprüfungsordnungen, sofern sie nur Analysedokumente sind
- einzelne Modulhandbücher des zu prüfenden Studiengangs

## Trennung von Regelquelle und Analysedokument

Eine studiengangsspezifische Prüfungsordnung kann im Einzelfall selbst
Prüfmaßstab für ein Modulhandbuch sein. Sie wird dadurch aber nicht automatisch
Teil des dauerhaften Institutionsprofils.

Dauerhaft in `knowledge/` sollten nur Quellen liegen, die für mehrere
Prüfvorgänge wiederverwendet werden sollen.
