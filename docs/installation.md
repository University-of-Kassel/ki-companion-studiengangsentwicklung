# Studiengang-CompAIgnon – Installation

Studiengang-CompAIgnon ist als konfigurierbares Repository aufgebaut.

Die Dateien sind nicht direkt als Anwendung ausführbar. Für die Nutzung werden
eine passende KI- bzw. Regel-Laufzeit und eine projektspezifische Integration benötigt.

## 1. Repository klonen

```bash
git clone <REPOSITORY_URL>
cd Studiengang-CompAIgnon
```

## 2. Regulatorische Basis prüfen

Unter `regulatory/de/knowledge/` müssen die für die gewünschte Nutzung
erforderlichen Referenzdokumente vorhanden sein.

Fehlende Dokumente werden nicht durch Modellwissen ersetzt.

## 3. Landesprofil anlegen

Kopiere:

```text
profiles/state/template/
```

nach beispielsweise:

```text
profiles/state/<state-name>/
```

Passe anschließend `profile.yaml` und `rules.yaml` an.

## 4. Institutionsprofil anlegen

Kopiere:

```text
profiles/institution/template/
```

nach:

```text
profiles/institution/<institution-id>/
```

Passe an:

- `profile.yaml`
- `rules.yaml`
- `terminology.yaml`
- `contacts.yaml`

und ergänze die institutionellen Knowledge-Dateien.

## 5. Profile aktivieren

Die konkrete technische Aktivierung hängt von der Laufzeitumgebung ab.

Mindestens müssen gemeinsam verfügbar sein:

- Studiengang-CompAIgnon Core
- `regulatory/de`
- genau ein passendes Landesprofil
- genau ein passendes Institutionsprofil
- die zu prüfenden Analysedokumente

## 6. Prüfung

Vor produktiver Nutzung sollte die Konfiguration mit den Fällen unter `tests/`
validiert werden.
