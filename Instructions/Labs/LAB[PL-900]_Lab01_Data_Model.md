---
lab:
    title: 'Lab 01: Datenmodellierung'
    module: 'Modul 03: Einführung in den Common Data Service'
---

# PL-900: Microsoft-Power-Platform-Grundlagen
## Modul 3, Lab 1 – Datenmodellierung

## Wichtiger Hinweis zu: Mandanten – vorübergehende Problemumgehung

Ab dem 23. Januar 2020 kann WWL den Kursteilnehmern keinen vorab bereitgestellten Dynamics 365-Zugriff gewähren und arbeitet an einer Lösung, die in den nächsten 4 bis 6 Wochen verfügbar sein sollte. Um dieses Problem zu umgehen, empfehlen wir die Verwendung von Dynamics 365-Testkonten. Jeder Kursteilnehmer ist dafür verantwortlich, diese anzufordern. Um den Kursteilnehmern dabei zu helfen, die Dynamics 365-Mandanten (einschließlich Marketing) zu erhalten, werden M365-Mandanten über die Authorized Lab Hoster bereitgestellt. Dies ist eine kurzfristige Lösung, und wir werden alle Beteiligten, einschließlich Learning-Partner und MCTs, auf dem Laufenden halten, sobald Fortschritte erzielt wurden, und sie informieren, wenn ein dauerhafterer Lösungszeitplan für die Vorabbereitstellung des Dynamics 365-Zugriffs für die Labnutzung festgelegt ist. Bitte arbeiten Sie mit Ihrem Authorized Lab Hoster zusammen, um die M365-Mandanten für die Kursteilnehmer bereitzustellen, und folgen Sie den nachstehenden Anweisungen, um den M365-Mandanten zum Absichern eines Dynamics 365-Tests für Ihre entsprechende Anwendung zu nutzen.
 
1. Melden Sie sich mit Ihren bereitgestellten M365-Anmeldeinformationen bei https://admin.microsoft.com/ an, und akzeptieren Sie die Bedingungen.
2. Wenn Sie sich erfolgreich angemeldet haben, greifen Sie auf https://trials.dynamics.com/ zu. Wählen Sie die zutreffende Anwendung für Ihren Kurs aus.
3. Geben Sie unter „E-Mail (geschäftlich)“ die E-Mail-Adresse aus den M365-Anmeldeinformationen ein. Geben Sie unter „Telefonnummer“ Ihre eigene Telefonnummer ein.
4. Wählen Sie „Erste Schritte“ aus.
5. Sie werden aufgefordert, Ihr Kennwort für das Konto „on.microsoft.com“ einzugeben. Geben Sie das Kennwort ein, das für den M365-Mandanten bereitgestellt wurde.
6. Akzeptieren Sie die allgemeinen Geschäftsbedingungen, wenn Sie dazu aufgefordert werden. Ihre Umgebung kann einige Minuten zur Bereitstellung benötigen.

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen Automatisierungen durch, um es dem Verwaltungs- und Sicherheitspersonal des Bellows College zu ermöglichen, den Zugang zu den Gebäuden auf dem Campus zu verwalten und zu steuern. 

In diesem Lab richten Sie eine Umgebung ein, erstellen eine Common Data Service (CDS)-Datenbank und eine Lösung, um Ihre Änderungen nachzuverfolgen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1 –  Verfolgen Sie Standorte (Gebäude) der Campusbesuche
-   R2 –  Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen 
-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen 

Zum Abschluss importieren Sie Beispieldaten in CDS.

Weiterführende Schritte des Lab
======================

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* eine Lösung und einen Herausgeber erstellen
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Die Metadatenbeschreibung (Entitäten, Feldtypen und Beziehungen) finden Sie im [Datenmodelldokument](../../Allfiles/Labs/Campus%20Management.vsdx). 

Nach Abschluss aller Anpassungen wird Ihre Lösung mehrere Entitäten enthalten:

-   Kontakt
-   Gebäude
-   Besuch

## Voraussetzungen

* Keine

Vor dem Beginn zu beachtende Dinge
-----------------------------------

* Namenskonvention
* Datentypen, Einschränkungen (z. B. maximale Länge eines Namens)
* Datetime-Formatierung zur Unterstützung einer einfachen Lokalisierung

Übung 1: Umgebung und Lösung erstellen
==================================================

**Ziel:** In dieser Übung bereiten Sie die Umgebung vor und erstellen eine Lösung zur Unterstützung des Datenmodellierungsprozesses. 

Aufgabe 1: Umgebung erstellen
-----------------------------

Wenn Sie keine Umgebung besitzen und vor der Übung auch keine erhalten haben, erstellen Sie in dieser Aufgabe eine neue Arbeitsumgebung. Andernfalls können Sie mit der nächsten Aufgabe fortfahren.

1.  Melden Sie sich bei <https://aka.ms/ppac> an.

2.  Wählen Sie **Umgebungen** aus, und klicken Sie im oberen Menü auf **Neu**. Dies öffnet
    ein Menü auf der rechten Seite des Fensters.

3.  Geben Sie **Bellows College [Ihr Nachname]** als **Name** ein.

4.  Wählen Sie **Produktion** aus der Dropdown-Liste für **Typ**.

5.  Wählen Sie Ihre **Region** aus

6.  Geben Sie den **Zweck** des Erstellens dieser Umgebung ein (optional). 
    
7.  Stellen Sie den **Umschalter** auf **Datenbank für diese Umgebung erstellen**, wenn Sie
    die Datenbank damit zusammen erstellen möchten, andernfalls kann dies durchgeführt werden,
    wenn die Umgebung konfiguriert ist.

8.  Klicken Sie auf **Weiter**.

9.  Wählen Sie **Sprache** und **Währung** aus. Für die Zwecke dieser Labs
    wurden für die Umgebungen **Englisch** und **US-Dollar** (USD) ausgewählt.

10. Belassen Sie **Dynamics 365-Apps** deaktiviert während Labs
    deaktiviert.

11. Belassen Sie **Beispiel-Apps und -Daten bereitstellen** während dieser Labs
    deaktiviert.

12. Klicken Sie auf **Speichern**.

13. Ihre Umgebung kann einige Minuten zur Bereitstellung benötigen. Sie können auf die Schaltfläche **Aktualisieren** klicken, um die Liste zu aktualisieren. Wenn die Umgebung bereitgestellt ist, wechselt der **Zustand** zu „Bereit“.

14. Wenn Sie Ihre Datenbank noch nicht erstellt haben, wählen Sie Ihre Umgebung aus und klicken auf **Meine Datenbank erstellen**. Andernfalls überspringen Sie diesen Schritt.

    - Wählen Sie **Währung** und **Sprache** aus. Für die Zwecke dieser Labs
    Umgebungen haben **US-Dollar** (USD) und **Englisch** ausgewählt.

    - Klicken Sie auf **Meine Datenbank erstellen**.

Aufgabe 2: Lösung und Publisher erstellen
---------------------------------------

1.  Lösung erstellen

    -   Anmelden bei <https://make.powerapps.com>

    -   Wählen Sie aus dem oberen Dropdownmenü Ihre Umgebung aus.

    -   Wählen Sie **Lösungen** aus dem linken Menü aus, und klicken Sie auf **Neue Lösung**.

    -   Geben Sie **Campusmanagement** als **Anzeigename** ein.

2.  Publisher erstellen

    -   Klicken Sie auf das Dropdown-Menü **Publisher**, und wählen Sie **+ Publisher** aus.

    -   Geben Sie **Bellows College** als **Anzeigename** und **bc** als **Präfix** ein.

    -   Klicken Sie auf **Speichern und schließen**.

3.  Schließen Sie die Lösungserstellung ab.

    -   Klicken Sie nun auf die Dropdownliste **Publisher**, und wählen Sie den Herausgeber **Bellows College** aus,
        den Sie gerade erstellt haben.

    -   Geben Sie **1.0.0.0** als **Version** ein, und klicken Sie auf **Erstellen**.

Aufgabe Nr. 3: Eine vorhandene Entität hinzufügen
-----------------------------

1.  Klicken Sie zum Öffnen auf die Lösung **Campusmanagement**, die Sie gerade erstellt haben.
2.  Klicken Sie auf **Vorhandene hinzufügen**, und wählen Sie **Entität** aus.
3.  Suchen Sie nach **Kontakt**, und wählen Sie dies aus.
4.  Klicken Sie auf **Weiter**.
5.  Klicken Sie auf **Komponenten auswählen**.
6.  Wählen Sie die Registerkarte **Ansichten** aus, und wählen Sie die Ansicht **Aktive Kontakte** aus. Klicken Sie auf
    **Hinzufügen**.
7.  Klicken Sie erneut auf **Komponenten auswählen**.
8.  Wählen Sie die Registerkarte **Formulare** aus, und wählen Sie das Formular **Kontakt**aus.
9.  Klicken Sie auf **Hinzufügen**.
10. Sie sollten **1 Ansicht** und **1 Formular** ausgewählt haben. Klicken Sie erneut auf **Hinzufügen**.
    Dadurch wird die Kontaktentität zur neu erstellten Lösung hinzugefügt. 
21.  Ihre Lösung sollte jetzt eine Entität haben: Kontakt.

Übung Nr. 2: Entitäten und Beziehungen erstellen
========================================

**Ziel:** In dieser Übung erstellen Sie Entitäten und fügen Beziehungen
zwischen den Entitäten hinzu.

Aufgabe Nr. 1: Entität „Gebäude“ und Felder erstellen
-----------------------------------------

1.  Öffnen Sie in Ihrer Entwicklungsumgebung die Lösung „Campus Management“
    Lösung
    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie noch nicht angemeldet sind)
    * Wählen Sie **Lösungen** aus, und klicken Sie zum Öffnen auf die Lösung **Campus Management**,
          die Sie gerade erstellt haben (falls Sie sich noch nicht in dieser Lösung befinden)
2.  Die Entität „Gebäude“ erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
    -   Geben Sie **Gebäude** als **Anzeigename** ein, und klicken Sie auf **Erstellen**. Dies startet
            die Bereitstellung der Entität im Hintergrund, während Sie mit dem Hinzufügen
            weiterer Entitäten und Felder beginnen können.

## Aufgabe 2: Erstellen der Entität „Besuch“ und von Feldern

Die Entität **Besuch** enthält Informationen zu den Campusbesuchen, einschließlich des Gebäudes, des Besuchers und des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs. 

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> [HINWEIS]
> Wir nutzen **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs *immer* die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird. 

1.  Wählen Sie die Lösung **Campus Management**
2. Entität „Besuch“ erstellen

   * Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
   * Geben Sie **Besuch** als **Anzeigename** ein, und klicken Sie auf **Erstellen**. Dadurch wird die Entität im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Felder hinzuzufügen.

3. Erstellen Sie das Feldes „Geplanter Start“

   * Stellen Sie sicher, dass Sie die Registerkarte **Felder** ausgewählt haben, und klicken Sie auf **Feld hinzufügen**.
   * Geben Sie **Geplanter Start** als **Anzeigename** ein.
   * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
   * Aktivieren Sie das Kontrollkästchen **Erforderlich**.
   * Erweitern Sie den Abschnitt **Erweitert**.
   * Wählen Sie **Zeitzonenunabhängig** als **Verhalten**.
   * Klicken Sie auf **Fertig**.

4.  Erstellen des Feldes „Geplantes Ende“

    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Geplantes Ende** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Aktivieren Sie das Kontrollkästchen **Erforderlich**.
    * Erweitern Sie den Abschnitt **Erweitert**.
    * Wählen Sie **Zeitzonenunabhängig** als **Verhalten**.
    * Klicken Sie auf **Fertig**.
6.  Erstellen des Feldes „Tatsächlicher Start“
    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Erweitern Sie den Abschnitt **Erweitert**.
    * Wählen Sie **Zeitzonenunabhängig** als **Verhalten**.
    * Klicken Sie auf **Fertig**.
7.  Erstellen Sie das Feld „Tatsächliches Ende“
    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Erweitern Sie den Abschnitt **Erweitert**.
    * Wählen Sie **Zeitzonenunabhängig** als **Verhalten**.
    * Klicken Sie auf **Fertig**.
7.  Erstellen Sie das Feld „Code“
    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Code** als **Anzeigename** ein.
    * Wählen Sie **AutoWert** als **Datentyp** aus.
    * Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.
    * Klicken Sie auf **Fertig**.
8.  Klicken Sie auf **Entität speichern**

Aufgabe 3: Beziehungen erstellen
------------------------------

1.  Wählen Sie die Lösung **Campusmanagement** aus.
4.  Erstellen der Beziehung „Besuch zu Kontakt“
    * Klicken Sie, um die Entität **Besuch** zu öffnen.
    * Wählen Sie die Registerkarte **Beziehungen** aus.
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie „Kontakt“ für **Verknüpft (Eins)** aus 
    * Geben Sie **Besucher** als **Anzeigename des Nachschlagefelds** ein 
    * Klicken Sie auf **Fertig**.
3.  Erstellen Sie die Beziehung „Besuch in Gebäude“
    * Klicken Sie, um die Entität **Besuch** zu öffnen.
    * Wählen Sie die Registerkarte **Beziehungen** aus.
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie „Gebäude“ für **Verknüpft (Eins)** aus 
    * Klicken Sie auf **Fertig**.
4.  Klicken Sie auf **Entität speichern**.
5.  Wählen Sie aus dem oberen Menü **Lösungen** aus, und klicken Sie auf **Alle
    Anpassungen veröffentlichen.**

# Übung 3: Daten importieren

**Ziel:** In dieser Übung importieren Sie Beispieldaten in die Common Data Service-Datenbank.

## Aufgabe Nr. 1: Datenzuordnung importieren

1. Laden Sie [CampusDataMap.xml](../../Allfiles/Labs/CampusDataMap.xml) herunter.
2. Navigieren Sie zum Power Platform Admin Center unter https://aka.ms/ppac, und melden Sie sich an.
3. Wählen Sie auf der linken Navigationsseite „Umgebungen“ aus, wählen Sie dann die Zielumgebung aus, und klicken Sie auf **Einstellungen**.
4. Erweitern Sie den Abschnitt **Datenverwaltung**, und wählen Sie dann **Datenzuordnungen** aus. Dadurch wird der Bildschirm „Zuordnung importieren“ auf einer neuen Browserregisterkarte geöffnet.
5. Klicken Sie auf **Importieren**, und klicken Sie dann auf **Datei wählen**. Suchen Sie die zuvor heruntergeladene Datei **CampusDataMap.xml**, wählen Sie sie aus, und klicken Sie dann auf **OK**.

## Aufgabe 2: Daten importieren  

1. Laden Sie [CampusData.zip](../../Allfiles/Labs/CampusData.zip) herunter.
2. Wechseln Sie wieder zur ursprünglichen Registerkarte mit der Umgebung.  
3. Klicken Sie auf **Datenimport-Assistenten**.
4. Klicken Sie auf **DATEN IMPORTIEREN**.
5. Klicken Sie auf **Datei wählen**. Suchen Sie dann die zuvor heruntergeladene Datei **CampusData.zip**, und wählen sie aus.
6. Klicken Sie auf **Weiter** und dann erneut auf **Weiter**.
7. Wählen Sie **CampusImportDataMap** aus, und klicken Sie auf **Weiter**.
8. Überprüfen Sie die Zuordnungszusammenfassung. Klicken Sie auf **Weiter** und anschließend auf **Übermitteln**.
9. Klicken Sie auf **Fertig**.

## Aufgabe 3: Datenimport überprüfen

1. Wählen Sie die Lösung **Campusmanagement** aus.
2. Wählen Sie die Entität **Besuch** aus, und wählen Sie dann die Registerkarte **Daten** aus.
3. Klicken Sie auf die Ansichtsauswahl in der oberen rechten Ecke, und wählen Sie dann **Alle Felder** aus
4. Wenn der Import erfolgreich war, sollte eine Liste der Besuchseinträge angezeigt werden.
5. Klicken Sie auf einen beliebigen Wert in der Spalte **Gebäude**, und bestätigen Sie, dass das Gebäudeformular in einem separaten Fenster geöffnet wird.
6. Klicken Sie auf einen beliebigen Wert in der Spalte **Besucher** (möglicherweise müssen Sie nach rechts scrollen), und bestätigen Sie, dass das Kontaktformular in einem separaten Fenster geöffnet wird.

# Herausforderungen

* Würden Sie in Betracht ziehen, die *Termin*-Aktivität als Teil der Lösung zu verwenden? Was würde sich ändern?
* Wie wird erzwungen, dass das geplante Ende nach dem geplanten Start liegt? 
* Fügen Sie Unterstützung für mehrere Besprechungen während eines einzelnen Besuchs hinzu.
* Schützen Sie den Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter.
* Bestimmte Gebäude dürfen nur nach Genehmigung des Managements betreten werden. Was würde der Genehmigungsprozess im Datenmodell ändern?

