# EazyMenu Documentation

## Anmerkung

Wir werden hier einige Daten einfügen, die wir für unsere Diplomarbeit verwenden werden. Da die Firewall in der Firma Github blockiert werden wir voraussichtlich in dieser Readme alles Dokumentieren.

Github Pages: [EazyMenu Index](https://musikfreunde.github.io/eazy-menu-docs/) (Noch nicht fertig)

## Info 

EazyMenu ist eine Webanwendung, die für Arbeiter der Oberösterreichischen Versicherung entwickelt wird, um essen bei einer Kantine zu bestellen.

## Team

* Benjamin Besic
* David Ignjatovic
* Bozidar Spasenovic


## ERD Alt

Die linke Seite ist schon von der Firma vorgegeben worden. Es werden aber kleine Details geändert und verbessert. 

![ERD-alt](erd.png)

Dieses ERD ist veraltet. Laut der Firma ist es zu groß und detailliert. Die Kantine findet es besser wenn, es vereinfacht wird.

## ERD Neu

Diese ERD ist (stand 06.07.2021), laut der Firma, in Ordnung und wird auch verwendet.

![ERD-neu](erd-neu.png)

## Beschreibung Datenmodell

Beschreibung des Datenmodells: 
Owner: OOEVKANTINE  
**Tabelle: KANTINE**

<tbody>

<tr>

<th class="confluenceTh">Spalte</th>

<th class="confluenceTh">Typ</th>

<th class="confluenceTh">Optional</th>

<th class="confluenceTh">Kommentar</th>

<th class="confluenceTh">Hinweis</th>

</tr>

<tr>

<td class="confluenceTd">KANTINE_ID</td>

<td class="confluenceTd">NUMBER(3,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Künstlicher interner Schlüssel, welcher durch die Sequnce KANTINE_SEQ zu befüllen ist.</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">KANTINENBEZEICHNUNG</td>

<td class="confluenceTd">VARCHAR2(200 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Bezeichnung der Kantine</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">SERVICEBEZEICHNUNG</td>

<td class="confluenceTd">VARCHAR2(200 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Gruppenbezeichnung der Öffnungszeiten</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">STATUSKZ</td>

<td class="confluenceTd">VARCHAR2(1 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Kennzeichen, ob der Kantineneintrag (A)ktiv oder (I)naktiv ist</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Datum der Ersterstellung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, der den Datensatz erstellt hat</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Zeitstempel der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

</tbody>

</table>

</div>

**Tabelle: OEFFNUNGSZEIT**

<div class="table-wrap">

<table class="confluenceTable">

<tbody>

<tr>

<th class="confluenceTh">Spalte</th>

<th class="confluenceTh">Typ</th>

<th class="confluenceTh">Optional</th>

<th class="confluenceTh">Kommentar</th>

<th class="confluenceTh">Hinweis</th>

</tr>

<tr>

<td class="confluenceTd">OEFFNUNGSZEIT_ID</td>

<td class="confluenceTd">NUMBER(4,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Künstlicher interner Schlüssel, welcher durch die Sequnce OEFFNUNGSZEIT_SEQ zu befüllen ist.</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">KANTINE_ID</td>

<td class="confluenceTd">NUMBER(3,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">verpflichtende Referenz auf den künstlichen internen Schlüssel der Tabelle KANTINE.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">STATUSKZ</td>

<td class="confluenceTd">VARCHAR2(1 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Kennzeichen, ob der Öffnungszeiteneintrag (A)ktiv oder (I)naktiv ist.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ZEITFESTERVON</td>

<td class="confluenceTd">VARCHAR2(5 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">"Beginn des Zeitfensters, ab dem die Kantine geöffnet ist. Formatvorgabe hh24:mi"</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ZEITFESTERBIS</td>

<td class="confluenceTd">VARCHAR2(5 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">"Ende des Zeitfensters, ab dem die Kantine geöffnet ist. Formatvorgabe hh24:mi"</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">MAXPLAETZE</td>

<td class="confluenceTd">NUMBER(4,0)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Maximale Anzahl von Plätzen, die in dem definierten Zeitfester verfügbar sind. NULL steht für keine Einschränkung.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Datum der Ersterstellung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, der den Datensatz erstellt hat</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Zeitstempel der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

</tbody>

</table>

</div>

**Tabelle: MENUE**

<div class="table-wrap">

<table class="confluenceTable">

<tbody>

<tr>

<th class="confluenceTh">Spalte</th>

<th class="confluenceTh">Typ</th>

<th class="confluenceTh">Optional</th>

<th class="confluenceTh">Kommentar</th>

<th class="confluenceTh">Hinweis</th>

</tr>

<tr>

<td class="confluenceTd">MENUE_ID</td>

<td class="confluenceTd">NUMBER</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Künstlicher interner Schlüssel, welcher durch die Sequnce MENUE_SEQ zu befüllen ist.</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">KANTINE_ID</td>

<td class="confluenceTd">NUMBER(3,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">verpflichtende Referenz auf den künstlichen internen Schlüssel der Tabelle KANTINE.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">MENUEDATUM</td>

<td class="confluenceTd">DATE</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Datum, an dem das Menü gültig ist</td>

<td class="confluenceTd">die Datenbank wird das Datum immer abschneiden => Datum mit der Uhrzeit 00:00:00</td>

</tr>

<tr>

<td class="confluenceTd">MENUECODE</td>

<td class="confluenceTd">VARCHAR2(1 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Kennzeichnung des Menüs innerhalb eines Tages (A, B, C ...)</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">VORSPEISE</td>

<td class="confluenceTd">VARCHAR2(2000 CHAR)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Beschreibung der Vorspeise</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">HAUPTSPEISE</td>

<td class="confluenceTd">VARCHAR2(2000 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Beschreibung der Hauptspeise</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">NACHSPEISE</td>

<td class="confluenceTd">VARCHAR2(2000 CHAR)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Beschreibung der Nachspeise</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Datum der Ersterstellung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, der den Datensatz erstellt hat</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Zeitstempel der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

</tbody>

</table>

</div>

**Tabelle: BESTELLUNG**



<tbody>

<tr>

<th class="confluenceTh">Spalte</th>

<th class="confluenceTh">Typ</th>

<th class="confluenceTh">Optional</th>

<th class="confluenceTh">Kommentar</th>

<th class="confluenceTh">Hinweis</th>

</tr>

<tr>

<td class="confluenceTd">BESTELLUNG_ID</td>

<td class="confluenceTd">NUMBER</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Künstlicher interner Schlüssel, welcher durch die Sequnce BESTELLUNG_SEQ zu befüllen ist.</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">OEFFNUNGSZEIT_ID</td>

<td class="confluenceTd">NUMBER(4,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Auswahl einer Servicezeit - verpflichtende Referenz auf den künstlichen internen Schlüssel der Tabelle OEFFNUNGSZEIT.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">MENUE_ID</td>

<td class="confluenceTd">NUMBER</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Auswahl des Menüs - verpflichtende Referenz auf den künstlichen internen Schlüssel der Tabelle MENUE.</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">BESTELLTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, der die Bestellung durchgeführt hat</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">BESTELLTFUER</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, für den die Bestellung durchgeführt wurde (Konsument)</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">KOMMENTAR</td>

<td class="confluenceTd">VARCHAR2(4000 CHAR)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Zusatzwünsche an die Kantine</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">PERSONALNUMMER</td>

<td class="confluenceTd">NUMBER(5,0)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Personalnummer zur Verrechnung des Menüs (in der Regel die Nummer des Konsumenten)</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ANZAHL</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Anzahl der Menüs, die bestellt wurden</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">STORNIERTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Datum der Stornierung</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ABGERECHNETUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Zeitpunkt, wann die Bestellung abgerechnet wurde</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">KOSTENSTELLE</td>

<td class="confluenceTd">NUMBER(5,0)</td>

<td class="confluenceTd">Yes</td>

<td class="confluenceTd">Kostenstelle, gegen die die Kosten verrechnet werden</td>

<td class="confluenceTd"> </td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Datum der Ersterstellung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">ANGELEGTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User, der den Datensatz erstellt hat</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTUM</td>

<td class="confluenceTd">TIMESTAMP(6)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">Zeitstempel der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

<tr>

<td class="confluenceTd">GEAENDERTVON</td>

<td class="confluenceTd">VARCHAR2(32 CHAR)</td>

<td class="confluenceTd">No</td>

<td class="confluenceTd">User der letzten Änderung</td>

<td class="confluenceTd">muss nicht von der Anwendung befüllt werden; DB-Trigger vorhanden</td>

</tr>

</tbody>

</table>



Zusatz: 
* zu jeder Tabelle gibt es eine technische History-Tabelle, welche automatisch bei DMLs mitgewartet werden. Es dürfte KEINEN Geschäftsfall geben, wo die Anwendung auf diese Tabellen (*_h) zugreifen sollte. 
* es wurden bereits eine Handvoll Testdaten erzeugt (verscripted, damit wiederholbar und ausbaufähig)</div>

## Mockups

### Login

Einfaches Login für die Mitarbeiter, aber auch Kantine und Personal. Wird wahrscheinlich mit Keycloak gemacht.
![login](login-View.png)

### Menü Übersicht 

Hier wird jedes Menü angezeigt zum davor ausgewählten Datum. Der User kann zwischen 3 Mahlzeiten wählen.

![übersicht](menubestellung-übersicht.png)

### Formular Übersicht (Nach Auswahl des Menüs)

Der User muss nach auswahl der Mahlzeit dieses "Formular" ausfüllen. Die muss auswählen, um wie viel Uhr gegessen wird und wie viel Mahlzeiten konsumiert werden.

![übersicht-onClick](menubestellung-übersicht-onClick.png)

### History

Hier werden alle Mahlzeiten angezeigt, welcher der User gegessen hat.

![history mockup-view](history.png)


