---
lab:
    title: 'Lab: Power BI'
    module: 'Modul 5: Erste Schritte mit Power BI'
---

# Modul 5: Erste Schritte mit Power BI
## Lab: Power BI

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

Weiterführende Schritte des Lab
======================

Wir werden die folgenden Schritte ausführen, um das Power BI-Dashboard zu entwerfen und zu erstellen:

-   Eine Verbindung zum Common Data Service herstellen 
-   Die Daten so transformieren, dass sie benutzerfreundliche Beschreibungen für die zugehörigen Datensätze enthalten (Lookups)
-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und veröffentlichen
-   Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden
-   Mobile Ansicht erstellen


## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Standort?
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten zu den Besuchen zu analysieren?

Übung Nr. 1: Power BI-Bericht erstellen 
===============================

**Ziel:** In dieser Übung erstellen Sie, basierend auf Daten aus der Common Data Service-Datenbank, einen Power BI-Bericht.

Aufgabe 1: Daten vorbereiten
---------------------------

1.  Finden Sie die URL Ihrer Organisation heraus.

    * Navigieren Sie zum Power Platform Admin Center unter https://admin.powerplatform.com.
    * Wählen Sie auf der linken Navigationsseite „Umgebungen“ aus, und öffnen Sie dann die Zielumgebung.
    * Klicken Sie im Bereich **Details** mit der rechten Maustaste auf **Umgebungs-URL**, und wählen Sie dann **Linkadresse kopieren** aus.
2. Wenn Sie Power BI Desktop nicht installiert haben, navigieren Sie zu https://aka.ms/pbidesktopstore, um die Power BI-App herunterzuladen und zu installieren.

3. Öffnen Sie Power BI Desktop, und melden Sie sich an, wenn Sie dazu aufgefordert werden.

4. Wählen Sie **Daten abrufen** aus.

5. Wählen Sie auf der linken Seite **Power Platform** und dann **Common Data Service** aus, und klicken Sie dann auf **Verbinden**.

6. Fügen Sie die zuvor kopierte Umgebungs-URL in das Feld **Server-URL** ein, und drücken Sie dann auf **OK**.

7. Erweitern Sie den Knoten **Entitäten**, wählen Sie die Entitäten **bc_Building** und **bc_Visit** aus, und klicken Sie auf **Laden**.

8. Klicken Sie in der linken vertikalen Symbolleiste auf das Symbol für **Modell**.

9. Ziehen Sie die Spalte **bc_buildingid** aus der Tabelle **bc_Building** in die Spalte **bc_building** in der Tabelle **bc_Visit**. Dadurch wird eine Beziehung zwischen zwei Entitäten erstellt, mit denen Power BI verwandte Daten anzeigen kann.

10. Wählen Sie in der linken Symbolleiste das Symbol **Bericht** aus.

11. Erweitern Sie den Knoten **bc_Visits** im Bereich **Felder**.

12. Klicken Sie auf die Schaltfläche mit den drei Punkten (...) neben **bc_Visits**, und wählen Sie **Neue Spalte** aus.

13. Stellen Sie die App wie folgt fertig.

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    , und drücken Sie die EINGABETASTE. Dadurch wird den Besuchsdaten ein neues Feld mit dem Gebäudenamen hinzugefügt.

14. Klicken Sie neben dem Feld auf ..., und wählen Sie **Umbenennen** aus. Geben Sie **Gebäude** als Feldnamen ein.

15. Klicken Sie neben dem Feld **bc_visitid** auf ..., und wählen Sie **Umbenennen** aus. Geben Sie **Besuche** als Feldnamen ein.

16. Klicken Sie auf ... neben dem Feld **bc_scheduledstart**, und wählen Sie **Umbenennen** aus. Geben Sie **Start** als Feldnamen ein.

17. Speichern Sie in Bearbeitung befindliche Arbeiten, indem Sie auf **File \** klicken.**| Speichern** und einen Dateinamen Ihrer Wahl eingeben.

## Aufgabe 2: Diagramm- und Zeitvisualisierungen erstellen

1. Klicken Sie auf das Kreisdiagrammsymbol im Bereich **Visualisierungen**, um das Diagramm einzufügen.
2. Ziehen Sie das Feld **Gebäude** in das Zielfeld **Legende**.
3. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
4. Ändern Sie die Größe des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.
5. Klicken Sie im Power BI-Menüband auf **Neues visuelles Element**, und wählen Sie dann, falls nicht bereits ausgewählt, im Bereich **Visualisierungen** das gestapelte Säulendiagramm aus. 
6. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
7. Ziehen Sie das Feld **Start** in das Zielfeld **Achse**.
8. Klicken Sie im Bereich „Visualisierungen“ auf das **x** neben **Tag** und **Quartal**, sodass nur die Summen für **Jahr** und **Monat** für die Achse angezeigt werden.
9. Ändern Sie die Größe des Diagramms bei Bedarf mithilfe der Ziehpunkte an den Ecken.
10. Testen Sie die Berichtsinteraktivität:
    * Wählen Sie verschiedene Gebäudesegmente im Kreisdiagramm aus, und beobachten Sie Änderungen im Zeitbericht.
    * Wählen Sie verschiedene Balken im Zeitsäulendiagramm aus, und beobachten Sie Änderungen im Kreisbericht.
    * Führen Sie mithilfe der Symbole oder mit **Daten/Drill \** einen Drilldown zur Monatsebene durch.**| Nächste Ebene erweitern** einen Drilldown auf die Monatsebene aus.
11. Speichern Sie in Bearbeitung befindliche Arbeiten, indem Sie auf **File \** klicken.**| Speichern** klicken.

Übung Nr. 2: Power BI-Dashboard erstellen
================================

## Aufgabe Nr. 1: Power BI-Bericht veröffentlichen

1. Drücken Sie auf der Registerkarte „Start“ des Menübands auf die Schaltfläche **Veröffentlichen**.

2. Wählen Sie **Mein Arbeitsbereich** als Ziel aus, und klicken Sie dann auf **Auswählen**.

3. Warten Sie, bis die Veröffentlichung abgeschlossen ist, und klicken Sie dann auf **\<Name Ihres Berichts\>.pbix in Power BI öffnen**.

## Aufgabe 2: Power BI-Dashboard erstellen

1. Klicken Sie auf der im vorherigen Schritt geöffneten Webseite oben auf **Mein Arbeitsbereich**.
2. Wählen Sie Ihren **Bericht** aus der Liste der Elemente aus.
3. Wählen im Menü **Live-Seite anheften** aus. Je nach Layout müssen Sie möglicherweise auf ... klicken, um weitere Menüelemente anzuzeigen.
4. Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.
5. Geben Sie **Campusverwaltung** unter **Dashboardname** ein, und klicken Sie auf **Live anheften**.
6. Wählen Sie oben **Mein Arbeitsbereich** aus, und wählen Sie dann das Dashboard **Campusmanagement** aus.
7. Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.

## Aufgabe 3: Visualisierungen in natürlicher Sprache hinzufügen

1. Wählen Sie innerhalb des Dashboards **Campusmanagement** oben **Stellen Sie eine Frage zu Ihren Daten** aus.
2. Geben Sie im Frage- und Antwortbereich **Gebäude nach Anzahl der Besuche** ein. Das Balkendiagramm wird angezeigt.
3. Wählen Sie **Visualisierung anheften** aus.
4. Wählen Sie **Vorhandenes Dashboard** und dann das Dashboard **Campusverwaltung** aus, und klicken Sie auf **Anheften**.
5. Testen Sie das Verhalten, indem Sie auf das Diagramm klicken, um einen Drilldown zum Q&A auszuführen.
6. Klicken Sie auf **Q & A beenden**.

## Aufgabe Nr. 4: Mobiltelefonansicht erstellen

1. Wählen Sie im Dashboard **... \| Mobile Ansicht**.
2. Ordnen Sie die Kacheln wie gewünscht neu an.
3. Klicken Sie oben rechts auf **Telefonansicht**, und ändern Sie die Ansicht in **Webansicht**.
4. Wählen Sie oben **Mein Arbeitsbereich** aus, und wählen Sie dann Ihren **Bericht** aus.
5. Wählen Sie ... \| QR-Code generieren.
6. Wenn Sie ein mobiles Gerät haben, scannen Sie den Code mit einer QR-Scanner-App, die auf iOS- und Android-Plattformen verfügbar ist. Melden Sie sich bei Ihrem Konto an, wenn Sie dazu aufgefordert werden.
7. Navigieren Sie auf einem mobilen Gerät in dem Bericht, und erkunden Sie ihn.

# Herausforderungen

* Dashboards und Berichte mit Campus- und Gebäudeplänen
* Berichten und Analysieren von Besuchsmustern und -trends
* Visualisierung von Überschreitungen der Besuchszeiten
* Streaming von Power BI zur Verarbeitung in Quasi-Echtzeit für einen großen Campus 
