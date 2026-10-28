# Studiengang-CompAIgnon – Programme-Features

## Zweck

Programme-Features bilden **optionale institutionelle Regelkomplexe** ab, die nicht für alle
Studiengänge einer Hochschule gelten, aber auch nicht auf nur einen einzelnen Studiengang
beschränkt sind.

Sie schließen die Lücke zwischen dem allgemeinen Institutionsprofil und dem konkreten
Analysedokument.

## Ablage

```text
profiles/institution/<institution>/programme-features/<feature>/
├── profile.yaml
├── rules.yaml
├── knowledge-index.yaml
├── README.md
└── knowledge/
```

## Aktivierung

Ein Feature wird aktiviert, wenn der Prüfkontext es ausdrücklich enthält oder die
Analysedokumente einen hinreichend eindeutigen normativen Bezug zeigen.

Nicht ausreichend sind:

- bloße thematische Ähnlichkeit,
- ein einzelnes fachlich passendes Modul,
- Vermutungen aufgrund des Studiengangnamens.

## Parameter

Features können mehrere Anwendungsformen besitzen. Diese werden nicht als getrennte
Studiengangtypen modelliert, sondern über `feature_parameters`.

```yaml
programme_features:
  - sustainability_studies
feature_parameters:
  sustainability_studies:
    integration_mode: inas_a
```

## Vererbungslogik

Die Ladefolge lautet:

```text
Core
→ regulatory/de
→ State Profile
→ Institution Profile
→ aktive Programme-Features
→ Analysedokumente
```

Das Feature **ergänzt** die übergeordneten Schichten. Es ersetzt sie nicht.

## Quellenbindung

Auch Feature-Regeln brauchen eine konkrete Quelle und Fundstelle. Eine Feature-Quelle darf
nur dann als Norm verwendet werden, wenn das Feature im konkreten Studiengang tatsächlich
gilt.

## Beispiel Universität Kassel

`nachhaltigkeitsstudien` verwendet die AB NaS als hochschulweite, aber optionale
Regelquelle. Die vier Integrationsmodi sind:

- `minor`
- `inas_a`
- `inas_b`
- `elective_focus`
