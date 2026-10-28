# Landesprofil – Template

Dieser Ordner ist die Vorlage für ein landesspezifisches Studiengang-CompAIgnon-Profil.

## Verwendung

Den Ordner `template/` kopieren und nach dem Bundesland benennen, z. B.:

```text
profiles/state/hessen/
profiles/state/nrw/
profiles/state/niedersachsen/
```

Anschließend:

1. Platzhalter in `profile.yaml` ersetzen.
2. landesspezifische Regelquellen in `knowledge/` ablegen.
3. konkrete, quellenbelegte Prüfregeln in `rules.yaml` ergänzen.
4. keine hochschulspezifischen Inhalte hier hinterlegen.

## Abgrenzung

Hierher gehören insbesondere:

- Landeshochschulgesetz
- Landesakkreditierungsverordnung
- zugehörige amtliche Begründungen
- weitere landesrechtlich einschlägige Regelungen

Hierher gehören nicht:

- Allgemeine Bestimmungen einer einzelnen Hochschule
- Fachprüfungsordnungen
- lokale Modulhandbuchvorgaben
- institutionelle Zuständigkeiten
- lokale Terminologie
- Ansprechpartner

Diese Inhalte gehören in `profiles/institution/`.
