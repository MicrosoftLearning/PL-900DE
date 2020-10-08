---
lab:
    title: 'Lab: Canvas-App – Teil 1'
    module: 'Modul 3: Erste Schritte mit Power Apps'
---

# Modul 3: Erste Schritte mit Power Apps
## Lab: Canvas-App – Teil 1

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in papierform aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Apps und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann.  

In Teil 1 dieses Labs erstellen Sie eine Canvas-App in Power Apps, mit der Universitätsmitarbeiter Besuche für ihre Gäste verwalten können.

Weiterführende Schritte des Lab
======================

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

-   Erstellen Sie die App aus Daten mithilfe der Smartphone-Formfaktor-Vorlage.
-   Eine Detailseite mit Besuchsinformationen konfigurieren
-   Eine Bearbeitungsseite, die für Besuche erstellt werden soll, konfigurieren
-   Ein Katalogsteuerelement konfigurieren, um die Besuche anzuzeigen
-   Hinzufügen von Filtern für die Katalogdatenquelle, um nur zukünftige Besuche anzuzeigen

## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Welches ist der am weitesten verbreitete Formfaktor für die Zielgruppe?
-   Schätzen der Anzahl der Datensätze im System 
-   Ausgewählte Datensätze einschränken, um die App-Leistung und die Benutzereinführung zu verbessern


Übung 1: Canvas-App für Mitarbeiter erstellen
===============================

**Ziel:** In dieser Übung erstellen Sie eine Canvas-App anhand einer Vorlage und ändern sie dann so, dass sie die erforderlichen Daten enthält.

Aufgabe 1: Canvas-App erstellen
---------------------------

In dieser Aufgabe erstellen Sie eine Canvas-App mithilfe der Telefonlayoutvorlage, die auf Common Data Service basiert. Wenn Sie „Besuche“ als ausgewählte Entität aus Common Data Service verwenden, generiert die Vorlage die App „Katalog – Ansicht – Bearbeiten“, um Campusbesuche zu verwalten.

1.  Öffnen Sie die Campus Management-Lösung.

    -   Anmelden bei <https://make.powerapps.com>

    -   Wählen Sie oben rechts Ihre **Umgebung** aus, falls noch nicht Ihre Bellows College-Umgebung eingestellt ist.

    -   Wählen Sie **Apps** aus.

2.  Erstellen Sie eine neue Canvas-App

    -   Klicken Sie auf **Neue App**, und wählen Sie **Canvas** aus.
    
    -   Klicken Sie unter **Common Data Service** auf **Telefonlayout**
    
-   Wählen Sie die **Common Data Service**-Verbindung aus, und klicken Sie dann auf **Erstellen**.

    -   Wählen Sie die Tabelle **Besuche** aus
    
    -   Auf **Verbinden**klicken
    
    -   Das Fenster **Willkommen bei Power Apps Studio** wird möglicherweise geöffnet. Klicken Sie auf **Überspringen**.
    
3.  Anwendung speichern

    1.  Klicken Sie auf **Datei > Speichern**.
    
    2.  Geben Sie **Campus-Mitarbeiter** als App-Name ein
    
    3.  Wählen Sie **Speichern** aus.

Aufgabe 2: Konfigurieren des Detailformulars für Besuche
--------------------------------

In dieser Aufgabe konfigurieren Sie das Detailformular, um Informationen zu einzelnen Besuchsaufzeichnungen anzuzeigen.

1.  Wählen Sie oben links den Rückwärtspfeil aus, um zur App-Definition zurückzukehren.
2. Erweitern Sie **DetailScreen1** unter **Strukturansicht**
3.  **DetailForm1** auswählen
4.  Wählen Sie neben **Felder** im Bereich auf der rechten Seite **Felder bearbeiten** aus.
5.  Klicken Sie auf **Feld hinzufügen**.
6.  Wählen Sie die folgenden Felder aus:
    * Tatsächliches Ende
    * Tatsächlicher Start
    * Gebäude 
    * Code
    * Geplantes Ende
    * Geplanter Start
    * Besucher
7.  Klicken Sie auf **Hinzufügen**.
8.  Ordnen Sie Felder im Bereich **Felder** neu an, indem Sie Feldnamen nach oben oder unten ziehen und ablegen. Dies ist die empfohlene Reihenfolge:
    * Code, Name, Gebäude, Besucher, geplanter Start, geplantes Ende, tatsächlicher Start, tatsächliches Ende
9.  Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei** und anschließend auf **Speichern**. Kehren Sie mithilfe des Rückwärtspfeils zur App zurück.

## Aufgabe 3: Bearbeitungsformular für Besuche konfigurieren 

In dieser Aufgabe konfigurieren Sie ein Formular zum Bearbeiten von Informationen zu einzelnen Besuchsaufzeichnungen.

1.  Erweitern Sie **EditScreen1** unter **Strukturansicht**.
2.  **EditForm1** auswählen
3.  Wählen Sie das Feld **Erstellt am** und klicken Sie die Taste **Entf** zum Entfernen des Feldes.
4.  Wählen Sie **Felder bearbeiten** im Eigenschaftenfenster
5.  Klicken Sie auf **Feld hinzufügen**.
6.  Wählen Sie die folgenden Felder aus:
    * Gebäude 
    * Geplantes Ende
    * Geplanter Start
    * Besucher
7.  Klicken Sie auf **Hinzufügen**.
8.  Ordnen Sie Felder im Bereich **Felder** neu an, indem Sie Feldnamen nach oben oder unten ziehen und ablegen. Dies ist die empfohlene Reihenfolge:
    * Name, Gebäude, Besucher, geplanter Start, geplantes Ende
9.  Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei** und anschließend auf **Speichern**. Kehren Sie mithilfe des Rückwärtspfeils zur App zurück.

Aufgabe 4: Konfigurieren Sie die Besuchsgalerie
---------------------------------------

In dieser Aufgabe konfigurieren Sie den vorab generierten Katalog so, dass Titel, Start- und Enddatum für den Besuch angezeigt werden. 

1.  Erweitern Sie **BrowseScreen1** unter **Strukturansicht**
2.  **BrowseGallery1** auswählen
3.  Wählen Sie die Eigenschaft **TemplateSize** aus dem Dropdown„Eigenschaft“
4.  Ersetzen Sie den Ausdruck durch `Min(150, BrowseGallery1.Height - 60)`. Dadurch wird ausreichend Platz für zusätzliche Informationen garantiert.
5.  Bearbeiten Sie den Katalog, indem Sie auf das Stiftsymbol in der oberen linken Ecke des Katalogs klicken (zeigen Sie auf die App-Vorschau, und klicken Sie auf das Stiftsymbol).
6.  Wählen Sie das Feld „Datum/Uhrzeit“ aus.
7.  Ändern Sie in der Formelleiste oben `ThisItem.'Created On'` in `ThisItem.'Scheduled Start'`
8.  Wählen Sie das Feld erneut aus
9.  Drücken Sie `CTRL-C` und dann `CTRL-V`, um eine Kopie des Felds zu erstellen.
10.  Bewegen Sie das kopierte Steuerelement mit der Maus oder der Tastatur nach unten, und richten Sie es an den anderen Steuerelementen im Katalog unter dem Feld „Datum/Uhrzeit“ aus.
11.  Ändern Sie in der Formelleiste oben `ThisItem.'Scheduled Start'` in `ThisItem.'Scheduled End'`
12.  Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei** und anschließend auf **Speichern**. Kehren Sie mithilfe des Rückwärtspfeils zur App zurück.

## Aufgabe 5: Datumsfilter hinzufügen

Da die Anzahl der Besuche kontinuierlich zunimmt, benötigen Benutzer eine Funktion zum Filtern der Besuchergalerie. Beispielsweise möchte der Benutzer möglicherweise nur die zukünftigen Besuche sehen. In dieser Aufgabe fügen Sie eine Funktion hinzu, um Besuche erst nach einem vom Benutzer ausgewählten Datum anzuzeigen.

1. Wählen Sie das Menü **Einfügen** oben aus.

2. Klicken Sie auf **Eingang**, und wählen Sie die **Datumsauswahl** aus.

3. Positionieren Sie das Steuerelement mit der Tastatur oder der Maus unter dem Suchfeld.

4. Wählen Sie **BrowseGallery1** aus 

5. Ändern Sie die Größe des Katalogsteuerelements, und verschieben Sie es so, dass es sich unter der Datumsauswahl befindet und den Bildschirm abdeckt. Klicken Sie dazu oben in der Mitte des Katalogsteuerelements auf das Größenänderungssymbol, und ändern Sie die Größe des Steuerelements, um nach der Datumsauswahl zu beginnen.

6. Während Sie noch **BrowseGallery1** auswählen, klicken Sie auf die Registerkarte **Erweitert** im Bereich „Eigenschaften“, und suchen Sie die Eigenschaft **Artikel**.

7. Suchen Sie im Ausdruck die Zeichenfolge `[@Visits]`, und ersetzen Sie sie durch `Filter(Visits,'Scheduled End' >= DatePicker1.SelectedDate)`. Der gesamte Ausdruck sollte wie folgt aussehen:

   ```
   SortByColumns(
   	Search(
        Filter(
        	Visits,
            'Scheduled End' >= DatePicker1.SelectedDate
           ),
           TextSearchBox1.Text,
       	"bc_code","bc_name"
       ),
     "bc_code",
     If(SortDescending1, Descending, Ascending)
   )
   ```
   
8. Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei** und anschließend auf **Speichern**. Kehren Sie mithilfe des Rückwärtspfeils zur App zurück.

# Übung 2: Fertigstellen der App

In dieser Übung testen Sie die Anwendung und fügen sie bei Erfolg Ihrer Lösung hinzu.

Aufgabe 1: App testen
--------------------------

1.  Starten Sie die Anwendung

    -   Wählen Sie **BrowseScreen1** aus, und drücken Sie **F5**, oder klicken Sie auf das Wiedergabesymbol in der oberen rechten Ecke, um eine Vorschau der App anzuzeigen.
    -   Die Anwendung sollte eine Liste der Besuche laden und anzeigen. 
    -   Testen Sie den Filter, indem Sie verschiedene Daten in der Datumsauswahl auswählen
    -   Wählen Sie einen Besuch aus, und überprüfen Sie, ob das Anzeigeformular ordnungsgemäß funktioniert.
    -   Kehren Sie zur Galerie zurück und drücken Sie +, um einen neuen Besuch zu erstellen. Überprüfen Sie, dass das Bearbeitungsformular die erforderlichen Felder enthält, einschließlich Besucher, Gebäude sowie geplante Start- und Enddaten.
    -   Geben Sie die Informationen an und senden Sie sie. Überprüfen Sie, dass der neue Datensatz in der Galerie angezeigt wird.
    -   Drücken Sie die**ESC**-Taste, um die App zu schließen.

2.  Speichern und veröffentlichen Sie die Anwendung

    -   Klicken Sie auf **Datei** und anschließend auf **Speichern**.

    -   Klicken Sie auf „Veröffentlichen“.

    -   Klicken Sie auf **Diese Version veröffentlichen**.

    -   Klicken Sie auf den Rückwärtspfeil, um zur App zurückzukehren.

    -   Schließen Sie das Fenster oder die Registerkarte des **Designer**-Browsers.

    -   Klicken Sie auf **Beenden**, wenn Sie aufgefordert werden, das Browserfenster zu schließen.


## Aufgabe 2: App zur Lösung hinzufügen und veröffentlichen 

1. Öffnen Sie die Campus Management-Lösung.
   * Anmelden bei <https://make.powerapps.com>
   * Wenn die oben rechts angezeigte Umgebung nicht Ihre Bellows College-Umgebung ist, wählen Sie Ihre **Umgebung** aus. 
   * Wählen Sie **Lösungen** aus.
   * Klicken Sie, um die **Campus Management**-Lösung zu öffnen.
2. Wählen Sie **Vorhandene hinzufügen**, klicken Sie dann auf **App** und auf **Canvas-App**.
3. Wählen Sie die Registerkarte **Externe Lösungen** aus.
4. Wählen Sie die App **Campus-Mitarbeiter**, klicken Sie auf **Hinzufügen**.
5. Wählen Sie **Alle Anpassungen veröffentlichen** aus.

# Herausforderungen

* Kalenderansicht aller Besuche und Filtern nach Datumsbereich
* Möglichkeit zum Erstellen und Verwalten von Kontakten als Teil der App
* So zeigen Sie mehrere Besprechungen während eines einzelnen Besuchs an

