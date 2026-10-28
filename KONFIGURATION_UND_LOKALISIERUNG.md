# Studiengang CompAIgnon: Systemvoraussetzungen und Lokalisierung

Diese Anleitung beschreibt, was eine Hochschule zusätzlich zu diesem Repository benötigt und welche Dateien sie für den eigenen Einsatz anpassen muss.

## 1. Was Sie mit dem Repository erhalten

Studiengang CompAIgnon stellt einen fachlichen Baukasten für die quellengestützte Analyse von Studiengangdokumenten bereit:

- Systemprompt, Prüfmethodik und Ergebnisvorgaben unter `core/`;
- deklarative Prüf- und Steuerungslogik in YAML;
- übergreifende deutsche und europäische Referenzquellen unter `regulatory/de/`;
- Vorlagen für Landes- und Hochschulprofile;
- ausgearbeitete Profile für Hessen und die Universität Kassel;
- ein optionales Kasseler Regelmodul für Nachhaltigkeitsstudien;
- fiktive Beispiele sowie fachliche Testfälle mit erwarteten Ergebnissen.

**Das Repository enthält derzeit keine eigenständig ausführbare Anwendung.** Es liefert weder einen Server noch eine Benutzeroberfläche, eine ausführbare Prüf-Engine, einen Profil-Loader oder einen automatisierten Test-Runner. Die Dateien unter `core/rule-engine/` beschreiben die gewünschte Logik; sie führen diese nicht selbst aus. Auch YAML-Felder wie `inherits`, `validation` oder `action_on_violation` lösen allein keine technischen Aktionen aus.

Ein Download oder GitHub-Fork reicht daher noch nicht für den Betrieb. Sie benötigen eine KI-Umgebung und müssen dort die relevanten Anweisungen, Profile und Dokumente gezielt einbinden.

## 2. Welche Systeme werden zusätzlich benötigt?

### Technische Mindestfunktionen

| Komponente | Was Ihre Hochschule bereitstellen muss |
| --- | --- |
| KI-Umgebung | Eine Oberfläche oder Integration, die dauerhafte Arbeitsanweisungen und bereitgestellte Dokumente für die Analyse verwenden kann. |
| Sprachmodell | Ein Modell, das deutschsprachige Regeltexte, strukturierte Vorgaben und mehrere Studiengangdokumente verarbeiten kann. Die Eignung ist mit den Testfällen zu prüfen. |
| Anweisungseinbindung | Eine Möglichkeit, Core-Vorgaben als dauerhafte, gegenüber dem Prüfmaterial abgegrenzte Anweisungen bereitzustellen. Nur eine ZIP-Datei in einen Chat zu laden ist keine verlässliche Einrichtung. |
| Dokumentenzugriff | Zugriff auf die ausgewählten Profile, zugehörigen Regeln und vollständigen relevanten Quellenpassagen. Dateien im GitHub-Repository sind dem Modell nicht automatisch zugänglich. |
| Dokumentenverarbeitung | Zuverlässige Übernahme von PDF-Texten und Tabellen; bei Bildscans zusätzlich OCR. Auch YAML- und Markdown-Inhalte müssen lesbar eingebunden oder vorverarbeitet werden können. |
| Kontextverwaltung | Eine dokumentierte Auswahl des aktiven Landes- und Hochschulprofils und der jeweiligen Analysedokumente. Alte Prüffälle dürfen nicht unbemerkt weiterwirken. |
| Ergebnissicherung | Eine Möglichkeit, Ergebnisse einschließlich Quellenbezügen, offenen Punkten und verwendetem Konfigurationsstand zu speichern oder zu exportieren. |

OpenWebUI ist **keine Voraussetzung**. Das Paket schreibt auch keinen bestimmten Modellanbieter vor. Plattformunabhängigkeit bedeutet hier, dass die fachlichen Dateien übertragbar sind. Sie bedeutet nicht, dass jede Plattform sie unverändert importiert oder jedes Modell dieselbe Ergebnisqualität erreicht.

Für den gelieferten Baukasten sind keine festen Mindestwerte für RAM, GPU, Kontextfenster oder Modellgröße ausgewiesen. Diese hängen von Modell, Dokumentumfang und Integration ab. Ein konkretes Modell oder eine konkrete Plattform ist durch diese Anleitung nicht als geeignet zertifiziert.

### Zwei mögliche Betriebswege

| Betriebsweg | Zusätzlicher Einrichtungsbedarf | Eignung und Grenzen |
| --- | --- | --- |
| Konfiguration in einer vorhandenen KI-Oberfläche | Core als Anweisungen einrichten; aktive Profile und Quellen gezielt bereitstellen; Prüfmaterial separat hochladen; Ergebnisse fachlich kontrollieren. | Für einen betreuten Pilotbetrieb. Dateiformate, Dateizahl, Anweisungslänge und Kontextgrenzen der gewählten Umgebung müssen geprüft werden. |
| Eigene Integration über eine Modellschnittstelle | Zusätzlich Anwendungscode für Profilauswahl, Dateiladen, Quellenabruf, Dokumentenverarbeitung, Protokollierung und Ergebnisprüfung entwickeln. | Für wiederholbare Abläufe und technische Kontrollen. Der hierfür erforderliche Anwendungscode wird bislang nicht mitgeliefert. |

Für die Nutzung über eine vorhandene Oberfläche ist allein wegen dieses Repositories keine lokale Python- oder Node.js-Installation erforderlich. Bei einer eigenen Integration bestimmen Sie die Laufzeit und deren Bibliotheken selbst. Ein Modell-API-Zugang wird nur benötigt, wenn Ihr gewählter Betriebsweg ihn voraussetzt.

Bei extern betriebenen Modellen benötigt die Umgebung Zugang zum jeweiligen Dienst. Bei lokal betriebenen Modellen sind entsprechend geeignete Rechenressourcen und ein Modellbetrieb erforderlich. Git ist für das Lesen und manuelle Einrichten nicht zwingend: Das Repository kann auch als ZIP heruntergeladen werden.

### Fachliche und organisatorische Voraussetzungen

Benennen Sie eine fachlich verantwortliche Stelle für Quellen, Regeln und Freigabe, etwa im Qualitätsmanagement oder Prüfungsrecht, sowie eine technisch verantwortliche Stelle für die KI-Umgebung. Eine Person kann mehrere Rollen übernehmen.

Klären Sie vor dem Hochladen realer Unterlagen, welche Dokumente in der gewählten Umgebung verarbeitet werden dürfen. Personenbezogene Angaben und vertrauliche Anlagen sind nur einzubeziehen, soweit erforderlich und für diese Umgebung freigegeben. Zugangsdaten und vertrauliche Dokumente gehören nicht in ein öffentliches Repository.

## 3. Was bleibt erhalten, was wird lokalisiert?

| Bereich | Vorgehen bei Übernahme an eine andere Hochschule |
| --- | --- |
| `core/` | Als gemeinsame fachliche Grundlage übernehmen. Für eine reine Lokalisierung grundsätzlich unverändert lassen. Quellenbindung, Geltungsbereichsprüfung und Trennung zwischen Hinweis und Mangel beibehalten. |
| `regulatory/de/` | Für eine deutsche Hochschule als Ausgangspunkt prüfen. Quellenstand, Verfügbarkeit und Anwendbarkeit kontrollieren; nicht sämtliche enthaltenen Quellen pauschal aktivieren. |
| `profiles/state/template/` | Vorlage für ein eigenes Landesprofil kopieren, sofern kein geeignetes und geprüftes Landesprofil vorhanden ist. |
| `profiles/state/hessen/` | Nur für einen passenden hessischen Prüfkontext verwenden und zuvor den Quellenstand kontrollieren. Für andere Bundesländer nicht als Prüfmaßstab laden. |
| `profiles/institution/template/` | Vorlage für das Profil Ihrer Hochschule kopieren und ausfüllen. |
| `profiles/institution/university-kassel/` | Als Strukturbeispiel lesen. Kasseler Regeln, Quellen und Kontakte gelten nicht automatisch an Ihrer Hochschule. |
| `programme-features/` innerhalb eines Hochschulprofils | Nur für tatsächlich einschlägige, lokal belegte besondere Regelkomplexe verwenden. |
| `examples/example-university/` | Ausschließlich als fiktives Anschauungs- und Testmaterial verwenden. Enthaltene Zahlen sind keine realen Rechtsvorgaben. |
| `tests/` | Mitgelieferte Referenzfälle verwenden und um eigene Fälle ergänzen. |
| Studiengangdokumente | Pro Prüfverfahren bereitstellen und getrennt vom dauerhaften Regelbestand verwalten. |

Die Architektur ist delokalisiert; das Repository enthält dennoch reale Landes- und Hochschulprofile. Diese müssen nicht gelöscht werden. Entscheidend ist, dass Ihre Integration nur die für den jeweiligen Prüfkontext ausgewählten Profile aktiviert. Eine gemeinsame Wissenssammlung mit sämtlichen Hochschulprofilen kann zu ungewollter Vermischung führen.

Der mitgelieferte regulatorische Unterbau ist auf Deutschland ausgerichtet. Für Hochschulen außerhalb Deutschlands genügt es nicht, Hochschulname und Landeskennzeichen zu ersetzen; dort ist auch die regulatorische Basisschicht neu aufzubauen.

## 4. Einrichtung Schritt für Schritt

### Schritt 1: Eigene Arbeitsfassung anlegen

Erstellen Sie einen Fork oder eine lokale Kopie des Repositories. Dokumentieren Sie den übernommenen Release oder Commit. Bearbeiten Sie Kopien der Profilvorlagen, damit spätere Aktualisierungen der gemeinsamen Methodik nachvollziehbar bleiben.

Ein öffentliches Repository ist für den lokalen Betrieb nicht erforderlich. Veröffentlichen Sie nur Quellen und lokale Inhalte, deren Weitergabe zulässig ist. Beachten Sie dazu `NOTICE.md`: Die Repository-Lizenz erfasst fremde Knowledge-Dokumente nicht automatisch.

### Schritt 2: Landesprofil erstellen oder prüfen

Kopieren Sie `profiles/state/template/` nach `profiles/state/<landes-id>/`.

| Datei bzw. Ordner | Erforderliche Anpassung |
| --- | --- |
| `profile.yaml` | `profile.id`, Name, Landeskennzeichen und Landesname setzen; Quellen registrieren; Vererbung auf `regulatory/de` prüfen. |
| `rules.yaml` | `rules.profile` an die Profil-ID anpassen; belegte landesspezifische Regeln und Anwendungsbereiche ergänzen. |
| `knowledge/` | Ordner bei Bedarf anlegen und erforderliche Landesquellen ablegen. |

Typische Quellen sind Landeshochschulgesetz, geltende Studienakkreditierungsverordnung und deren Begründung. Ergänzen Sie besondere Quellen, beispielsweise zum Lehramt, nur soweit für Ihre Prüfgegenstände erforderlich.

Ersetzen Sie alle Platzhalter, etwa `<STATE_CODE>`, `<STATE_NAME>` und die Quellen-IDs. Jede `knowledge_file`-Angabe muss relativ zum jeweiligen Profil auf eine tatsächlich verfügbare Datei verweisen. Eine amtliche Begründung erläutert eine Regelung und ist entsprechend als auslegende Quelle zu behandeln.

### Schritt 3: Hochschulprofil erstellen

Kopieren Sie `profiles/institution/template/` nach `profiles/institution/<hochschul-id>/`.

| Datei bzw. Ordner | Was Sie eintragen |
| --- | --- |
| `profile.yaml` | Eindeutige Profil- und Hochschul-ID, Hochschulname und -typ, Bundesland, passendes Landesprofil unter `inherits`, lokale Quellen und deren Geltungsbereich. |
| `rules.yaml` | Zu Ihrer Hochschule passende Prüfregeln mit Quelle und konkreter Fundstelle; `rules.profile` auf die eigene Profil-ID setzen. |
| `terminology.yaml` | Hochschul-ID und tatsächlich gewünschte Begriffe, etwa Fakultät/Fachbereich oder Rektorat/Präsidium. |
| `contacts.yaml` | Hochschul-ID und freigegebene Zuständigkeiten, Funktionsadressen und Links; unbenötigte Platzhalter entfernen. |
| `knowledge/` | Wiederverwendbare lokale Quellen, beispielsweise Rahmenprüfungsordnungen, Allgemeine Bestimmungen und verbindliche Dokumentationsvorgaben. |

Registrieren Sie verbindliche Quellen unter `profile.sources`. Die Einträge unter `optional_sources` sind Hinweise auf mögliche Ergänzungen und ersetzen keine Quellenregistrierung. Passen Sie auch institutionelle Scope-Angaben auf Ihre eigene Hochschul-ID an.

Falls Sie entsprechend den ausgearbeiteten Profilen zusätzlich eine `knowledge-index.yaml` führen, halten Sie Quellen-ID, Pfad und Aktivierungsstatus mit `profile.yaml` konsistent. Die Templates erzeugen diesen Index nicht automatisch.

### Schritt 4: Lokale Prüfregeln fachlich festlegen

Prüfen Sie insbesondere, welche Vorgaben Ihre Quellen tatsächlich enthalten:

- Workload je Leistungspunkt und zulässige Abweichungen;
- Modulgrößen, Sollvorgaben und begründungsbedürftige Ausnahmen;
- Pflichtangaben und Feldbezeichnungen im Modulhandbuch;
- Prüfungsleistungen, Modulteilprüfungen und Studienleistungen;
- Schlüsselkompetenzen, Praxisanteile und Abschlussmodule;
- Anforderungen an Studiengangkonzept und Studienverlaufsplan;
- besondere Regeln für bestimmte Abschlüsse, Fachbereiche oder Studienformen.

Übernehmen Sie weder Kasseler Schwellenwerte noch die fiktiven Werte der Example University ungeprüft. Jede verbindliche Regel muss eine registrierte `source` und eine konkrete `citation` besitzen. Zahlenwerte ohne belegbare Grundlage bleiben deaktiviert.

Unterscheiden Sie Mussvorgaben, Sollvorgaben mit Ausnahmemöglichkeit und nichtnormative Qualitätswünsche. Letztere gehören unter `local_quality_checks` und dürfen nur einen `HINWEIS` begründen. Terminologie und Kontaktangaben ändern keine fachliche Bewertung.

Vorlagen, Beispielprofil und ausgearbeitete Profile zeigen teilweise unterschiedliche YAML-Strukturen, etwa für Pflichtfelder. Ein verbindliches maschinenlesbares Gesamtschema und ein entsprechender Validator werden nicht mitgeliefert. Wenn Sie eine eigene Integration entwickeln, müssen Sie diese Varianten ausdrücklich unterstützen oder vereinheitlichen; gültige YAML-Syntax allein gewährleistet noch keine korrekte Regelauswertung.

### Schritt 5: Besondere Studiengangsmerkmale berücksichtigen

Trennen Sie den Grundtyp (`programme_type`, etwa `bachelor`, `master` oder `state_examination`) von zusätzlichen Merkmalen unter `programme_features`, etwa Lehramtsbezug, Weiterbildung oder Joint Programme.

Für besondere lokale Regelkomplexe können Sie ein eigenes Feature-Profil unter `profiles/institution/<hochschul-id>/programme-features/<feature-id>/` anlegen. Das vorhandene Kasseler Nachhaltigkeitsprofil zeigt die Struktur mit `profile.yaml`, `rules.yaml`, `knowledge-index.yaml` und Quellenordner.

Aktivieren Sie ein Feature nur bei dokumentierter Anwendbarkeit oder ausdrücklicher, fachlich zutreffender Konfiguration. Ein ähnlicher Studiengangname genügt nicht. Erforderliche Parameter werden unter `feature_parameters` festgelegt; fehlende Angaben dürfen nicht geraten werden.

### Schritt 6: Dateien in die gewählte KI-Umgebung einbinden

Stellen Sie in dieser fachlichen Reihenfolge bereit:

1. Core: `system-prompt.md`, `methodology.md`, `output-specification.md`, die vier YAML-Dateien unter `core/rule-engine/` sowie die benötigten Ausgabevorlagen unter `core/templates/`.
2. `regulatory/de/` mit den einschlägigen Quellen und Metadaten.
3. Das ausgewählte Landesprofil mit Regeln und Quellen.
4. Das ausgewählte Hochschulprofil mit Regeln und Quellen.
5. Erforderliche optionale Feature-Profile.
6. Die Dokumente des konkreten Prüfverfahrens.

Diese Reihenfolge beschreibt die fachliche Zusammenstellung; sie wird vom Repository nicht automatisch ausgeführt. Ebenso bedeutet späteres Laden keinen pauschalen Vorrang einer Hochschulregel vor Landesrecht.

Die konkrete Aufteilung auf Anweisungsfelder, Wissenssammlungen oder einen eigenen Loader hängt von Ihrer Plattform ab. Prüfen Sie dabei:

- Werden Markdown, YAML und PDF tatsächlich eingelesen oder nur als Dateianhang angezeigt?
- Stehen Core, Profile und relevante Quellenauszüge während der Analyse zur Verfügung?
- Bleiben Tabellen, Modulgrenzen, Fußnoten und Fundstellen nachvollziehbar?
- Sind Quellenabruf und Kontextumfang für die Prüfung ausreichend?
- Bleiben inaktive Profile, historische Quellen und frühere Prüffälle ausgeschlossen?

Falls Ihre Umgebung RAG nutzt, also passende Textpassagen aus einer Wissenssammlung abruft, muss der Abruf anhand der aktiven Profile und Quellen begrenzt werden. Ein einzelner Suchtreffer belegt nicht, dass alle relevanten Regeln geprüft wurden. Bei großen Modulhandbüchern ist eine abschnittsweise Prüfung mit anschließendem dokumentübergreifendem Abgleich sinnvoll.

### Schritt 7: Prüfkontext festhalten

Dokumentieren Sie vor jeder Prüfung mindestens Hochschule, Bundesland, Abschluss, Studiengangtyp, relevante Zusatzmerkmale, Prüfdatum bzw. maßgeblichen Regelungszeitpunkt sowie Titel und Fassungen der Analysedokumente.

Halten Sie außerdem fest, welche Profile und Quellen aktiv sind. Fehlt eine wesentliche Kontextangabe, ist sie zu klären oder die daraus folgende Einschränkung im Ergebnis auszuweisen. Dies ist eine Einrichtungsanforderung; ein fertiges Konfigurationsformular wird nicht mitgeliefert.

## 5. Quellenbestand prüfen und pflegen

Eine vorhandene PDF und ein Eintrag wie `binding` bestätigen für sich genommen weder Aktualität noch Anwendbarkeit. Prüfen Sie vor dem Einsatz Quelle, Fassung, Inkrafttreten, Übergangsbestimmungen, Geltungsbereich und die Übereinstimmung zwischen Regel und Fundstelle.

Das Kasseler Profil enthält einen konkreten Abstimmungsbedarf: `knowledge/studiengangskonzept.pdf` ist vorhanden, während die Quelle im `profile.yaml` weiterhin als `planned_sources` mit `source_missing` und im `knowledge-index.yaml` als `missing` und deaktiviert geführt wird. Prüfen Sie Dokument und Metadaten vor einer Aktivierung. Die bloße Existenz der Datei hebt den deaktivierten Status nicht auf.

Historische Quellen unter `legacy/` sind nicht automatisch für aktuelle Verfahren geeignet. Die Musterrechtsverordnung ersetzt nicht die Auswahl der einschlägigen Landesverordnung. Die im Repository dokumentierten Quellenprüfungen ersetzen keine fortlaufende Pflege an Ihrer Hochschule.

Bei einer neuen Fassung aktualisieren Sie Quelldatei, Metadaten, Fundstellen und betroffene Regeln gemeinsam. Dokumentieren Sie Verantwortlichkeit und Prüfdatum. Eine fehlende Quelle ist als fehlende Prüfgrundlage auszuweisen und darf nicht durch Modellwissen ersetzt werden.

## 6. Funktion vor dem Einsatz nachweisen

Die Dateien unter `tests/` sind fachliche Referenzfälle. Sie können in der gewählten Umgebung manuell geprüft werden; ein automatisierter Testlauf ist bislang nicht enthalten.

| Prüfung | Erwartetes Verhalten |
| --- | --- |
| Mitgelieferter Workload-Test | Im ausdrücklich fiktiven Beispielprofil ergeben 5 Credits bei 25 Stunden je Credit 125 Stunden. Die angegebenen 200 Stunden werden als `ABWEICHUNG` erkannt. Der fiktive Faktor darf nicht auf reale Prüfungen übertragen werden. |
| Fehlende Lernergebnisse | Den Fall unter `tests/cases/module-description/` mit dem zugehörigen erwarteten Ergebnis prüfen. |
| Unklare Kompetenz-Prüfungs-Zuordnung | Den Fall unter `tests/cases/examination-design/` mit dem erwarteten Ergebnis abgleichen. |
| Lehramtsabgrenzung | Im Bachelor-Test ohne Lehramtsmerkmal bleibt der Lehramts-Trigger blockiert. |
| Eigene Quelle fehlt | Keine erfundene Regel oder Fundstelle; Einschränkung bzw. `NICHT PRÜFBAR` ausweisen. |
| Fremdes Hochschulprofil | Eine nur für Kassel belegte Anforderung wird nicht als Pflicht Ihrer Hochschule angewandt. |
| Lokaler Qualitätswunsch | Ausgabe als `HINWEIS`, ohne daraus einen Rechtsverstoß abzuleiten. |
| Reales Dokumentpaket | Ausgewählte Befunde, Zahlen und Quellenbezüge mit einer fachlichen Handprüfung vergleichen. |

Ergänzen Sie eigene Testfälle für zentrale lokale Regeln, zulässige Ausnahmen und eindeutig konforme Beispiele. Prüfen Sie nicht nur, ob das System Mängel findet, sondern auch, ob es unbegründete Beanstandungen vermeidet.

Dokumentieren Sie Modell, Umgebung, Konfigurationsstand, erwartete und tatsächliche Ergebnisse. Wiederholen Sie die relevanten Tests nach Änderungen an Modell, Core, Profilen, Quellen oder Dokumentenverarbeitung. Sprachmodellbasierte Auswertung setzt die deklarierte Prüflogik nicht automatisch zuverlässig durch.

## 7. Checkliste für den ersten fachlich betreuten Einsatz

- [ ] KI-Umgebung und Modell ausgewählt; erforderliche Dokumentverarbeitung geprüft.
- [ ] Landes- und Hochschulprofil vollständig ausgefüllt; Platzhalter entfernt.
- [ ] Vererbungsbezüge, IDs und Dateipfade konsistent.
- [ ] Quellen verfügbar, lesbar und für den Prüfkontext fachlich geprüft.
- [ ] Verbindliche Regeln mit Quelle, Fundstelle und zutreffendem Geltungsbereich belegt.
- [ ] Fremde Profile und nicht einschlägige Features ausgeschlossen.
- [ ] Core und relevante Konfiguration in der Umgebung wirksam eingebunden.
- [ ] Referenzfälle und eigene Positiv-, Negativ- und Ausnahmefälle fachlich bewertet.
- [ ] Verarbeitung realer Unterlagen für die gewählte Umgebung geklärt.
- [ ] Verantwortliche Stelle für Pflege und Ergebniskontrolle benannt.
- [ ] Erster realer Prüffall mit einer fachlichen Handprüfung abgeglichen.

Die Ergebnisse unterstützen die fachliche Vorprüfung. Verbindliche Entscheidungen, Freigaben und erforderliche Rechtsklärungen verbleiben bei den zuständigen Stellen der Hochschule. Die Repository-Fassung weist insbesondere noch offene Quellenprüfungen und ausstehende End-to-End-Tests mit realen Analysedokumenten aus.

## 8. Weiterführende Dateien im Repository

- [Installation](docs/installation.md)
- [Konfiguration](docs/configuration.md)
- [Architektur](docs/architecture.md)
- [Landesprofil erstellen](docs/creating-a-state-profile.md)
- [Hochschulprofil erstellen](docs/creating-an-institution-profile.md)
- [Knowledge-Dateien hinzufügen](docs/adding-knowledge-files.md)
- [Programme-Features](docs/programme-features.md)
- [Referenzfälle](tests/README.md)
- [Lizenz- und Quellenhinweise](NOTICE.md)
