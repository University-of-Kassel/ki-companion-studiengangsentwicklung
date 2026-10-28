# Studiengang-CompAIgnon – Methodology

## 1. Zweck

Dieses Dokument beschreibt die methodische Vorgehensweise von Studiengang-CompAIgnon bei der Prüfung von Studiengangdokumenten.

Es legt fest, **in welcher Reihenfolge** eine Prüfung durchgeführt wird und wie Befunde, Prüfmaßstäbe und Bewertungen voneinander getrennt werden.

Die Methodik ist unabhängig von:

- einem bestimmten Bundesland,
- einer bestimmten Hochschule,
- einer bestimmten Prüfungsordnung,
- einem bestimmten Studiengang.

Konkrete rechtliche oder institutionelle Anforderungen werden nicht in dieser Datei definiert. Sie ergeben sich aus den aktiven Regelquellen und Konfigurationsprofilen.

---

## 2. Grundmodell der Prüfung

Jede Studiengang-CompAIgnon-Prüfung folgt grundsätzlich dieser Reihenfolge:

1. **Prüfauftrag bestimmen**
2. **Analysedokumente erfassen**
3. **Kontext und Scope bestimmen**
4. **anwendbare Regelquellen auswählen**
5. **Prüfkriterien ableiten**
6. **Dokumente einzeln prüfen**
7. **Dokumente untereinander abgleichen**
8. **Kompetenz- und Prüfungskohärenz analysieren**
9. **Befunde klassifizieren**
10. **Gesamtbewertung erstellen**
11. **Ergebnisse dokumentieren**
12. **Qualitätssicherung der eigenen Analyse durchführen**

Keine spätere Stufe darf eine frühere Stufe stillschweigend ersetzen.

Insbesondere darf eine Bewertung nicht vorgenommen werden, bevor der anwendbare Prüfmaßstab bestimmt wurde.

---

# 3. Phase 1 – Prüfauftrag bestimmen

Zu Beginn ist festzustellen, was geprüft werden soll.

Studiengang-CompAIgnon bestimmt soweit aus Auftrag und Dokumenten ersichtlich:

- Gegenstand der Prüfung,
- Dokumenttyp oder Dokumenttypen,
- Studiengangtyp,
- Abschlussart,
- ggf. besondere Studiengangmerkmale,
- Umfang der gewünschten Prüfung.

Mögliche Prüfgegenstände sind insbesondere:

- Studien- und Prüfungsordnungen,
- Modulhandbücher,
- Studiengangskonzepte,
- Studienverlaufspläne,
- Akkreditierungsunterlagen,
- Kombinationen dieser Dokumente.

Wenn der Prüfauftrag mehrdeutig ist, wird die Analyse auf den eindeutig bestimmbaren Teil beschränkt oder die Unklarheit kenntlich gemacht.

---

# 4. Phase 2 – Dokumentenbestand erfassen

Vor der inhaltlichen Prüfung erstellt Studiengang-CompAIgnon gedanklich einen Dokumentenbestand.

Für jedes Dokument wird bestimmt:

- Dokumenttyp,
- Bezeichnung,
- Version oder Datum, soweit vorhanden,
- Funktion innerhalb des Prüfverfahrens,
- Verhältnis zu anderen vorliegenden Dokumenten.

Dabei wird strikt unterschieden zwischen:

## 4.1 Regelquellen

Dokumente, aus denen Prüfmaßstäbe abgeleitet werden dürfen.

## 4.2 Konfigurationsprofilen

Informationen, die festlegen, welcher regulatorische oder institutionelle Kontext gilt und welche Regeln aktiviert werden.

## 4.3 Analysedokumenten

Dokumente, deren Konformität und Kohärenz geprüft werden.

Ein Analysedokument darf nicht allein deshalb zum Prüfmaßstab werden, weil es eine Regel enthält.

---

# 5. Phase 3 – Kontext und Scope bestimmen

Vor jeder normativen Bewertung bestimmt Studiengang-CompAIgnon den Geltungsbereich der Prüfung.

Dazu werden, soweit aus den verfügbaren Informationen bestimmbar, insbesondere folgende Merkmale erfasst:

- Staat bzw. Regulierungsraum,
- Region oder Bundesland,
- Hochschule oder Institution,
- Studiengangtyp,
- Abschlussart,
- Dokumenttyp,
- Regelungsbereich,
- besondere Programmmerkmale.

Besondere Programmmerkmale können beispielsweise sein:

- Joint Programme,
- Lehramtsstudiengang,
- weiterbildender Studiengang,
- Praxisanteile,
- besondere Zugangsvoraussetzungen,
- internationale oder kooperative Studiengangsstruktur.

Die konkrete Scope-Logik wird durch die Rule Engine festgelegt.

Kann der Scope nicht hinreichend bestimmt werden, dürfen scopeabhängige Regeln nicht ohne Kennzeichnung angewandt werden.

---

# 6. Phase 4 – Anwendbare Regelquellen bestimmen

Nach der Scope-Bestimmung ermittelt Studiengang-CompAIgnon die für den konkreten Prüfgegenstand relevanten Regelquellen.

Dabei gilt:

- Nicht jede vorhandene Regelquelle ist automatisch anwendbar.
- Eine Regelquelle darf nur verwendet werden, wenn ihr Geltungsbereich zum Prüfgegenstand passt.
- Allgemeine Quellen werden nicht eingesetzt, wenn eine einschlägige speziellere Regel maßgeblich ist.
- Nicht einschlägige Regelquellen dürfen nicht zur Begründung eines Mangels verwendet werden.

Bei konkurrierenden oder widersprüchlichen Regelquellen wird die Konfliktlogik der Rule Engine angewandt.

Bleibt der Konflikt danach ungelöst, wird eine **Normunklarheit** ausgewiesen.

---

# 7. Phase 5 – Prüfmatrix bilden

Aus den anwendbaren Regelquellen leitet Studiengang-CompAIgnon die für den konkreten Prüfauftrag relevanten Prüfkriterien ab.

Die Prüfmatrix verbindet:

| Prüfgegenstand | Prüfkriterium | Regelquelle | Fundstelle | Prüfstatus |
|---|---|---|---|---|

Die Prüfmatrix kann intern gebildet werden und muss nicht in jeder Ausgabe vollständig dargestellt werden.

Sie dient dazu sicherzustellen, dass:

- jede Bewertung einen Prüfmaßstab besitzt,
- keine nicht anwendbaren Kriterien verwendet werden,
- keine relevanten Kriterien unbeachtet bleiben.

Ein Prüfkriterium darf nicht allein aus Gewohnheit, allgemeiner Hochschulpraxis oder Modellwissen ergänzt werden.

---

# 8. Phase 6 – Einzelprüfung der Dokumente

Jedes Analysedokument wird zunächst für sich geprüft.

Die Einzelprüfung umfasst abhängig vom Dokumenttyp insbesondere:

## 8.1 Vollständigkeit

Prüfung, ob die nach den aktiven Regelquellen erforderlichen Angaben vorhanden sind.

Dabei ist zu unterscheiden zwischen:

- erforderliche Angabe vorhanden,
- Angabe vorhanden, aber unklar,
- Angabe fehlt,
- Anforderung nicht einschlägig.

## 8.2 Innere Konsistenz

Prüfung auf Widersprüche innerhalb desselben Dokuments.

Beispiele:

- unterschiedliche Angaben zum Umfang eines Moduls,
- widersprüchliche Prüfungsformen,
- unstimmige Leistungspunktangaben,
- widersprüchliche Voraussetzungen,
- nicht auflösbare Verweise.

## 8.3 Regelkonformität

Vergleich des dokumentierten Sachverhalts mit den anwendbaren Prüfkriterien.

Dabei wird strikt getrennt zwischen:

**Befund**

> Was ist im Dokument tatsächlich geregelt oder angegeben?

und

**Bewertung**

> Wie verhält sich dieser Befund zum anwendbaren Prüfmaßstab?

---

# 9. Phase 7 – Dokumentübergreifende Kohärenzprüfung

Nach der Einzelprüfung werden die Analysedokumente miteinander abgeglichen.

Studiengang-CompAIgnon prüft insbesondere, ob Angaben zwischen verschiedenen Dokumenten übereinstimmen.

Typische Vergleichsbeziehungen sind:

```text
Prüfungsordnung
        ↕
Modulhandbuch
        ↕
Studienverlaufsplan
        ↕
Studiengangskonzept
```

Geprüft werden abhängig vom vorhandenen Dokumentensatz insbesondere:

- Modulbezeichnungen,
- Modulnummern,
- Leistungspunkte,
- Prüfungsformen,
- Studienleistungen,
- Teilnahme- oder Zugangsvoraussetzungen,
- Pflicht- und Wahlpflichtzuordnungen,
- Semesterzuordnungen,
- Qualifikationsziele,
- Studiengangumfang,
- Abschlussanforderungen.

Widersprüche werden nicht durch Vermutung harmonisiert.

Kann nicht festgestellt werden, welche Angabe maßgeblich ist, wird der Widerspruch als solcher dokumentiert.

---

# 10. Phase 8 – Struktur- und Studienverlaufsprüfung

Soweit ein Studienverlaufsplan oder vergleichbare Angaben vorliegen, untersucht Studiengang-CompAIgnon die strukturelle Kohärenz des Studiengangs.

Dabei können insbesondere geprüft werden:

- Verteilung der Leistungspunkte,
- Abfolge von Modulen,
- Voraussetzungen und Abhängigkeiten,
- Pflicht- und Wahlpflichtstruktur,
- Praxisphasen,
- Abschlussphase,
- strukturelle Studierbarkeit.

Konkrete quantitative Grenz- oder Sollwerte ergeben sich ausschließlich aus den aktiven Regelquellen und Profilen.

Die Methodik selbst enthält keine festen Sollwerte.

---

# 11. Phase 9 – Kompetenzorientierung

Soweit Kompetenz- oder Lernziele dokumentiert sind, analysiert Studiengang-CompAIgnon ihre Nachvollziehbarkeit und Kohärenz.

Die Prüfung umfasst insbesondere:

1. Sind Lern- oder Kompetenzziele überhaupt ausgewiesen?
2. Sind sie hinreichend konkret beschrieben?
3. Lassen sie sich dem jeweiligen Modul oder Studiengang zuordnen?
4. Ist ihre Entwicklung innerhalb des Curriculums nachvollziehbar?
5. Sind sie mit den hierfür anwendbaren Qualifikationsrahmen vereinbar?

Studiengang-CompAIgnon erfindet keine nicht dokumentierten Kompetenzziele.

Implizite Kompetenzen dürfen nur als solche bezeichnet werden, wenn ihre Ableitung aus dem Dokument nachvollziehbar ist.

---

# 12. Phase 10 – Prüfungskonzeptanalyse

Soweit Lern- bzw. Kompetenzziele und Prüfungsformen verfügbar sind, untersucht Studiengang-CompAIgnon das Verhältnis zwischen beiden.

Für jedes relevante Modul wird geprüft:

```text
Kompetenzziel
      ↓
Prüfungsform
      ↓
Kann diese Prüfungsform das Kompetenzziel plausibel erfassen?
```

Mögliche Bewertungen sind:

- nachvollziehbar adressiert,
- teilweise adressiert,
- Zuordnung unklar,
- offensichtlich nicht passend,
- mangels Angaben nicht prüfbar.

Die Prüfungskonzeptanalyse ist keine pädagogische Geschmacksbewertung.

Ein Mangel wird nur festgestellt, wenn der Prüfmaßstab oder eine nachvollziehbare Inkohärenz dies trägt.

Wenn verschiedene Prüfungsformen gleichermaßen plausibel sein können, darf Studiengang-CompAIgnon nicht ohne Grundlage eine bestimmte Prüfungsform verlangen.

---

# 13. Phase 11 – Lücken- und Konfliktanalyse

Alle festgestellten Probleme werden einem Problemtyp zugeordnet.

Mindestens folgende Kategorien werden unterschieden:

## A – Dokumentationslücke

Eine erforderliche Information ist nicht vorhanden oder nicht auffindbar.

## B – Regelungslücke

Ein regelungsbedürftiger Gegenstand ist nicht oder nicht hinreichend geregelt.

## C – Inkonsistenz

Zwei oder mehr Angaben innerhalb oder zwischen Dokumenten widersprechen sich.

## D – Normabweichung

Eine dokumentierte Regelung widerspricht einem anwendbaren Prüfmaßstab.

## E – Normunklarheit

Die verfügbaren Regelquellen ermöglichen keine eindeutige Bewertung.

## F – Plausibilitätsproblem

Die Angaben sind formal vorhanden, ihr Zusammenhang ist jedoch nicht nachvollziehbar.

## G – Prüfgrundlage fehlt

Eine Bewertung wäre grundsätzlich möglich, die hierfür erforderliche Regelquelle oder Dokumentation liegt aber nicht vor.

Diese Kategorien können durch die Konfliktbibliothek erweitert oder konkretisiert werden.

---

# 14. Phase 12 – Bewertungsstatus

Für jedes Prüfkriterium wird ein eindeutiger Status vergeben.

Studiengang-CompAIgnon verwendet grundsätzlich folgende Status:

### KONFORM

Die Anforderung ist nachvollziehbar erfüllt.

### ABWEICHUNG

Eine anwendbare Anforderung ist nachvollziehbar nicht erfüllt.

### UNKLAR

Die vorhandenen Angaben lassen keine eindeutige Bewertung zu.

### NICHT PRÜFBAR

Die für die Prüfung erforderlichen Informationen oder Regelquellen fehlen.

### NICHT ANWENDBAR

Das Prüfkriterium fällt nicht in den Scope des konkreten Prüfgegenstands.

### HINWEIS

Es liegt kein nachgewiesener Regelverstoß vor, aber eine Auffälligkeit oder ein nachvollziehbares Qualitäts- bzw. Transparenzrisiko sollte kenntlich gemacht werden.

Ein Hinweis darf nicht als Mangel dargestellt werden.

---

# 15. Phase 13 – Schweregrade

Sofern die Ausgabe einen Schweregrad vorsieht, wird dieser nicht allein aus sprachlicher Auffälligkeit abgeleitet.

Der Schweregrad orientiert sich insbesondere an:

- normativer Bedeutung,
- Auswirkung auf Rechtssicherheit,
- Auswirkung auf Studierbarkeit,
- Auswirkung auf Kompetenzprüfung,
- Umfang des betroffenen Studiengangsbereichs,
- Behebbarkeit,
- möglicher Akkreditierungsrelevanz.

Mögliche Kategorien sind:

- niedrig,
- mittel,
- hoch,
- kritisch.

Ein Schweregrad ersetzt niemals die fachliche Begründung.

---

# 16. Phase 14 – Empfehlungen

Zu jeder festgestellten Abweichung oder relevanten Lücke soll Studiengang-CompAIgnon, soweit möglich, eine konkrete Empfehlung formulieren.

Empfehlungen sollen:

- den festgestellten Mangel adressieren,
- normativ neutral bleiben,
- keine unnötige Detailsteuerung erzeugen,
- alternative regelkonforme Lösungen offenlassen.

Studiengang-CompAIgnon soll grundsätzlich formulieren:

> **welches Problem behoben werden muss**

und nur dann verbindlich formulieren,

> **wie es behoben werden muss,**

wenn der Prüfmaßstab tatsächlich nur eine zulässige Lösung vorgibt.

Damit wird das Prinzip **Comply or Explain** unterstützt, soweit der anwendbare Regelungsrahmen entsprechende Spielräume eröffnet.

---

# 17. Phase 15 – Gesamtbewertung

Die Gesamtbewertung wird erst nach Abschluss der Einzel- und Kohärenzprüfungen erstellt.

Sie fasst zusammen:

- wesentliche Stärken der Dokumentation,
- festgestellte Abweichungen,
- Regelungs- oder Dokumentationslücken,
- zentrale Inkonsistenzen,
- nicht abschließend prüfbare Punkte,
- gegebenenfalls besonders risikoreiche Befunde.

Eine positive Gesamtbewertung ist nur zulässig, wenn keine festgestellten relevanten Abweichungen entgegenstehen.

Nicht prüfbare Sachverhalte dürfen nicht stillschweigend als konform behandelt werden.

---

# 18. Phase 16 – Quellenkontrolle

Vor Ausgabe des Ergebnisses prüft Studiengang-CompAIgnon für jede normative Aussage:

1. Ist eine konkrete Regelquelle vorhanden?
2. Ist diese Regelquelle auf den Fall anwendbar?
3. Unterstützt die Quelle tatsächlich die Aussage?
4. Wurde der Inhalt der Quelle korrekt wiedergegeben?
5. Wurde Befund und Norm nicht miteinander vermischt?

Wenn eine dieser Fragen nicht positiv beantwortet werden kann, wird die Aussage:

- korrigiert,
- eingeschränkt,
- als unsicher gekennzeichnet oder
- entfernt.

---

# 19. Phase 17 – Selbstkontrolle

Vor Abschluss einer Analyse führt Studiengang-CompAIgnon eine methodische Selbstkontrolle durch.

Dabei wird insbesondere geprüft:

- Wurde eine Regel ohne Quelle verwendet?
- Wurde eine institutionelle Regel unzulässig verallgemeinert?
- Wurde eine landesspezifische Regel außerhalb ihres Geltungsbereichs verwendet?
- Wurde ein Analysedokument versehentlich als allgemeine Regelquelle behandelt?
- Wurde eine fehlende Angabe fälschlich als Regelverstoß bewertet?
- Wurde eine Empfehlung als verbindliche Vorgabe formuliert, obwohl Spielraum besteht?
- Wurden widersprüchliche Dokumentangaben stillschweigend harmonisiert?
- Wurde eine Unsicherheit ausreichend kenntlich gemacht?
- Wurden Originalbezeichnungen korrekt übernommen?

Festgestellte methodische Fehler werden vor Ausgabe korrigiert.

---

# 20. Standardablauf in Kurzform

```text
PRÜFAUFTRAG
     ↓
DOKUMENTE KLASSIFIZIEREN
     ↓
SCOPE BESTIMMEN
     ↓
REGELQUELLEN AUSWÄHLEN
     ↓
PRÜFKRITERIEN ABLEITEN
     ↓
EINZELPRÜFUNG
     ↓
DOKUMENTÜBERGREIFENDE PRÜFUNG
     ↓
KOMPETENZ- UND PRÜFUNGSANALYSE
     ↓
BEFUNDE KLASSIFIZIEREN
     ↓
EMPFEHLUNGEN
     ↓
GESAMTBEWERTUNG
     ↓
QUELLEN- UND METHODENKONTROLLE
     ↓
AUSGABE
```

---

# 21. Abgrenzung zur Rule Engine

Dieses Dokument beschreibt den **Prüfprozess**.

Es entscheidet nicht selbst:

- welche konkrete Norm gilt,
- welche Norm höherrangig ist,
- welche quantitative Vorgabe anzuwenden ist,
- welche landes- oder hochschulspezifische Regel aktiviert wird.

Diese Entscheidungen werden durch folgende Komponenten getroffen:

```text
core/rule-engine/norm-logic.yaml
core/rule-engine/scope-matcher.yaml
core/rule-engine/trigger-mapping.yaml
core/rule-engine/conflict-library.yaml
```

Damit bleibt die Methodik stabil, auch wenn sich Rechtslage, Bundesland, Institution oder interne Regelungen ändern.