---
lab:
    title: 'Lab 02: Canvas App, Teil 1'
    module: 'Modul 03: Einführung in den Common Data Service'
---

# PL-900: Microsoft-Power-Platform-Grundlagen
## Modul 3, Lab 2 – Canvas-App, Teil 1

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen Automatisierungen durch, um es dem Verwaltungs- und Sicherheitspersonal des Bellows College zu ermöglichen, den Zugang zu den Gebäuden auf dem Campus zu verwalten und zu steuern.  

In Teil 1 dieses Labs entwerfen Sie eine PowerApps-Canvas-App, mit der College-Mitarbeiter Besuche für ihre Gäste verwalten können.

Weiterführende Schritte des Lab
======================

Wir werden uns beim Entwerfen der App an nachstehende Gliederung halten:

-   Erstellen Sie die App aus Daten mithilfe der Smartphone-Formfaktor-Vorlage.
-   Eine Detailseite mit Besuchsinformationen
-   Eine Bearbeitungsseite, die für Besuche erstellt werden soll
-   Ein Katalogsteuerelement, um die Besuche anzuzeigen
-   Hinzufügen von Filtern für die Katalogdatenquelle, um nur zukünftige Besuche anzuzeigen

## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Was ist der am weitesten verbreitete Formfaktor für die Zielgruppe?
-   Schätzen Sie die Anzahl der Datensätze im System 
-   Ausgewählte Datensätze einschränken, um die App-Leistung und die Benutzereinführung zu verbessern


Übung 1: Canvas-App in Staff erstellen
===============================

**Ziel:** In dieser Übung erstellen Sie eine Canvas-App aus einer Vorlage und ändern sie dann so, dass sie die erforderlichen Daten enthält.

Aufgabe 1: Canvas-App erstellen
---------------------------

In dieser Aufgabe erstellen Sie eine Canvas-App mithilfe der Telefonlayoutvorlage, die auf Common Data Service basiert. Wenn Sie „Besuche“ als ausgewählte Entität aus CDS nutzen, generiert die Vorlage die App „Galerie - Ansicht - Bearbeiten“, um Campusbesuche zu verwalten.

1.  Öffnen Sie die Campus Management-Lösung.

    -   Anmelden bei <https://make.powerapps.com>

    -   Wählen Sie Ihre **Umgebung** aus.

    -   Wählen **Apps**.

2.  Erstellen Sie eine neue Canvas-Anwendung

    -   Klicken Sie auf **Neue App | Canvas-App**.
    -   Klicken Sie unter ** Common Data Service ** auf ** Telefonlayout ** 
-   Wählen Sie die **Common Data Service**-Verbindung und klicken Sie dann auf **Erstellen**
    -   Tabelle **Besuch** auswählen
    -   Auf **Verbinden**klicken
3.  Anwendung speichern
    1.  Klicken Sie auf **Datei > Speichern**
    2.  Geben Sie **Campus-Mitarbeiter** als App-Name ein
    3.  Wählen Sie **Speichern** aus

Aufgabe 2: Konfigurieren des Detailformulars für Besuche
--------------------------------

In dieser Aufgabe konfigurieren Sie das Detailformular, um Informationen zu einzelnen Besuchsaufzeichnungen anzuzeigen.

1.  Erweitern Sie **DetailScreen1** unter **Strukturansicht**
2.  **DetailForm1** auswählen
3.  Wählen Sie **Bearbeiten** neben **Felder** im Eigenschaftenpanel aus
4.  Klicken Sie auf **Feld hinzufügen**.
5.  Wählen Sie die folgenden Felder aus:
    * Tatsächliches Ende
    * Tatsächlicher Start
    * Gebäude 
    * Code
    * Geplantes Ende
    * Geplanter Start
    * Besucher
6.  Klicken Sie auf **Hinzufügen**
7.  Ordnen Sie Felder neu an, indem Sie Feldnamen nach oben oder unten ziehen und ablegen. Empfohlene Bestellung ist:
    * Code, Name, Gebäude, Besucher, geplanter Start, geplantes Ende, tatsächlicher Start, tatsächliches Ende
8.  Klicken Sie auf **Datei**, um die laufenden Arbeiten beizubehalten.** | Speichern**, dann drücken Sie **Speichern**. 

## Aufgabe 3: Konfigurieren Sie das Bearbeitungsformular für Besuche 

In dieser Aufgabe konfigurieren Sie ein Formular zum Bearbeiten von Informationen zu einzelnen Besuchsaufzeichnungen

1.  Erweitern Sie**EditScreen1** unter **Strukturansicht**.
2.  **EditForm1** auswählen
3.  Wählen Sie das Feld **Erstellt am** und klicken Sie die Taste **Entf** zum Entfernen des Feldes.
4.  Wählen Sie **Felder bearbeiten** im Eigenschaftenfenster
5.  Klicken Sie auf **Feld hinzufügen**.
6.  Wählen Sie die folgenden Felder aus:
    * Gebäude 
    * Geplantes Ende
    * Geplanter Start
    * Besucher
7.  Klicken Sie auf **Hinzufügen**
8.  Ordnen Sie Felder neu an, indem Sie Feldnamen nach oben oder unten ziehen und ablegen. Empfohlene Bestellung ist:
    * Name, Gebäude, Besucher, geplanter Start, geplantes Ende
9.  Klicken Sie auf **Datei**, um die laufenden Arbeiten beizubehalten.** | Speichern**, dann drücken Sie **Speichern**. 

Aufgabe Nr. 4: Konfigurieren Sie die Besuchsgalerie
---------------------------------------

In dieser Aufgabe konfigurieren Sie die vorgenerierte Galerie so, dass Titel, Start- und Enddatum für den Besuch angezeigt werden. 

1.  Erweitern Sie **BrowseScreen1** unter **Strukturansicht**
2.   **BrowseGallery1** auswählen
3.  Wählen Sie die Eigenschaft **TemplateSize** aus dem Dropdown„Eigenschaft“
4.  Ersetzen Sie den Ausdruck durch ‘Min (150, BrowseGallery1.Height - 60)’. Dadurch wird ausreichend Platz für zusätzliche Informationen garantiert.
5.  Bearbeiten Sie den Katalog, indem Sie auf das Stiftsymbol in der oberen linken Ecke klicken
6.  Wählen Sie das Feld mit Datum und Uhrzeit aus 
7.  Ändern Sie die Eigenschaft **Text** von „ThisItem.'Created On'“ zu „ThisItem.'Scheduled Start'“.
8.  Feld erneut auswählen
9.  Drücken Sie STRG+C und dann STRG+V, um eine Kopie des Felds zu erstellen.
10.  Bewegen Sie das kopierte Steuerelement mit der Maus oder der Tastatur nach unten, und richten Sie es an den anderen Steuerelementen im Katalog aus
11.  Ändern Sie die Eigenschaft **Text** in „ThisItem.'Scheduled End'“
12.  Klicken Sie auf **Datei**, um die laufenden Arbeiten beizubehalten.** | Speichern**, dann drücken Sie **Speichern**. 

## Aufgabe Nr. 6: Datumsfilter hinzufügen

Da die Anzahl der Besuche kontinuierlich zunimmt, benötigen Benutzer eine Funktion zum Filtern der Besuchergalerie. Beispielsweise möchte der Benutzer möglicherweise nur die zukünftigen Besuche sehen. In dieser Aufgabe können Sie Besuche erst nach einem vom Benutzer ausgewählten Datum anzeigen.

1. Menü **Einfügen** auswählen

2. Klicken Sie auf **Eingabe | Datumsauswahl** 

3. Positionieren Sie das Steuerelement mit der Tastatur oder der Maus unter dem Suchfeld.

4.  **BrowseGallery1** auswählen 

5. Ändern Sie die Größe des Katalogsteuerelements, und verschieben Sie es so, dass es sich unter der Datumsauswahl befindet und den Bildschirm abdeckt.

6. Wählen Sie die Eigenschaft **Elemente** aus

7. Suchen Sie im Ausdruck ’[@Visits]‘ und ersetzen Sie ihn durch ‘Filter(Visits,'Scheduled End' >= DatePicker1.SelectedDate)‘. Der gesamte Ausdruck sollte wie folgt aussehen:

   ```
   SortByColumns(
   	Search(
        Filter(
        	Besuche,
            'Geplantes Ende'> = DatePicker1.SelectedDate
           ),
           TextSearchBox1.Text,
       	"bc_code","bc_name"
       ),
     "bc_code",
     If(SortDescending1, Descending, Ascending)
   )
   ```
   
8. Klicken Sie auf **Datei**, um die laufenden Arbeiten beizubehalten.** | Speichern**, dann drücken Sie **Speichern**.

# Übung Nr. 2: Fertigstellen der App

In dieser Übung testen Sie die Anwendung und fügen sie bei Erfolg Ihrer Lösung hinzu.

Aufgabe 1: App testen
--------------------------

1.  Starten Sie die Anwendung

    -   Wählen Sie **BrowseScreen1**, und klicken Sie **F5** oder **Vorschau der App**.
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

    -   Klicken Sie auf **Schließen**.

    -   Schließen Sie das Fenster oder die Registerkarte des **Designer**browsers.

    -   Klicken Sie auf **Beenden**, wenn Sie aufgefordert werden, das Browserfenster zu schließen.

    -   Navigieren Sie zurück zum vorherigen Fenster, und klicken Sie auf **Fertig**.

## Aufgabe 2: App zur Lösung hinzufügen und veröffentlichen 

1. Öffnen Sie die Campus Management-Lösung.
   * Anmelden bei <https://make.powerapps.com>
   * Wählen Sie Ihre **Umgebung** aus.
   * Wählen Sie **Lösungen** aus.
   * Klicken Sie, um die **Campus Management**-Lösung zu öffnen.
2. Wählen Sie **Vorhandene hinzufügen** aus.** | App | Canvas-App**
3. Wählen Sie die Registerkarte **Externe Lösungen** aus.
4. Wählen Sie die App **Campus-Mitarbeiter**, klicken Sie auf **Hinzufügen**.
5. Wählen Sie die App **Campus-Mitarbeiter**, klicken Sie auf **Bearbeiten**.
6. Wählen Sie **Datei** aus.** | Veröffentlichen** 

# Herausforderungen

* Kalenderansicht aller Besuche und Filtern nach Datumsbereich
* Möglichkeit zum Erstellen und Verwalten von Kontakten als Teil der App
* So zeigen Sie mehrere Besprechungen während eines einzelnen Besuchs an

