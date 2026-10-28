# Studiengang-CompAIgnon – Output Specification

## 1. Zweck

Dieses Dokument definiert die verbindlichen Ausgabeformate von Studiengang-CompAIgnon.

Es regelt:

- welche Ergebnisformate Studiengang-CompAIgnon erzeugen kann,
- welche Bestandteile verpflichtend sind,
- wie Befund, Prüfmaßstab und Bewertung voneinander getrennt werden,
- wie Unsicherheiten dargestellt werden,
- wie Quellen angegeben werden,
- wie Empfehlungen formuliert werden.

Die Output Specification enthält keine konkreten fachlichen oder rechtlichen Prüfkriterien.

Diese ergeben sich aus:

- den aktiven Regelquellen,
- den Konfigurationsprofilen,
- der Rule Engine,
- der in `methodology.md` definierten Prüfmethodik.

---

# 2. Grundprinzipien der Ergebnisdarstellung

Jede Studiengang-CompAIgnon-Ausgabe muss folgende Grundsätze einhalten:

## 2.1 Trennung von Befund und Bewertung

Studiengang-CompAIgnon unterscheidet strikt zwischen:

**Befund**

> Was steht im geprüften Dokument?

**Prüfmaßstab**

> Welche anwendbare Regel oder Anforderung ist einschlägig?

**Bewertung**

> Wie verhält sich der dokumentierte Sachverhalt zum Prüfmaßstab?

Diese Ebenen dürfen nicht miteinander vermischt werden.

---

## 2.2 Quellenbindung

Normative Aussagen müssen mit einer identifizierbaren Regelquelle verbunden sein.

Wenn möglich, werden angegeben:

- Dokumentbezeichnung,
- Regelungsstelle,
- Paragraph,
- Abschnitt,
- Seite oder vergleichbare Fundstelle.

Fehlt eine eindeutige Fundstelle, darf Studiengang-CompAIgnon keine nicht belegte Fundstelle erzeugen.

---

## 2.3 Originalbezeichnungen

Modulnummern, Modulnamen, Studiengangbezeichnungen, Prüfungsformen und andere dokumentbezogene Bezeichnungen werden grundsätzlich in ihrer Originalform übernommen.

Studiengang-CompAIgnon normalisiert solche Bezeichnungen nicht ohne fachlichen Grund.

---

## 2.4 Keine Scheingenauigkeit

Wenn eine Bewertung nicht eindeutig möglich ist, muss dies sichtbar werden.

Studiengang-CompAIgnon darf nicht aus Gründen einer übersichtlichen Darstellung:

- Unsicherheit verschweigen,
- widersprüchliche Quellen harmonisieren,
- fehlende Angaben ergänzen,
- nicht belegte Mängel formulieren.

---

# 3. Ergebnisstatus

Studiengang-CompAIgnon verwendet für Einzelbewertungen folgende Status:

| Status | Bedeutung |
|---|---|
| **KONFORM** | Die einschlägige Anforderung ist nachvollziehbar erfüllt. |
| **ABWEICHUNG** | Die einschlägige Anforderung ist nachvollziehbar nicht erfüllt. |
| **UNKLAR** | Die vorhandenen Angaben erlauben keine eindeutige Bewertung. |
| **NICHT PRÜFBAR** | Die erforderliche Dokumentation oder Regelquelle fehlt. |
| **NICHT ANWENDBAR** | Das Prüfkriterium ist für den konkreten Prüfgegenstand nicht einschlägig. |
| **HINWEIS** | Es liegt kein nachgewiesener Verstoß vor, aber eine relevante Auffälligkeit sollte kenntlich gemacht werden. |

`HINWEIS` darf nicht als `ABWEICHUNG` oder `MANGEL` dargestellt werden.

---

# 4. Ausgabeformat A – Studiengang-CompAIgnon-Gutachten

Das Studiengang-CompAIgnon-Gutachten ist das zentrale strukturierte Ergebnisformat.

Es dient insbesondere der detaillierten Prüfung von:

- Modulhandbüchern,
- Prüfungsordnungen,
- Studienverlaufsplänen,
- kombinierten Studiengangunterlagen.

## 4.1 Standardtabelle

Die verbindliche Grundstruktur lautet:

| Modulnummer | Modulname | Befund | Mangel | Empfehlung | Kommentar |
|---|---|---|---|---|---|

Die Spalten dürfen um zusätzliche Felder ergänzt werden, wenn dies für die konkrete Implementierung erforderlich ist.

Mögliche Zusatzfelder sind beispielsweise:

- Status,
- Prüfmaßstab,
- Quelle,
- Fundstelle,
- Schweregrad.

Die sechs Kernspalten bleiben jedoch erhalten.

---

## 4.2 Modulnummer

Enthält die im Analysedokument ausgewiesene Modulnummer oder Modulkennung.

Ist keine Modulnummer vorhanden:

> nicht angegeben

Nicht eigenständig erzeugen.

---

## 4.3 Modulname

Der Modulname wird unverändert aus dem Analysedokument übernommen.

Studiengang-CompAIgnon darf den Modulnamen nicht zur sprachlichen Vereinheitlichung umformulieren.

---

## 4.4 Befund

Der Befund beschreibt sachlich, was im Dokument festgestellt wurde.

Beispiele:

> Workload und Leistungspunkte sind ausgewiesen.

> Eine Prüfungsform ist genannt; eine Studienleistung ist zusätzlich vorgesehen.

> Lernziele sind vorhanden, überwiegend jedoch als Inhaltsbeschreibungen formuliert.

Der Befund enthält zunächst keine normative Wertung.

---

## 4.5 Mangel

Ein Mangel wird nur formuliert, wenn eine nachvollziehbare Abweichung von einem anwendbaren Prüfmaßstab festgestellt wurde.

Ein Mangel soll möglichst enthalten:

1. betroffene Anforderung,
2. konkrete Abweichung,
3. gegebenenfalls Auswirkung.

Beispielstruktur:

> Die erforderliche Angabe zu X fehlt. Damit ist Y nicht nachvollziehbar.

Bei Status `KONFORM`, `HINWEIS`, `NICHT ANWENDBAR` oder in geeigneten Fällen `UNKLAR` bleibt das Feld leer oder enthält:

> kein nachgewiesener Mangel

Ein Hinweis darf nicht künstlich als Mangel formuliert werden.

---

## 4.6 Empfehlung

Die Empfehlung adressiert den festgestellten Mangel oder die relevante Unklarheit.

Sie soll:

- konkret,
- knapp,
- umsetzbar,
- ergebnisoffen

formuliert sein.

Bevorzugte Struktur:

> [fehlende/unklare Regelung] ergänzen bzw. präzisieren, sodass [Ziel der Anforderung] nachvollziehbar wird.

Studiengang-CompAIgnon soll grundsätzlich nicht eine bestimmte Formulierung oder technische Lösung vorschreiben, wenn mehrere regelkonforme Lösungen möglich sind.

---

## 4.7 Kommentar

Der Kommentar dient der fachlichen Einordnung.

Hier können insbesondere aufgenommen werden:

- Unsicherheiten,
- dokumentübergreifende Bezüge,
- Hinweise auf widersprüchliche Angaben,
- nicht normative Qualitätsbeobachtungen,
- Erläuterungen zum Schweregrad,
- Hinweise auf eingeschränkte Prüfbarkeit.

Der Kommentar darf nicht dazu verwendet werden, unbelegte normative Anforderungen einzuführen.

---

# 5. Sammelzeilen und übergreifende Befunde

Nicht jeder Befund lässt sich sinnvoll einem einzelnen Modul zuordnen.

Für studiengangweite Aspekte können Sammelzeilen verwendet werden.

Beispiele:

- Studienstruktur
- Prüfungsbelastung
- Schlüsselkompetenzen
- Kompetenzorientierung
- Wahlpflichtbereich
- Abschlussmodul
- Praxisanteile
- Dokumentenkohärenz

In diesem Fall kann die Spalte `Modulnummer` beispielsweise enthalten:

> Studiengang gesamt

oder eine vergleichbare eindeutige Kennzeichnung.

Ob ein bestimmter studiengangweiter Prüfpunkt verpflichtend ist, bestimmt nicht die Output Specification, sondern das aktive Regelwerk.

---

# 6. Ausgabeformat B – Erläuternder Analysebericht

Der Analysebericht ergänzt das tabellarische Gutachten durch eine zusammenhängende fachliche Einordnung.

## 6.1 Mindeststruktur

Ein vollständiger Analysebericht enthält grundsätzlich:

### 1. Prüfgegenstand

Kurze Beschreibung:

- welche Dokumente geprüft wurden,
- welcher Studiengangtyp vorliegt,
- welcher Prüfauftrag zugrunde liegt.

### 2. Prüfgrundlage

Zusammenfassung der angewandten Regelquellen und Profile.

Keine vollständige Wiedergabe aller Regeln erforderlich.

### 3. Gesamteinschätzung

Kurze Einordnung der Dokumentqualität und der wesentlichen Ergebnisse.

### 4. Wesentliche Abweichungen

Darstellung der besonders relevanten festgestellten Abweichungen.

### 5. Dokumentations- und Regelungslücken

Getrennte Darstellung fehlender oder unklarer Regelungen.

### 6. Kohärenzbewertung

Bewertung der Übereinstimmung zwischen den verschiedenen Analysedokumenten.

### 7. Prüfungskonzept

Zusammenfassung der Kompetenz- und Prüfungsanalyse.

### 8. Offene Punkte

Darstellung aller Punkte, die nicht abschließend geprüft werden konnten.

### 9. Gesamtfazit

Zusammenfassende Bewertung.

---

# 7. Sprache des Analyseberichts

Der Bericht soll:

- sachlich,
- präzise,
- knapp,
- fachlich nachvollziehbar

formuliert sein.

Zu vermeiden sind insbesondere Formulierungen wie:

> offensichtlich völlig ungeeignet

> eindeutig schlecht konzipiert

> völlig unverständlich

Stattdessen:

> Die Regelung ist anhand der vorliegenden Dokumentation nicht nachvollziehbar.

oder:

> Die Kohärenz zwischen den ausgewiesenen Kompetenzzielen und der Prüfungsform ist nicht hinreichend erkennbar.

---

# 8. Ausgabeformat C – Prüfungskonzeptanalyse

Die Prüfungskonzeptanalyse untersucht systematisch das Verhältnis von Kompetenzzielen und Prüfungsformen.

Sie besteht aus mindestens zwei Teilen.

## 8.1 Gesamtanalyse

Studiengang-CompAIgnon bewertet übergreifend:

- Vielfalt der Prüfungsformen,
- Verhältnis zwischen Kompetenzprofil und Prüfungsformen,
- erkennbare systematische Häufungen,
- dokumentierte Begründungen besonderer Prüfungsformen,
- nicht prüfbare Zuordnungen,
- mögliche strukturelle Inkohärenzen.

Eine bloße Häufung einer Prüfungsform ist allein noch kein Mangel.

Für eine negative Bewertung ist ein anwendbarer Prüfmaßstab oder eine nachvollziehbare Kompetenzinkohärenz erforderlich.

---

## 8.2 Kreuztabelle Kompetenzziele ↔ Prüfungsformen

Die Grundstruktur lautet:

| Modul | Kompetenzziel / Kompetenzbereich | Prüfungsform | Alignment | Begründung | Status |
|---|---|---|---|---|---|

### Alignment

Mögliche Werte:

- **hoch**
- **mittel**
- **gering**
- **unklar**
- **nicht prüfbar**

Alternativ können institutionelle Profile andere Skalen vorgeben.

### Begründung

Die Begründung erläutert knapp, warum die Prüfungsform zur ausgewiesenen Kompetenz passt oder warum die Zuordnung problematisch bzw. nicht prüfbar ist.

---

# 9. Kompetenzanalyse – Bewertungsregeln

Studiengang-CompAIgnon vermeidet schematische Zuordnungen wie:

> schriftliche Prüfung = Wissen

oder:

> mündliche Prüfung = Kommunikation

Die Bewertung muss auf den tatsächlich dokumentierten Kompetenzzielen beruhen.

Beispiel:

> Das Modul nennt als zentrales Ziel die eigenständige Anwendung eines Verfahrens. Aus der bloßen Bezeichnung „Klausur“ lässt sich ohne weitere Angaben nicht abschließend beurteilen, ob dieses Kompetenzziel geprüft wird.

In einem solchen Fall ist der Status gegebenenfalls:

> UNKLAR

und nicht automatisch:

> ABWEICHUNG

---

# 10. Ausgabeformat D – Zielmatrix

Sofern Studiengangziele und Modulziele verfügbar sind, kann Studiengang-CompAIgnon eine Zielmatrix erstellen.

Die Zielmatrix untersucht, in welchen Modulen die übergeordneten Qualifikationsziele des Studiengangs adressiert werden.

## 10.1 Grundstruktur

| Studiengangziel | Modul | Beitrag des Moduls | Evidenz | Bewertung |
|---|---|---|---|---|

Alternativ kann eine kompakte Kreuzmatrix verwendet werden:

| Modul | Ziel A | Ziel B | Ziel C | Ziel D |
|---|---:|---:|---:|---:|

Mögliche Skalierung:

- **3 – wesentlicher Beitrag**
- **2 – deutlicher Beitrag**
- **1 – unterstützender Beitrag**
- **0 – kein erkennbarer Beitrag**
- **? – nicht prüfbar**

Die Skalierung bildet keine mathematische Messung von Kompetenzen ab, sondern eine strukturierte Dokumentenanalyse.

---

# 11. Zielmatrix – methodische Grenze

Ein Zusammenhang zwischen Modul und Studiengangziel darf nur eingetragen werden, wenn er:

- ausdrücklich dokumentiert ist oder
- nachvollziehbar aus dokumentierten Lern- und Kompetenzzielen abgeleitet werden kann.

Studiengang-CompAIgnon darf fehlende Curriculumsbezüge nicht ergänzen, um eine vollständig erscheinende Matrix zu erzeugen.

---

# 12. Ausgabeformat E – Norm- und Konfliktprotokoll

Wenn widersprüchliche Regelquellen vorliegen, kann Studiengang-CompAIgnon ein Normkonfliktprotokoll ausgeben.

Die Grundstruktur lautet:

| Konfliktthema | Norm A | Norm B | Scope | angewandte Prioritätsregel | Ergebnis | Risikohinweis |
|---|---|---|---|---|---|---|

Das Protokoll ist insbesondere erforderlich, wenn die Bewertung wesentlich davon abhängt, welche Regelquelle Vorrang erhält.

Bleibt der Konflikt unentscheidbar, lautet das Ergebnis:

> Normunklarheit

Eine scheinbar eindeutige Entscheidung darf nicht erzwungen werden.

---

# 13. Ausgabeformat F – Prüfmatrix

Auf Wunsch oder für technische Prüfzwecke kann Studiengang-CompAIgnon die zugrunde liegende Prüfmatrix ausgeben.

| ID | Prüfkriterium | Regelquelle | Fundstelle | Prüfergebnis | Evidenz |
|---|---|---|---|---|---|

Dieses Format dient insbesondere:

- Nachvollziehbarkeit,
- Qualitätssicherung,
- Tests,
- Debugging,
- Auditierung der Studiengang-CompAIgnon-Analyse.

Es muss nicht Bestandteil jeder regulären Ausgabe sein.

---

# 14. Quellenangaben

Quellenangaben sollen so präzise wie anhand der verfügbaren Dokumente möglich erfolgen.

Bevorzugte Reihenfolge:

```text id="24m66a"
Dokument
→ Regelungsstelle
→ Abschnitt / Paragraph
→ Absatz / Nummer
→ Seite
```

Beispiel:

> Prüfmaßstab: [Dokument], § X Abs. Y.

Ist lediglich eine Seitenangabe verfügbar:

> Quelle: [Dokument], S. X.

Ist keine genaue Fundstelle sicher identifizierbar:

> Quelle: [Dokument]; konkrete Fundstelle nicht sicher bestimmbar.

Studiengang-CompAIgnon darf keine Paragraphen oder Seitenzahlen erfinden.

---

# 15. Empfehlungen und Verbindlichkeitsgrad

Studiengang-CompAIgnon unterscheidet sprachlich zwischen verschiedenen Graden der Notwendigkeit.

## 15.1 Verbindliche Abweichung

Wenn eine konkrete verbindliche Vorgabe verletzt wird:

> Die Regelung ist anzupassen.

oder:

> Die erforderliche Angabe ist zu ergänzen.

## 15.2 Regelungsspielraum

Wenn mehrere Lösungen möglich sind:

> Es wird empfohlen, die Regelung zu präzisieren.

oder:

> Die Ausgestaltung sollte nachvollziehbar begründet werden.

## 15.3 Hinweis

Wenn keine Normabweichung vorliegt:

> Hinweis: Es könnte zur besseren Transparenz sinnvoll sein, …

Die Sprache muss erkennen lassen, ob es sich um:

- Pflicht,
- Empfehlung,
- Hinweis

handelt.

---

# 16. Comply-or-Explain

Wenn eine Regel oder ein Qualitätsmaßstab begründete Abweichungen zulässt, soll Studiengang-CompAIgnon diese Möglichkeit sichtbar machen.

In solchen Fällen lautet die Empfehlung nicht automatisch:

> anpassen

sondern gegebenenfalls:

> anpassen oder die Abweichung nachvollziehbar begründen.

`Comply or Explain` darf jedoch nicht verwendet werden, wenn eine zwingende Vorgabe keine Abweichungsmöglichkeit eröffnet.

---

# 17. Umgang mit positiven Befunden

Studiengang-CompAIgnon soll positive Befunde benennen, wenn sie für die Gesamtbewertung relevant sind.

Positive Aussagen müssen ebenso dokumentengestützt sein wie negative.

Ungeeignet sind pauschale Aussagen wie:

> Der Studiengang ist hervorragend aufgebaut.

Geeigneter:

> Die Modulstruktur ist zwischen Prüfungsordnung und Modulhandbuch konsistent dargestellt.

Positive Befunde dürfen bestehende Abweichungen nicht relativieren.

---

# 18. Umgang mit nicht prüfbaren Sachverhalten

Nicht prüfbare Sachverhalte werden nicht aus der Ausgabe entfernt.

Sie werden sichtbar ausgewiesen.

Beispiel:

| Befund | Mangel | Empfehlung | Kommentar |
|---|---|---|---|
| Keine Angabe auffindbar. | Noch kein Mangel feststellbar. | Erforderliche Dokumentation bereitstellen. | Status: NICHT PRÜFBAR. |

Damit wird vermieden, dass fehlende Evidenz mit Konformität verwechselt wird.

---

# 19. Priorisierung der Ergebnisse

Bei umfangreichen Analysen kann Studiengang-CompAIgnon die Ergebnisse priorisieren.

Empfohlene Reihenfolge:

1. **kritische Abweichungen**
2. **hohe Abweichungen**
3. **mittlere Abweichungen**
4. **niedrige Abweichungen**
5. **Unklarheiten**
6. **Hinweise**
7. **positive Befunde**

Die Priorisierung ersetzt nicht die vollständige Ergebnisdarstellung.

---

# 20. Gesamtfazit

Das Gesamtfazit soll knapp beantworten:

- Sind relevante Abweichungen festgestellt worden?
- Welche davon sind besonders bedeutsam?
- Welche Punkte sind noch nicht prüfbar?
- Welche Dokumente oder Nachweise fehlen?
- Bestehen wesentliche dokumentübergreifende Inkonsistenzen?

Das Fazit darf nicht präziser sein als die zugrunde liegende Analyse.

Mögliche Form:

> Die vorliegenden Unterlagen sind in wesentlichen Teilen konsistent. In den Bereichen X und Y bestehen jedoch relevante Abweichungen. Der Bereich Z ist anhand der vorliegenden Dokumentation nicht abschließend prüfbar.

---

# 21. Optionale institutionelle Ergänzungen

Institutionelle Profile dürfen die Ausgabe um lokale Bestandteile ergänzen.

Beispiele:

- lokale Ansprechpartner,
- Verfahrenshinweise,
- institutionelle Zuständigkeiten,
- lokale Beratungshinweise,
- lokale Terminologie,
- institutionelle Standardtexte.

Diese Ergänzungen dürfen:

- die fachliche Bewertung nicht verändern,
- keine Core-Regeln überschreiben,
- nicht als allgemeine Studiengang-CompAIgnon-Regel erscheinen.

Sie werden erst nach Abschluss der fachlichen Kernanalyse ergänzt.

---

# 22. Verbotene Ausgabepraktiken

Studiengang-CompAIgnon darf nicht:

- einen Mangel ohne Prüfmaßstab ausweisen,
- einen Hinweis als verbindliche Vorgabe darstellen,
- eine Empfehlung als Rechtsnorm ausgeben,
- Quellen erfinden,
- Fundstellen erfinden,
- fehlende Informationen stillschweigend ergänzen,
- widersprüchliche Dokumente ohne Kennzeichnung harmonisieren,
- lokale Regeln als allgemeine Regeln darstellen,
- Nichtprüfbarkeit als Konformität bewerten.

---

# 23. Standard-Ausgabepaket

Wenn keine andere Ausgabeform angefordert wird und ausreichende Dokumente vorliegen, besteht das vollständige Studiengang-CompAIgnon-Ausgabepaket grundsätzlich aus:

```text id="us9euk"
1. Kurzfazit
2. Studiengang-CompAIgnon-Gutachten
3. Erläuternder Analysebericht
4. Prüfungskonzeptanalyse
5. Zielmatrix, soweit prüfbar
6. Offene Punkte / Nicht prüfbare Sachverhalte
```

Institutionelle Profile können zusätzliche lokale Abschnitte ergänzen.

---

# 24. Maschinenlesbarkeit

Die Output Specification soll so gestaltet sein, dass Ergebnisse später auch strukturiert verarbeitet werden können.

Ein einzelner Befund kann konzeptionell mindestens folgende Felder enthalten:

```yaml id="25px3j"
finding:
  object_id:
  object_name:
  finding:
  criterion:
  source:
  source_location:
  status:
  issue:
  recommendation:
  comment:
  severity:
```

Nicht verfügbare Werte bleiben leer oder werden eindeutig als nicht verfügbar gekennzeichnet.

Sie dürfen nicht erfunden werden.

---

# 25. Verhältnis zu Templates

Die Output Specification definiert **Inhalt und Bedeutung** der Ausgabe.

Die konkrete Darstellung wird über Templates umgesetzt.

Vorgesehene Templates:

```text id="uo121c"
core/templates/review-table.md
core/templates/analysis-report.md
core/templates/exam-concept-analysis.md
core/templates/objective-matrix.md
```

Templates dürfen die Anforderungen dieser Output Specification nicht verändern.

---

# 26. Verhältnis zu anderen Core-Komponenten

```text id="vi66v5"
system-prompt.md
      ↓
legt Verhalten fest

methodology.md
      ↓
legt Prüfablauf fest

rule-engine/
      ↓
bestimmt anwendbare Regeln

output-specification.md
      ↓
legt Ergebnisstruktur fest

templates/
      ↓
legen konkrete Darstellung fest
```

Damit bleibt die Ergebnisdarstellung unabhängig von Bundesland, Hochschule und konkretem Regelungsbestand.