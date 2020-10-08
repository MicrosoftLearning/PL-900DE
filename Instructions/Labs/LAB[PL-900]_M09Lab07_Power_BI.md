---
lab:
    title: 'Lab: Power BI'
    module: 'Modul 5: Erste Schritte mit Power BI'
---

# Modul 5: Erste Schritte mit Power BI
## Lab: Power BI

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Geb�uden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine M�glichkeit, Daten �ber die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung m�chte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Geb�uden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden m�ssen.

W�hrend dieses Kurses erstellen Sie Anwendungen und f�hren eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Geb�uden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie ein Power BI-Dashboard, das Daten zu Campusbesuchen visualisiert.

Weiterf�hrende Schritte des Lab
======================

Wir werden die folgenden Schritte ausf�hren, um das Power BI-Dashboard zu entwerfen und zu erstellen:

-   Eine Verbindung zum Common Data Service herstellen 
-   Die Daten so transformieren, dass sie benutzerfreundliche Beschreibungen f�r die zugeh�rigen Datens�tze enthalten (Lookups)
-   Einen Bericht mit verschiedenen Visualisierungen der Informationen zu Campusbesuchen erstellen und ver�ffentlichen
-   Abfrage in nat�rlicher Sprache zum Erstellen zus�tzlicher Visualisierungen verwenden
-   Mobile Ansicht erstellen


## Voraussetzungen

* Abschluss von Lab 1 � Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Wer ist das Zielpublikum des Berichts?
-   Wie wird das Publikum den Bericht verwenden? Typisches Ger�t? Standort?
-   Haben Sie ausreichend Daten f�r die Visualisierung?
-   Welche m�glichen Merkmale k�nnen Sie verwenden, um Daten zu den Besuchen zu analysieren?

�bung Nr. 1: Power BI-Bericht erstellen 
===============================

**Ziel:** In dieser �bung erstellen Sie, basierend auf Daten aus der Common Data Service-Datenbank, einen Power BI-Bericht.

Aufgabe�1: Daten vorbereiten
---------------------------

1.  Finden Sie die URL Ihrer Organisation heraus.

    * Navigieren Sie zum Power Platform Admin Center unter https://admin.powerplatform.com.
    * W�hlen Sie auf der linken Navigationsseite �Umgebungen� aus, und �ffnen Sie dann die Zielumgebung.
    * Klicken Sie im Bereich **Details** mit der rechten Maustaste auf **Umgebungs-URL**, und w�hlen Sie dann **Linkadresse kopieren** aus.
2. Wenn Sie Power BI Desktop nicht installiert haben, navigieren Sie zu https://aka.ms/pbidesktopstore, um die Power BI-App herunterzuladen und zu installieren.

3. �ffnen Sie Power BI Desktop, und melden Sie sich an, wenn Sie dazu aufgefordert werden.

4. W�hlen Sie **Daten abrufen** aus.

5. W�hlen Sie auf der linken Seite **Power Platform** und dann **Common Data Service** aus, und klicken Sie dann auf **Verbinden**.

6. F�gen Sie die zuvor kopierte Umgebungs-URL in das Feld **Server-URL** ein, und dr�cken Sie dann auf **OK**.

7. Erweitern Sie den Knoten **Entit�ten**, w�hlen Sie die Entit�ten **bc_Building** und **bc_Visit** aus, und klicken Sie auf **Laden**.

8. Klicken Sie in der linken vertikalen Symbolleiste auf das Symbol f�r **Modell**.

9. Ziehen Sie die Spalte **bc_buildingid** aus der Tabelle **bc_Building** in die Spalte **bc_building** in der Tabelle **bc_Visit**. Dadurch wird eine Beziehung zwischen zwei Entit�ten erstellt, mit denen Power BI verwandte Daten anzeigen kann.

10. W�hlen Sie in der linken Symbolleiste das Symbol **Bericht** aus.

11. Erweitern Sie den Knoten **bc_Visits** im Bereich **Felder**.

12. Klicken Sie auf die Schaltfl�che mit den drei Punkten (...) neben **bc_Visits**, und w�hlen Sie **Neue Spalte** aus.

13. Stellen Sie die App wie folgt fertig.

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    , und dr�cken Sie die EINGABETASTE. Dadurch wird den Besuchsdaten ein neues Feld mit dem Geb�udenamen hinzugef�gt.

14. Klicken Sie neben dem Feld auf ..., und w�hlen Sie **Umbenennen** aus. Geben Sie **Geb�ude** als Feldnamen ein.

15. Klicken Sie neben dem Feld **bc_visitid** auf ..., und w�hlen Sie **Umbenennen** aus. Geben Sie **Besuche** als Feldnamen ein.

16. Klicken Sie auf ... neben dem Feld **bc_scheduledstart**, und w�hlen Sie **Umbenennen** aus. Geben Sie **Start** als Feldnamen ein.

17. Speichern Sie in Bearbeitung befindliche Arbeiten, indem Sie auf **File \** klicken.**| Speichern** und einen Dateinamen Ihrer Wahl eingeben.

## Aufgabe�2: Diagramm- und Zeitvisualisierungen erstellen

1. Klicken Sie auf das Kreisdiagrammsymbol im Bereich **Visualisierungen**, um das Diagramm einzuf�gen.
2. Ziehen Sie das Feld **Geb�ude** in das Zielfeld **Legende**.
3. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
4. �ndern Sie die Gr��e des Kreisdiagramms mithilfe der Ziehpunkte an den Ecken, sodass alle Diagrammkomponenten sichtbar sind.
5. Klicken Sie im Power BI-Men�band auf **Neues visuelles Element**, und w�hlen Sie dann, falls nicht bereits ausgew�hlt, im Bereich **Visualisierungen** das gestapelte S�ulendiagramm aus. 
6. Ziehen Sie das Feld **Besuche** in das Zielfeld **Werte**.
7. Ziehen Sie das Feld **Start** in das Zielfeld **Achse**.
8. Klicken Sie im Bereich �Visualisierungen� auf das **x** neben **Tag** und **Quartal**, sodass nur die Summen f�r **Jahr** und **Monat** f�r die Achse angezeigt werden.
9. �ndern Sie die Gr��e des Diagramms bei Bedarf mithilfe der Ziehpunkte an den Ecken.
10. Testen Sie die Berichtsinteraktivit�t:
    * W�hlen Sie verschiedene Geb�udesegmente im Kreisdiagramm aus, und beobachten Sie �nderungen im Zeitbericht.
    * W�hlen Sie verschiedene Balken im Zeits�ulendiagramm aus, und beobachten Sie �nderungen im Kreisbericht.
    * F�hren Sie mithilfe der Symbole oder mit **Daten/Drill \** einen Drilldown zur Monatsebene durch.**| N�chste Ebene erweitern** einen Drilldown auf die Monatsebene aus.
11. Speichern Sie in Bearbeitung befindliche Arbeiten, indem Sie auf **File \** klicken.**| Speichern** klicken.

�bung Nr. 2: Power BI-Dashboard erstellen
================================

## Aufgabe Nr.�1: Power BI-Bericht ver�ffentlichen

1. Dr�cken Sie auf der Registerkarte �Start� des Men�bands auf die Schaltfl�che **Ver�ffentlichen**.

2. W�hlen Sie **Mein Arbeitsbereich** als Ziel aus, und klicken Sie dann auf **Ausw�hlen**.

3. Warten Sie, bis die Ver�ffentlichung abgeschlossen ist, und klicken Sie dann auf **\<Name Ihres Berichts\>.pbix in Power BI �ffnen**.

## Aufgabe�2: Power BI-Dashboard erstellen

1. Klicken Sie auf der im vorherigen Schritt ge�ffneten Webseite oben auf **Mein Arbeitsbereich**.
2. W�hlen Sie Ihren **Bericht** aus der Liste der Elemente aus.
3. W�hlen im Men� **Live-Seite anheften** aus. Je nach Layout m�ssen Sie m�glicherweise auf ... klicken, um weitere Men�elemente anzuzeigen.
4. W�hlen Sie bei der Eingabeaufforderung **An Dashboard anheften** die Option **Neues Dashboard** aus.
5. Geben Sie **Campusverwaltung** unter **Dashboardname** ein, und klicken Sie auf **Live anheften**.
6. W�hlen Sie oben **Mein Arbeitsbereich** aus, und w�hlen Sie dann das Dashboard **Campusmanagement** aus.
7. Testen Sie die Interaktivit�t der angezeigten Kreis- und Balkendiagramme.

## Aufgabe�3: Visualisierungen in nat�rlicher Sprache hinzuf�gen

1. W�hlen Sie innerhalb des Dashboards **Campusmanagement** oben **Stellen Sie eine Frage zu Ihren Daten** aus.
2. Geben Sie im Frage- und Antwortbereich **Geb�ude nach Anzahl der Besuche** ein. Das Balkendiagramm wird angezeigt.
3. W�hlen Sie **Visualisierung anheften** aus.
4. W�hlen Sie **Vorhandenes Dashboard** und dann das Dashboard **Campusverwaltung** aus, und klicken Sie auf **Anheften**.
5. Testen Sie das Verhalten, indem Sie auf das Diagramm klicken, um einen Drilldown zum Q&A auszuf�hren.
6. Klicken Sie auf **Q & A beenden**.

## Aufgabe Nr.�4: Mobiltelefonansicht erstellen

1. W�hlen Sie im Dashboard **... \| Mobile Ansicht**.
2. Ordnen Sie die Kacheln wie gew�nscht neu an.
3. Klicken Sie oben rechts auf **Telefonansicht**, und �ndern Sie die Ansicht in **Webansicht**.
4. W�hlen Sie oben **Mein Arbeitsbereich** aus, und w�hlen Sie dann Ihren **Bericht** aus.
5. W�hlen Sie ... \| QR-Code generieren.
6. Wenn Sie ein mobiles Ger�t haben, scannen Sie den Code mit einer QR-Scanner-App, die auf iOS- und Android-Plattformen verf�gbar ist. Melden Sie sich bei Ihrem Konto an, wenn Sie dazu aufgefordert werden.
7. Navigieren Sie auf einem mobilen Ger�t in dem Bericht, und erkunden Sie ihn.

# Herausforderungen

* Dashboards und Berichte mit Campus- und Geb�udepl�nen
* Berichten und Analysieren von Besuchsmustern und -trends
* Visualisierung von �berschreitungen der Besuchszeiten
* Streaming von Power BI zur Verarbeitung in Quasi-Echtzeit f�r einen gro�en Campus 
