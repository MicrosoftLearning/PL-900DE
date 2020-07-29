---
lab:
    title: 'Lab 04: Power BI'
    module: 'Modul XX: Power Apps Build'
---

# PL-900: Microsoft Power Platform – Grundlagen
## Modul X, Lab 4 – Power BI

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Apps und führen Automatisierungen durch, um es dem Verwaltungs- und Sicherheitspersonal des Bellows College zu ermöglichen, den Zugang zu den Gebäuden auf dem Campus zu verwalten und zu steuern. 

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

Weiterführende Schritte des Lab
======================

Wir werden die folgenden Schritte ausführen, um das Power BI-Dashboard zu entwerfen und zu erstellen:

-   Eine Verbindung zum Common Data Service herstellen 
-   Die Daten so transformieren, dass sie benutzerfreundliche Beschreibungen für die zugehörigen Datensätze enthalten (Lookups)
-    Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und veröffentlichen
-    Abfrage in natürlicher Sprache zum Erstellen zusätzlicher Visualisierungen verwenden
-    Mobile Ansicht erstellen


## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Gerät? Standort?
-   Haben Sie ausreichend Daten für die Visualisierung?
-   Welche möglichen Merkmale können Sie verwenden, um Daten über die Besuche zu analysieren?

Übung 1: Power BI-Bericht erstellen 
===============================

**Ziel:** In dieser Übung erstellen Sie, basierend auf Daten aus der Common Data Service-Datenbank, einen Power BI-Bericht.

Aufgabe 1: Daten vorbereiten
---------------------------

1.  Finden Sie die URL Ihrer Organisation heraus.

    * Navigieren Sie zum Power Platform Admin Center unter https://aka.ms/ppac.
    * Wählen Sie im linken Navigationsbereich „Umgebungen“ aus, und wählen Sie dann die Zielumgebung aus.
    * Klicken Sie im Panel **Details** mit der rechten Maustaste auf **Umgebungs-URL**, und wählen Sie dann **Link kopieren** aus.
2. Wenn Sie Power BI Desktop nicht installiert haben, navigieren Sie zu https://aka.ms/pbidesktopstore, um die Power BI-App herunterzuladen und zu installieren.

3. Öffnen Sie Power BI Desktop, und melden Sie sich an, wenn Sie dazu aufgefordert werden.

4. Wählen Sie **Daten abrufen** aus.

5. Wählen Sie **Power Platform** und dann **Common Data Service** aus, und klicken Sie dann auf **Verbinden**.

6. Fügen Sie die zuvor kopierte Umgebungs-URL ein, und klicken Sie auf **OK**.

7. Erweitern Sie den Knoten **Entitäten**, wählen Sie die Entitäten **bc_Building** und **bc_Visit** aus, und klicken Sie auf **Laden**.

8. Klicken Sie in der linken vertikalen Symbolleiste auf das Symbol für **Modell**.

9. Ziehen Sie die Spalte **bc_buildingid** aus der Tabelle **bc_Building** in die Spalte **bc_building** in der Tabelle **bc_Visit**. Dadurch wird eine Beziehung zwischen zwei Entitäten erstellt, mit denen Power BI verwandte Daten anzeigen kann.

10. Wählen Sie in der linken Symbolleiste das Symbol **Bericht** aus.

11. Erweitern Sie den Knoten **bc_Visits** im Bereich **Felder**.

12. Klicken Sie auf ..., und wählen Sie **Neue Spalte** aus.

13. Stellen Sie die App wie folgt fertig.

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    , und drücken Sie die EINGABETASTE. Dadurch wird den Besuchsdaten ein neues Feld mit dem Gebäudenamen hinzugefügt.

14. Klicken Sie neben dem Feld auf ..., und wählen Sie **Umbenennen** aus. Geben Sie **Gebäude** als Feldnamen ein.

15. Klicken Sie neben dem Feld **bc_visitid** auf ..., und wählen Sie **Umbenennen** aus. Geben Sie **Besuche** als Feldnamen ein.

16. Klicken Sie auf ... neben dem Feld **bc_scheduledstart**, und wählen Sie **Umbenennen** aus. Geben Sie **Start** als Feldnamen ein.

17. Speichern Sie laufende Arbeiten durch Klicken von **Datei | Speichern** und geben Sie einen Dateinamen Ihrer Wahl ein.

## Aufgabe 2: Diagramm- und Zeitvisualisierungen erstellen

1. Klicken Sie auf das Kreisdiagrammsymbol im Panel **Visualisierungen**, um das Diagramm einzufügen.
2. Ziehen Sie das Feld **Gebäude** in das Zielfeld **Legende**.
3. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
4. Ändern Sie die Größe des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.
5. Klicken Sie im Power BI-Menüband auf **Neues visuelles Element**, und wählen Sie dann im Bereich **Visualisierungen** das gestapelte Säulendiagramm aus. 
6. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
7. Ziehen Sie das Feld **Start** in das Zielfeld **Achse**.
8. Klicken Sie auf das **x** neben **Tag** und **Quartal**, sodass nur die Summen für  **Jahr** und **Monat** angezeigt werden.
9. Ändern Sie die Größe des Diagramms bei Bedarf mithilfe der Ziehpunkte an den Ecken.
10. Testen Sie die Berichtsinteraktivität:
    * Wählen Sie verschiedene Gebäudesegmente im Kreisdiagramm aus, und beobachten Sie Änderungen im Zeitbericht.
    * Wählen Sie verschiedene Balken im Zeitsäulendiagramm aus, und beobachten Sie Änderungen im Kreisbericht.
    * Drilldown auf Monatsebene mit Symbolen oder dem Multifunktionsleistenbefehl **Daten / Drill | Nächste Ebene erweitern**.
11. Speichern Sie laufende Arbeiten durch Klicken von **Datei | Speichern**.

Übung Nr. 2: Power BI-Dashboard erstellen
================================

## Aufgabe Nr. 1: Power BI-Bericht veröffentlichen

1. Klicken Sie im Menüband auf die Schaltfläche **Veröffentlichen**.

2. Wählen Sie **Mein Arbeitsbereich** als Ziel aus, und klicken Sie dann auf **Auswählen**.

3. Warten Sie, bis die Veröffentlichung abgeschlossen ist, und klicken Sie dann auf **\<Name Ihres Berichts\>.pbix in Power BI öffnen**.

## Aufgabe 2: Power BI-Dashboard erstellen

1. Erweitern Sie  **Mein Arbeitsbereich**.
2. Wählen Sie den Bericht unter der Überschrift **Berichte** aus.
3. Wählen im Menü **Live-Seite anheften** aus. Je nach Layout müssen Sie möglicherweise auf ... klicken, um weitere Menüelemente anzuzeigen.
4. Wählen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.
5. Geben Sie **Campusverwaltung** unter **Dashboardname** ein, und klicken Sie auf **Live anheften**.
6. Wählen Sie den Knoten **Mein Arbeitsbereich** und dann das Dashboard **Campusverwaltung** aus.
7. Testen Sie die Interaktivität der angezeigten Kreis- und Balkendiagramme.

## Aufgabe 3: Visualisierungen in natürlicher Sprache hinzufügen

1. Wählen Sie oben im Dashboard **Stellen Sie eine Frage zu Ihren Daten.** aus.
2. Geben Sie im Frage- und Antwortbereich **Gebäude nach Anzahl der Besuche** ein. Das Balkendiagramm wird angezeigt.
3. Wählen Sie **Visualisierung anheften** aus.
4. Wählen Sie **Vorhandenes Dashboard** und dann das Dashboard **Campusverwaltung** aus, und klicken Sie auf **Anheften**.
5. Testen Sie das Verhalten, indem Sie auf das Diagramm klicken, um einen Drilldown zum Q&A auszuführen.

## Aufgabe 4: Mobiltelefonansicht erstellen

1. Wählen Sie den Bericht aus dem Bereich **Berichte** aus.
2. Wählen Sie je nach UI-Version entweder ... | Mobile Ansicht oder **Webansicht | Telefonansicht**.
3. Ordnen Sie die Kacheln wie gewünscht neu an.
4. Wählen Sie ... | QR-Code generieren.
5. Wenn Sie ein mobiles Gerät haben, scannen Sie den Code mit einer QR-Scanner-App, die auf iOS- und Android-Plattformen verfügbar ist.
6. Navigieren Sie durch Berichte und erkunden Sie diese auf einem mobilen Gerät.

# Herausforderungen

* Dashboards und Berichte mit Campus- und Gebäudeplänen
* Berichten und Analysieren von Besuchsmustern und -trends
* Visualisierung von Überschreitungen der Besuchszeiten
* Streaming von Power BI zur Verarbeitung in Quasi-Echtzeit für einen großen Campus 