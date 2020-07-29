---
lab:
    title: 'Kursleiteranleitung'
    module: 'Modul XX: Power Apps Build'
---

# PL-900: Microsoft Power Platform – Grundlagen
## Kursleiteranleitung

# Umgebungen

Die Kursteilnehmer benötigen jeweils eine CDS-Umgebung (Common Data Service), um die Kursarbeit abzuschließen. Umgebungen können von den Kursteilnehmern während des Kurses bereitgestellt oder vor der Durchführung des Kurses mit Anmeldeinformationen bereitgestellt werden, die den Kursteilnehmern vor der ersten Übung übergeben wurden.

Die Umgebungen erfordern keine spezifischen Konfigurationsüberlegungen, ein einfaches CDS *ohne Beispieldaten* ist alles was benötigt wird.

Wir empfehlen, die Labs als Kursteilnehmer vor der Schulungsdurchführung abzuschließen. 

* Wenn Sie mit den Übungen vertraut sind, können Sie den Kurs effizienter abhalten.
* Lösungskomponenten, die während dieser Übung erstellt wurden, können nach Bedarf für Ihre Demos verwendet werden. Demos sind nicht erforderlich, aber manche Menschen finden sie nützlich. Bearbeiten Sie ein paar Themen, mit denen Sie sich am wohlsten fühlen.

# Übersicht

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in papierform aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Apps und führen Automatisierungen durch, um es dem Verwaltungs- und Sicherheitspersonal des Bellows College zu ermöglichen, den Zugang zu den Gebäuden auf dem Campus zu verwalten und zu steuern. 

Einige Kursteilnehmer fühlen sich möglicherweise überfordert, alle Anpassungen innerhalb des Lösungsframeworks vorzunehmen. Es ist jedoch wichtig, gute Gewohnheiten zu entwickeln, um sie nach dem Kurs mitzubringen.

> [WICHTIG!]
> Wir bauen Komponenten, die für Power Platform-Lösungen typisch sind. Es gibt nur minimale Abhängigkeiten, aber das **Lab 1** ist unerlässlich, da die restlichen Übungen ein Datenmodell verwenden, das während dieses Labs erstellt wurde. Während des Labs importierte Beispieldaten machen das Erstellen und Testen der Apps einfacher, realistischer und zuordenbarer.

Abgesehen vom Common Data Model, das in Lab 1 erstellt wurde, gibt es keine Abhängigkeiten zwischen verschiedenen Labs. Die Kursleiter sollten das Ziel eines jeden Labs klar erläutern und wichtige Lösungskomponenten und -techniken darlegen. Die Kursteilnehmer sollten dann ermutigt werden, ihre eigenen Lösungen zu entwerfen und zu entwickeln, ohne die schrittweisen Anweisungen für jede Übung hinzuzuziehen.

## Komponenten

Fertiggestellte Komponenten sind für *alle* Übungen verfügbar. Dazu gehören Canvas-Apps, modellgesteuerte Apps, Power Automation-Flows, Power BI-Pbix-Dateien, Beispieldaten und Datenimportzuordnungen sowie Komplettlösungen, die sowohl verwaltet, als auch nicht verwaltet exportiert werden. Die Komponenten sollten nicht als Abkürzung zum Abschluss der Übung verwendet werden. Stattdessen sind sie als Demo-Tool und als allgemeiner Bezugspunkt nützlich.

Da alle Labs im Kurs vom Datenmodell abhängen, ist das Modell als eigenständige Lösung [CampusDataModel_1_0_0_1.zip](..\Allfiles\CampusDataModel_1_0_0_1.zip) verfügbar. Es kann in eine frische Umgebung importiert werden, gefolgt von Übung 3 in Lab 1 (Datenimport). Dies wird als Ausgangspunkt für die Kursteilnehmer dienen, die das Lab nicht abschließen konnten. Das vorgefertigte Datenmodell gibt diesen Kursteilnehmern die Möglichkeit, die restlichen Übungen nachzuholen und fortzusetzen. 

## Herausforderungen

Am Ende jedes Labs steht eine Reihe von Herausforderungen zur Verfügung. Zu den Herausforderungen gehören in der Regel realistischere Szenarien, da die Kursübungen aus Zeitgründen vereinfacht werden. Die Herausforderungen umfassen auch fortgeschrittenere Themen, die einige Kursteilnehmer möglicherweise hilfreich finden.

Verwenden Sie die Herausforderungen, um eine Diskussion über reale Szenarien zu initiieren und wie Techniken, die während der Übungen erlernt wurden, angewendet werden können, um die Herausforderungen zu lösen.

Labs
======================

## Lab 01 – Datenmodell

Ein solides Datenmodell ist eine Grundlage für die auf der Plattform aufgebauten Apps. In diesem Lab richten wir eine Umgebung ein und erstellen Lösungen, um Änderungen nachzuverfolgen. Wir erstellen auch ein Datenmodell, um die Anforderungen zu unterstützen und Beispieldaten zu importieren.

Themen zur Diskussion:

* Welche Tools würden Sie verwenden?
* Wie gehen Sie beim Modellieren vor?
* Wo beginnen Sie?
* Beziehungen 
* Bewährte Verfahren zur Implementierung des Datenmodells in CDS
* Einbringen von Common Data Model-Entitäten (wie etwa Kontakte) – Was soll einbezogen werden?
* Dev/Test-Beispieldatensätze – Wie viel ist genug? Bewährte Verfahren zum Erstellen von Dev/Test-Datensätzen.

### Herausforderungen

* Würden Sie in Betracht ziehen, die *Termin*-Aktivität als Teil der Lösung zu verwenden? Was würde sich ändern?

  > Ein Termin oder eine andere Aktivitätsentität erfordert ein erweitertes Verstehen von Konzepten wie Aktivitätsparteien, Bezugsfeld usw. Einige der Maker-Tools sind möglicherweise noch nicht in der Lage, mit diesen zu arbeiten, und möglicherweise sind komplexe Problemumgehungen erforderlich.

* Wie wird erzwungen, dass das geplante Ende nach dem geplanten Start liegt? 

  > Ein gutes Thema zur Diskussion von Geschäftsregeln 

* Fügen Sie Unterstützung für mehrere Besprechungen während eines einzelnen Besuchs hinzu.

  > m:n-Beziehungen und damit verbundene Herausforderungen

* Schützen Sie den Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter.

  >  Eine gute Einführung in den internen vs. externen Datenzugriff, Benutzer vs. Kontakte, authentifiziert vs. anonym. Erwähnen Sie möglicherweise den Ansatz von Power Apps-Portalen, Benutzer für den Zweck auch als Kontakte zu behandeln

* Bestimmte Gebäude dürfen nur nach Genehmigung des Managements betreten werden. Was würde der Genehmigungsprozess im Datenmodell ändern?

  > Diskussion von Geschäftsprozessabläufen und Genehmigungen zur Powerautomation als Techniken zur Einführung des menschlichen Faktors in die Prozesse

## Lab 02 Canvas-App

Dieses Lab besteht aus zwei Teilen, die sich an unterschiedliche Benutzertypen richten.

In Teil 1 dieses Labs erstellen Sie eine Canvas-App in Power Apps, mit der Universitätsmitarbeiter Besuche für ihre Gäste verwalten können.

In Teil 2 dieses Labs erstellen Sie eine Canvas-App in Power Apps, die das Sicherheitspersonal an den Gebäudeeingängen verwendet, um die Besucher schnell zu validieren und zu registrieren.

Diskussionsthemen

- Tablet im Vergleich zu Telefon-Formfaktor. Dynamische Layouts (bald in Canvas verfügbar).
- Wie wirkt sich die Zielgruppe auf das App-Design aus?
- Wie können Kenntnisse in Excel App-Herstellern zugute kommen (traditionelle prozedurale Programmierung im Vergleich zu Eigenschaften und Ausdruckssyntax von Power Apps)?

- Welcher Connector soll verwendet werden? So ist der CDS-Connector jetzt in Power Apps integriert.

- App-Überprüfung – jeden Tag neue Metriken. Testen Sie die App erneut.

- Barrierefreiheit – Was macht eine gut zugängliche App aus?

### Herausforderungen

**Teil 1**

* Kalenderansicht aller Besuche und Filtern nach Datumsbereich

  > Komponenten, Diskussion über Steuerelemente von Drittanbietern, effektive Datenfilterung

* Möglichkeit zum Erstellen und Verwalten von Kontakten als Teil der App

  > Mehrere Bildschirme, Navigation zwischen ihnen

* So zeigen Sie mehrere Besprechungen während eines einzelnen Besuchs an

  > So navigieren Sie in Beziehungen und Eigenschaften

**Teil 2**

* Wie vermeide ich die manuelle Eingabe des Besuchscodes?

  > Verwenden Sie die Scanfunktionen für mobile Geräte, wenn der Besucher einen Barcode mit dem Code anzeigen kann. Gute Diskussion darüber, wie und wann Barcodes für die Besucher generiert werden sollen.

* Fügen Sie eine Gebäudevalidierung für den Besuch hinzu.

  > Fügen Sie dem Barcode Informationen zum Gebäude hinzu. Verwenden Sie möglicherweise GPS-Funktionen. 

* Hinzufügen einer Validierung der tatsächlichen Besuchszeit im Vergleich zur geplanten Besuchszeit hinzu (zu früh, zu spät usw.).

  > Manipulieren von Datum/Uhrzeit in Formeln, komplexerer Logik.

* Fügen Sie einen detaillierten Status des Besuchs hinzu, wie etwa eine. E-Mail-Anzeige und -Prüfung für den Besucher, Grund für die Verweigerung des Gebäudezugangs usw.

  > Zugriff auf die Eigenschaften verwandter Entitäten, erstellen einer ansprechenden Benutzeroberfläche

* Wie würden Sie mit den Anforderungen mehrerer Gebäude/Besprechungen/Überprüfungen während eines einzelnen Campusbesuchs umgehen? Zum Beispiel kann jemand den Campus für einen Tag besuchen und an diesem Tag Mitarbeiter in mehreren Gebäuden zu unterschiedlichen Tageszeiten treffen. Wie verhält es sich mit einer einzelnen Besprechung mit mehreren externen Teilnehmern? Würden Sie in Betracht ziehen, die *Termin*-Entität in die Lösung einzubeziehen? 

  > Hierbei handelt es sich um ein interessantes, aber potenziell komplexes und langwieriges Thema. Erwägen Sie, eine Diskussion einzuleiten und den Kursteilnehmern eine Art von „Hausaufgaben“ zu geben. Besprechen Sie, wie Power Apps einen iterativen Ansatz zum Erstellen von Apps ermöglichen, d. h. einfach starten und im Laufe der Zeit erweitern.

## Lab 03 Power Automate

In diesem Lab erstellen Sie Power Automate-Flows, um verschiedene Segmente des Campus-Managements zu automatisieren. Zusätzlich zu Lab 1 ist für dieses Lab eine App erforderlich, die in Teil 1 von Lab 2 erstellt wurde. Dies ist für die Durchführung des Testens der Automatisierung notwendig (Auslösen von Prozessen durch Eingabe neuer Daten)

Diskussionsthemen

* Flows in Lösungen
* CDS-Connectors (Standard vs. aktuelle Umgebung)
* Andere Automatisierungsmittel in Power Platform (Echtzeit-Workflow, Automatisierung von Benutzeroberflächen)
* Menschliche Interaktion mit Flows – Genehmigungsprozesse
* Testen der Prozesse während der Erstellung
* Die Flows teilen
* Laufende Prozesse überwachen

### Herausforderungen

* Erstellungsinformationen hinzufügen und dem Benachrichtigungsflow zuordnen.

  > Verwenden Sie möglicherweise Bilder, Karten und externe Dienste, um diese Informationen bereitzustellen.

* Können Sie einen Barcode für den Besuchscode generieren? Wann könnte das nützlich sein?

  > Barcodes können zusätzliche Informationen wie den Namen des Gebäudes enthalten und von einer anderen App gescannt werden, ohne dass eine manuelle Dateneingabe erforderlich ist. Wie werden die Barcodes generiert? Verwenden Sie Barcode-Schriftarten? Bilder? Externe Dienste?

* Wie kann eine benutzerfreundliche Datumsformatierung im E-Mail-Text sichergestellt werden?

  > Lokalisierung in Power Apps, einschließlich länderspezifischer Formatierung, Währungen und Zeitzonen.

* Ist es möglich, eine Tabelle mit Übernachtungsinformationen zu erstellen und nur eine einzige E-Mail zu senden?

  > Verwenden von Variablen, Erstellen komplexerer Ausdrücke und Bearbeiten des E-Mail-Formats.

## Lab 04 Power BI

In dieser Übung erstellen Sie ein Power BI-Dashboard, das Daten zu den Campusbesuchen visualisiert.

Diskussionsthemen

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Standort?
-   Wie starte ich das Design? Wie bewegt man sich über die leere Canvas hinaus
-   Verbindung zu Datenquellen, Erstellen und Verfeinern des Datenmodells 
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?
-   Veröffentlichen und Freigeben der Berichte
-   Barrierefreiheit in Power BI beim Erstellen interaktiver Berichte

### Herausforderungen

* Dashboards und Berichte mit Campus- und Gebäudeplänen.

  > Fügen Sie den Berichten Karten, Bilder und externe Daten hinzu

* Berichten und Analysieren von Besuchsmustern und -trends.

  > Diskussion der Analyse- und Datenverarbeitungsfunktionen von Power BI.

* Visualisierung der Besucher, die länger als geplant blieben

  > So machen Sie Berichte ansprechender. Sprechen Sie über das Einbetten von Power Apps in Power BI, um Datenbearbeitungsfunktionen als Reaktion auf die vorgestellten Berichte hinzuzufügen.

* Streaming Power BI in Quasi-Echtzeitverarbeitung für einen großen Campus.

  > Dies ist ein komplexes Thema, und die Lösungen wären für die meisten Kursteilnehmer höchstwahrscheinlich unerreichbar. Es ist jedoch wichtig, Datenalterung, Momentaufnahmen im Vergleich zu Streams, Frequenz von Datenaktualisierungen und veraltete Daten im Allgemeinen zu erörtern.

## Modellgesteuerte Lab 05-App

In diesem Lab erstellen Sie eine modellgesteuerte Power Apps-App, mit der die Campus-Mitarbeiter im Backoffice  die Besuchsdatensätze für den gesamten Campus verwalten können.

Themen zur Diskussion:

* Modellgetriebene Apps als Teil einer Lösung
* Modellgetriebene im Vergleich zu Canvas Power Apps. Zielgruppe und App-Ziele.
* Was macht eine gute Sitemap aus?
* Was soll für eine bestehende Entität in eine App aufgenommen werden?
* Apps und Rollen, Sicherheit in CDS, UI-Trimmen in modellgetriebenen Apps
* Anpassen des Datenmodells im Vergleich zum Anpassen der modellgesteuerten App

### Herausforderungen

* Spezifische Ansichten und Formulare für Besuche und Gebäude auswählen

  > Feinabstimmung der App für die Zielgruppe Erstellen nützlicher Ansichten und Formulare

* Das Sicherheitspersonal arbeitet üblicherweise in einem einzigen Gebäude. Welche einfache Möglichkeit könnten Sie ihnen bieten, Besuche nur für ein ausgewähltes Gebäude anzuzeigen?

  > Personalisierung in modellgesteuerten Apps, wie etwa persönliche Ansichten. Raster und Filtern. Vorab erstellte feste Ansichten, wenn die Anzahl der Gebäude gering ist. Unterraster (in dem Formular „Gebäude“)

* Wie würden Sie den Zugriff auf bestimmte Entitäten beschränken, wie etwa sollten Gebäude für alle Mitarbeiter außer den Administratoren schreibgeschützt sein?

  > Sicherheitsrollen, Trimmen der Benutzeroberfläche. Sprechen Sie möglicherweise über Verweisdaten (im Besitz von Benutzern vs. Entitäten im Besitz von Organisationen).

* Welche Dashboards würden Sie der App hinzufügen?

  > Integrierte Dashboards, eingebettete Canvas und eingebettetes Power BI