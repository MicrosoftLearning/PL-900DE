---
lab:
    title: 'Lab: Canvas-App – Teil 2'
    module: 'Modul 3: Erste Schritte mit Power Apps'
---

# Modul 3: Erste Schritte mit Power Apps
## Lab: Canvas-App – Teil 2

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in papierform aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Apps und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In Teil 2 dieses Labs erstellen Sie eine Power Apps-Canvas-App, mit deren Hilfe das Sicherheitspersonal an den Gebäudeeingängen die Besucher schnell bestätigen und registrieren kann.

Weiterführende Schritte des Lab
======================

Sie werden sich beim Entwerfen der App an nachstehende Gliederung halten:

-   Erstellen der App mit dem Formfaktor „Smartphone“
-   Eine Verbindung zum Common Data Service als Datenquelle herstellen
-   Die Eingabe (Besuchercode) erfassen und den Besucherdatensatz suchen
-   Ein Formularansicht-Steuerelement konfigurieren, um die Besucherinformationen anzuzeigen
-   Nutzen Sie eine Common Data Service-Ansicht, um den Katalog aufzufüllen
-   Ausführen des Ein- und Auscheckvorgangs für einen Besucher


## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Auf welche Informationen würde ein Sicherheitsbeauftragter schnell zugreifen müssen?
-   Was sollte geschehen, wenn ein Besuchercode ungültig ist?
-   Was soll geschehen, wenn der Besucher außerhalb der geplanten Zeiten ankommt? 

Übung 1: Erstellen einer Sicherheits-Canvas-App
===============================

**Ziel:** In dieser Übung erstellen Sie eine Canvas-App.

Aufgabe 1: Canvas-App erstellen
---------------------------

1.  Öffnen Sie die Campus Management-Lösung.

    -   Anmelden bei <https://make.powerapps.com>

    -   Wenn die oben rechts angezeigte Umgebung nicht Ihre Bellows College-Umgebung ist, wählen Sie Ihre **Umgebung** aus. 

    -   Wählen Sie **Lösungen** aus.

    -   Klicken Sie, um die **Campus Management**-Lösung zu öffnen.
2.  Erstellen Sie eine neue Canvas-App

    -   Klicken Sie auf **Neu**, und wählen Sie **App \| Canvas-App \| Formfaktor „Telefon“**.
        Dadurch wird der App-Editor in einem neuen Fenster geöffnet.
    -   Wenn Sie Ihre erste App erstellen, werden Sie aufgefordert,
        das Land oder die Region für die App festzulegen. Klicken Sie auf **Los geht's.**
    -   Klicken Sie auf „Datei“, und wählen Sie „Speichern unter“ aus.
    -   Überprüfen Sie, ob **Die Cloud** ausgewählt ist. Geben Sie **Campus-Sicherheit** als Name ein, und
        klicken Sie auf **Speichern**. Dadurch wird sichergestellt, dass die Änderungen nicht verloren gehen, wenn die App unerwartet geschlossen wird.
    -   Klicken Sie oben rechts (unter „Power Apps“) auf den Rückwärtspfeil, um zur App zurückzukehren.

3.  Verbindung zur Datenquelle herstellen (Besuche)
    1.  Klicken Sie auf **Ansicht \| Datenquellen**
    2.  Klicken Sie auf **Daten hinzufügen**.
    3.  Klicken Sie auf **Alle Entitäten anzeigen**.
    4.  Wählen Sie **Besuche** aus, und warten Sie, bis die Besuchs-Entität unter den Datenquellen angezeigt wird.
4.  Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei \| Speichern** und anschließend auf **Speichern**.

Aufgabe 2: Besucherinformationen anzeigen
--------------------------------

1.  Suchfeld hinzufügen

    -   Wählen Sie auf der linken Seite die Registerkarte **Strukturansicht** aus.
    -   Wählen Sie **Bildschirm1** aus.
    -   Wechseln Sie zur Registerkarte **Einfügen**.
    -   Klicken Sie auf **Text**, und wählen Sie **Texteingabe** aus.
    -   Wählen Sie die Eigenschaft **Standard** aus, und löschen Sie den Wert.
    -   Wählen Sie die Eigenschaft **HintText** aus, und geben Sie **„Besuchercode eingeben“** als Wert ein (einschließlich doppelter Anführungszeichen).
    -   Klicken Sie auf ... neben dem Steuerelementnamen in einer Strukturansicht, wählen Sie **Umbenennen** aus, und ändern Sie den Namen in **textCode**.
2. Formulansicht hinzufügen

   -   Klicken Sie auf der Registerkarte **Einfügen** auf **Formulare**, und wählen Sie dann **Anzeige** aus
   -   Positionieren Sie das Formular mithilfe der Größenziehpunkte unter dem Suchtextfeld
   -   Wählen Sie die Eigenschaft **Datenquelle** aus, und geben Sie **Besuche** ein.
   -   Wählen Sie im Eigenschaftenbereich die Option **Horizontal** als **Layout** aus
   -   Klicken Sie auf **Felder bearbeiten**.
   -   Klicken Sie auf **Feld hinzufügen**, und wählen Sie die folgenden Felder aus: Tatsächliches Ende, Tatsächlicher Start, Gebäude, Geplantes Ende, Geplanter Start, Besucher
   -   Drücken Sie auf **Hinzufügen**.
   -   Ändern Sie die Reihenfolge der ausgewählten Felder, indem Sie die Feldkarten in die Liste ziehen. Die empfohlene Reihenfolge ist: Besucher, Gebäude, Geplanter Start, Geplantes Ende, Tatsächlicher Start, Tatsächliches Ende
   -   Wählen Sie die Eigenschaft **Element** aus, und geben Sie `LookUp(Visits, Code = textCode.Text)` ein. 

3.  Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei \| Speichern** und anschließend auf **Speichern**. Klicken Sie oben rechts (unter „Power Apps“) auf den Rückwärtspfeil, um zur App zurückzukehren.

4. Testen der App

   -   Wechseln Sie zur Registerkarte „Browser“, die die Lösung enthält
   -   Wählen Sie die Entität **Besuch** aus
   -   Wählen Sie die Registerkarte **Daten** aus
   -   Öffnen Sie die Ansichtsauswahl oben rechts, indem Sie auf den aktuellen Ansichtsnamen (Aktive Besuche) klicken.
   -   Ändern Sie die Ansicht auf **Alle Felder**.
   -   Suchen Sie einen Besuchsdatensatz, der keinen tatsächlichen Start- oder Endwert hat. Wählen und kopieren Sie den **Code** für diesen Besuch.
   -   Wechseln Sie mit der App zur Browserregisterkarte, und drücken Sie F5, um die App auszuführen.
   -   Fügen Sie den kopierten Wert in das Suchtextfeld ein, und überprüfen Sie, ob der Datensatz im Formular angezeigt wird
   -   Löschen Sie den Inhalt des Suchtextfelds.
5.  Drücken Sie **ESC**, um die ausgeführte App zu beenden.


Aufgabe 3: Fügen Sie Eincheck- und Auscheck-Schaltflächen hinzu
---------------------------------------

1. Speichern Sie die Suchergebnisse in einer Variablen, um sie im gesamten Steuerelement wiederverwenden zu können

   * Wählen Sie das Steuerelement **textCode** aus
   * Wählen Sie auf der Registerkarte „Erweitert“ die Eigenschaft **OnChange** aus.
   * Geben Sie den folgenden Ausdruck ein: `Set(Visit, LookUp(Visits, Code = textCode.Text))`.
     Es ist derselbe Ausdruck wie oben, außer, dass wir diesmal die Ergebnisse in einer globalen Variablen speichern. Dadurch können wir die Variable *Besuch* in der gesamten App verwenden, ohne dass der gesamte Suchausdruck erneut eingegeben werden muss.

2. Hinzufügen der Schaltflächen zum Ein- und Auschecken
   
   1. Wählen Sie die Registerkarte **Einfügen** aus
   2. Klicken Sie auf **Schaltfläche**
   3. Ändern Sie die Eigenschaft **Text** der Schaltfläche in **„Einchecken“** (Sie können innerhalb der vorhandenen Anführungszeichen eingeben).
   4. Benennen Sie die Schaltfläche in **CheckInButton** um, indem Sie auf den Schaltflächennamen (Schaltfläche1) im rechten Bereich klicken.
   5. Klicken Sie auf **Schaltfläche**, um eine weitere Schaltfläche einzufügen.
   6. Ändern Sie die Eigenschaft der Schaltfläche **Text** in **„Auschecken“**
   7. Benennen Sie die Schaltfläche in **AuscheckSchaltfläche** um
   8. Positionieren Sie die Schaltflächen nebeneinander unter der Ansicht des Datensatzformulars 
   
3. Aktivieren und Deaktivieren von Schaltflächen abhängig von den Besuchsdaten. 
   Wir möchten die Schaltfläche **Einchecken** aktivieren, wenn der Besuchsdatensatz gefunden wurde (nicht leer), der Datensatzstatus aktiv ist, und der Besuch noch nicht begonnen hat, d. h. der tatsächliche Startwert leer ist.

   * Wählen Sie auf der Registerkarte „Eigenschaften“ die Schaltfläche „Einchecken“ aus, und klicken Sie dann auf die Eigenschaft **DisplayMode** der Schaltfläche.

   * Geben Sie den folgenden Ausdruck in die Funktionsleiste ein.

      ```
      If(!IsBlank(Visit) 
      && Visit.Status = 'Status (Visits)'.Active
      && IsBlank(Visit.'Actual Start'),
          DisplayMode.Edit,
          DisplayMode.Disabled
      )
      ```

   Der Ausdruck kann wie folgt unterteilt werden:

   * `!IsBlank(Visit)` – Besuchsdatensatz wurde gefunden
   * `&&` – logischer AND-Operator
   * `Visit.Status = 'Status (Visits)'.Active` Status des Datensatzes ist *Aktiv*
   * `IsBlank (Visit.'Actual Start ')` – Das Feld „Aktiver Start“ enthält keine Daten.

4. Wir möchten die Schaltfläche **Auschecken** aktivieren, wenn der Besuchsdatensatz gefunden wurde (nicht leer ist), der Datensatzstatus aktiv ist und der Besuch bereits gestartet wurde, d. h., der tatsächliche Startwert ist nicht leer.

   * Wählen Sie auf der Registerkarte „Eigenschaften“ die Schaltfläche „Auschecken“ aus, und klicken Sie dann auf die Eigenschaft  **DisplayMode** der Schaltfläche.

   * Geben Sie den folgenden Ausdruck in die Funktionsleiste ein.

     ```
     If(!IsBlank(Visit) 
     && Visit.Status = 'Status (Visits)'.Active
     && !IsBlank(Visit.'Actual Start'),
         DisplayMode.Edit,
         DisplayMode.Disabled
     )
     ```

5. Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei \| Speichern** und anschließend auf **Speichern**. Klicken Sie oben rechts (unter „Power Apps“) auf den Rückwärtspfeil, um zur App zurückzukehren.

6. Drücken Sie **F5**, um die App auszuführen. Beide Tasten sollten deaktiviert sein. Geben Sie den zuvor kopierten Code ein, und drücken Sie **Tab**, um den Fokus vom Textfeld zu nehmen. Die Schaltfläche **Einchecken** sollte aktiviert werden.

7. Drücken Sie **ESC** um die laufende App zu beenden.

## Aufgabe 4: Ein- und Auscheckvorgang abschließen

Um den Ein- und Auscheckvorgang durchzuführen, müssen die Common Data Service-Besuchsdaten wie folgt aktualisiert werden:

* Wenn der Besucher eincheckt, setzen Sie das Feld *Tatsächlicher Start* auf das aktuelle Datum und die aktuelle Uhrzeit.
* Wenn der Besucher auscheckt, setzen Sie das Feld *Tatsächliches Ende* auf das aktuelle Datum und die aktuelle Uhrzeit. 
* Setzen Sie den Datensatzstatus nach dem Auschecken auf inaktiv, um anzuzeigen, dass der Besuch abgeschlossen wurde.

1. Klicken Sie auf die Schaltfläche **Einchecken**.

2. Legen Sie die Eigenschaft **OnSelect** auf den folgenden Ausdruck fest.

   ```
   Patch(
       Visits,
       Visit,
       {'Actual Start': Now()}
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   Dieser Ausdruck enthält die folgenden Informationen:

   * `Patch(Visits, Visit, {'Actual Start': Now()});`. Die *Patch*-Methode aktualisiert die Entität **Besuche**, der durch die Variable **Besuch** (der aktuelle Besuch) identifizierte Datensatz. Der Ausdruck legt den Wert des Felds *Tatsächlicher Start* auf das aktuelle Datum und die aktuelle Uhrzeit (*Jetzt()* Methode) fest.
   * `Refresh([@Visits]);`. Dieser Ausdruck aktualisiert die Besuchsdatensätze, wenn sich die zugrunde liegenden Werte geändert haben.
   * `Set (Visit, LookUp (Visits, Code = textCode.Text));` Dieser Ausdruck aktualisiert die Variable *Besuch* mit aktuellen Daten von CDS.

3. Wählen Sie die Schaltfläche **Auschecken**.

4. Legen Sie die Eigenschaft **OnSelect** auf den folgenden Ausdruck fest.

   ```
   Patch(
       [@Visits],
       Visit,
       {
           'Actual End': Now(),
           Status: 'Status (Visits)'.Inactive
       }
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   Der einzige Unterschied zum Ausdruck „einchecken“ besteht im Festlegen des Felds *Status* auf den Wert *Inaktiv*.

5. Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei \| Speichern** und anschließend auf **Speichern**.

6. Drücken Sie **F5** zum Ausführen der App. Geben Sie den zuvor kopierten Code ein, und drücken Sie **Tab**, um den Fokus vom Textfeld zu nehmen. Die Schaltfläche **Einchecken** sollte aktiviert werden.

7. Klicken Sie auf die Schaltfläche **Einchecken**. Folgendes sollte geschehen:

   1. *Tatsächlicher Start* hat ein aktuelles Datum und eine aktuelle Uhrzeit
   2. Die Schaltfläche **Einchecken** wird deaktiviert
   3. Die Schaltfläche **Auschecken** wird aktiviert

8. Klicken Sie auf die Schaltfläche **Auschecken**.

   1. *Tatsächliches Ende* hat ein aktuelles Datum und eine aktuelle Uhrzeit
   2. Beide Schaltflächen sind deaktiviert

9. Drücken Sie **ESC** um die laufende App zu beenden.

Aufgabe 5: Visuelle Indikatoren hinzufügen
--------------------------------------

Die Benutzerfreundlichkeit einer mobilen App wird erheblich verbessert, wenn zusätzlich zu den Textinformationen die visuellen Indikatoren bereitgestellt werden. In dieser Aufgabe fügen wir ein Symbol hinzu, das angibt, ob ein Besucher ein- oder ausgecheckt werden kann.

1. Wählen Sie die Registerkarte **Einfügen** aus.

2. Wählen Sie **Symbole \| Hinzufügen**. An dieser Stelle spielt es keine Rolle, welches Symbol wir auswählen, da der Wert dynamisch sein soll.

3. Ändern Sie die Größe des Symbols, und platzieren Sie es in der Mitte des Bildschirms unter den Schaltflächen.

4. Wählen Sie auf der Registerkarte „Erweitert“ für das Symbol die Eigenschaft **Symbol** aus (im Abschnitt „Design“), und geben Sie den folgenden Ausdruck ein

   ```
   If(
      CheckInButton.DisplayMode = DisplayMode.Disabled 
   && CheckOutButton.DisplayMode = DisplayMode.Disabled,
       Icon.EmojiFrown,
       Icon.EmojiSmile
   )
   ```

5. Um die aktuellen Änderungen beizubehalten, klicken Sie auf **Datei \| Speichern** und anschließend auf **Speichern**.
6. Drücken Sie **F5** zum Ausführen der App. Geben Sie den zuvor kopierten Code ein, und drücken Sie **Tab**, um den Fokus vom Textfeld zu nehmen. Stellen Sie sicher, dass das Symbol ein Stirnrunzeln-Emoji anzeigt.
7. Suchen Sie einen anderen Codewert, der bisher noch nicht verwendet wurde (er sollte keinen tatsächlichen Start- oder Endwert haben). Sie können die zuvor erstellte App **Campus-Mitarbeiter** ausführen, um neue Besuchsdatensätze zu erstellen. Stellen Sie sicher, dass das Symbol ein Lächeln-Emoji anzeigt.
8. Drücken Sie **ESC** um die laufende App zu beenden.

## Aufgabe 6: Die App veröffentlichen

1. Sie sollten die App „Campus-Sicherheit“ weiterhin in Ihrem Browser geöffnet haben. Wenn nicht, wählen Sie die App **Campus-Sicherheit** aus, und klicken Sie auf **Bearbeiten**.
2. Wählen Sie **Datei \| Veröffentlichen** 
3. Wählen Sie **Diese Version veröffentlichen** aus.

# Herausforderungen

* Wie vermeide ich die manuelle Eingabe des Besuchscodes?
* Fügen Sie eine Gebäudevalidierung für den Besuch hinzu.
* Hinzufügen einer Validierung der tatsächlichen Besuchszeit im Vergleich zur geplanten Besuchszeit hinzu (zu früh, zu spät usw.).
* Fügen Sie einen detaillierten Status des Besuchs hinzu, wie etwa eine. E-Mail-Anzeige und -Prüfung für den Besucher, Grund für die Verweigerung des Gebäudezugangs usw.
* Wie würden Sie mit den Anforderungen mehrerer Gebäude/Besprechungen/Überprüfungen während eines einzelnen Campusbesuchs umgehen? Zum Beispiel kann jemand den Campus für einen Tag besuchen und an diesem Tag Mitarbeiter in mehreren Gebäuden zu unterschiedlichen Tageszeiten treffen. Würden Sie in Betracht ziehen, die Entität *Termin* in die Lösung einzubeziehen?
