# DB-Test

## Aufgabe 1
Stelle Entitäten mittels Chen-Notation und Min,Max Notation dar.
Wähle ein sinnvolles Beispiel!

## Antwort 1
siehe Bild 1
kenn mich mit Min/Max nicht aus



## Aufgabe 2
Kann eine Beziehung Attribute haben?
Wenn ja, wie stelle ich es im ERD dar?

## Antwort 2
Ja
die Darstellung erfolgt, indem man neben das Diamant-Symbol für die Beziehung das Attribut gleich notiert schreiben wie man es bei einer Entität machen würde

==> Beispiel: 
jeder Mitarbeiter einer Firma ist mindestens einem Projekt zugeordnet (M:N) und hat ein Kontingent an Stunden im Monat/Quartal/Jahr (whatev’s), die er an diesem Projekt bzw. an diesen Projekten arbeiten kann/soll; diese M:N-Beziehung hat folglich das Attribut “Stunden_für_Projekt”, die dann in der assoziativen Tabelle bzw. der Datenbank-Entität “Mitarbeiter_in_Projekt” neben jeden Eintrag geschrieben werden



## Aufgabe 3
Welche Codd'schen Anforderungen gibt es (Nenne mindestens 5)

## Antwort 3

es soll der illegale Zugriff auf Daten verhindert werden
Daten sollen auf eine einzige Art dargestellt werden
Daten sollen so wenig Redundanzen wie möglich haben
es gibt mehrere Abfragesprachen, um auf Daten zugreifen zu können
es soll keine verschiedenen Sichten der Daten geben, d.h. Daten sollen immer auf dem aktuellen Stand in der Datenbank gespeichert sind



## Aufgabe 4
Nenne den Unterschied zwischen Konzeptuellen und Logischem Schema

## Antwort 4
das logische Schema bildet das konzeptuelle ab, hat aber kein “Bewusstsein” davon, was es eigentlich macht bzw. das konzeptuelle Schema erdenkt die Datenstruktur, wie sie für den Zweck am geeignetsten erscheint, man kann im logischen Schema einer Datenbank aber auch andere Abfragen aus der Datenbank machen als konzeptuell vorgesehen



## Aufgabe 5
Welche 3 Bestandteile gibt es im Entity Relationship Model

## Antwort 5
Entitäten: eine eigenständige Tabellen in einer Datenbank, welche die Informationen mit gewissen Inhalten darstellt

Attribute: die vorhin erwähnten Inhalte bzw. die konkreten Eigenschaften einer Entität; beispielsweise kann eine Tabelle/Entität für eine Person die Attribute “Vorname”, “Nachname”, “Alter”, “Gehalt” beinhalten

Relation: die Beziehung zwischen zwei oder mehreren Entitäten; 

beispielsweise kann eine Mutter mehrere biologische Kinder haben, aber nur ein Kind eine biologische Mutter haben ==> die Beziehung hierfür ist also N:1 binär, stellvertrend für “Mutter:Kind Beziehung von zwei Entitäten”



## Aufgabe 6
Welche Datentypen gibt es in MySQL? (Nenne mindestens 5)

## Antwort 6
int, string, date, bool, double



## Aufgabe 7
Welche Arten von Schlüsseln gibt es und welche Eigenschaften besitzen diese?

## Antwort 7
Primärschlüssel ==> ist das unverwechselbare Attribut einer Entität, von dem alle anderen Attribute voll funktional abhängig sind

Fremdschlüssel ==> ähnlich dem Primärschlüssel ist dieser das Attribut einer Entität, das benötigt wird, um z.B. in einer assoziativen Tabelle (zur Auflösung einer einer N:M-Beziehung) zwei Entitäten logisch miteinander zu verbinden; wenn beispielsweise dargestellt werden soll, dass Studenten Vorlesungen besuchen, braucht es zur Auflösung dieser N:M-Beziehung besagte assoziative Tabelle, in die Matrikelnummer der Primärschlüssel und die Kursnummer der Fremdschlüssel

zusammengesetzte Schlüssel: in manchen Fälle ist es nötig, nicht nur einen, sondern mehrere Primärschlüssel zu wählen, um eine eindeutige Identifizierung innerhalb einer Entität festzulegen 
==> wobei ich mir nicht mehr sicher bin, ob diese Schlüssel unnötig werden, sobald Daten in die 3. Form normalisiert wurden



## Aufgabe 8
Welche Arten von Beziehungen gibt es? Zeichne für jede ein Beispiel auf

## Antwort 8
1:1 ein Mensch hat (von Natur aus im Normalfall) ein Herz
1:N ein Mensch hat mehrere anderen Menschen, die er kennt
N:1 mehrere Kinder haben eine biologische Mutter
N:M mehrere Studenten besuchen mehrere Lehrveranstaltungen



## Aufgabe 9
Was bedeutet der Begriff Kardinalität und welche Kardinalitäten gibt es?

## Antwort 9
eine Kardinalität ist dann gegeben, wenn in einer ternären Beziezung zwischen Entitäten eine die anderen überwiegt



## Aufgabe 10
Was bedeutet der Begriff Datenintegrität und worin unterscheidet sich Integrität und referentielle Integrität?

## Antwort 10
weiß ich nicht



## Aufgabe 11
Erkläre die 3 Normalformen

## Antwort 11
NF 1: alle Daten sind in ihre kleinsten Bestandteile zerlegt; z.B. eine Tabelle hat kein Attribut “Name” (einer Person) mehr, in dem Vorname und Nachname stehen, sondern je eine Attribut “Vorname” und ein Attribut “Nachname”; nach dem gleichen Schema ist bspw. die Adresse einer Person in die Attribute “Ort”, “PLZ”, Straße”, “Hausnummer” und ggf. “Wohnungsnummer” (“Stiege”, “Stock”, etc) zerlegt und jeweils individuell befüllt

NF 2: alle Bedingungen der NF 1 sind erfüllt, zusätzlich sind alle Attribute, die kein Schlüsselattribut sind, in Abhängigkeit von Primärschlüsseln gebracht worden ==> eine einzelne große Tabelle mit vielen Redundanzen und Fehlerquellen wurde in mehrere Tabellen getrennt

NF 3: alle Bedingungen von NF 1 und NF 2 sind erfüllt, zusätzlich sind auch die Abhängigkeiten innerhalb der Menge an Nicht-Schlüsselattributen aufgelöst und durch Ausgliederung in entsprechende eigene Entitäten vereinfach ==>
beispielsweise wurde aus den Attributen in der “Personen”-Entität der Name des Wohnorts in eine eigene Entität ausgelagert, um Redundanzen und unnötige Fehler zu vermeiden



## Aufgabe 12
Erkläre den Unterschied zwischen starken und Schwachen Entitäten und erstelle ein Beispiel.

## Antwort 12
schwache Entitäten davon abhängig, das es starke Entitäten gibt, die diese logisch enthalten können; die starken sind die Voraussetzung dafür, dass die schwache überhaupt logisch existieren können ==> beispielsweise hat ein Gebäude mehrere Räume, es kann also ein einzelner Raum nicht ohne die Anwesenheit bzw. das Gegeben-Sein des Gebäudes nicht exisistieren



## Aufgabe 13
Welche Grundregeln gibt es im Relationenmodell? (Nenne mindestens 4)

## Antwort 13
weiß ich nicht



## Aufgabe 14
Wie löst man eine M:N Beziehung auf? Erstelle ein Beispiel

## Antwort 14
eine logischen M:N-Beziehung ist gegeben, wenn mehrere Entitäten logisch miteinander in mehr als nur einer Weise interagieren können

==> beispielsweise gibt es in einem Hotel mehrere Personen in einem Reingigungs-Team, jede Person kann/darf Raum reinigen, es kann also jede Person (N) mit jedem Raum (M) interagieren; um also diese Beziehung auflösen zu können, bedarf es einer Zwischenlösung - einer assoziative Tabelle: 
jede Person im Reingungs-Team ist als Attribut der Entität “Reingigung” dieser mit einer Person-ID zugeordnet, und jeder Raum als Attribut in der Entität “Raum” hat eine Raum-ID.

==> erstellt man nun eine neue Entität namens “Raum_Reinigung” und gibt als Attribute die Person-ID und die Raum-ID an, ist in der dieser assoziativen Tabelle eine Beziehung zwischen Reinigungs-Team und Räumen hergestellt; sollte nun beispielsweise ein Gast nach dem Check-Out feststellen, dass er etwas im Raum vergessen hat, kann durch diese Beziehung festgestellt werden, wer den Raum gereinigt hat und wen man folglich als erstes wegen des vergessenen Gegenstandes fragen kann



## Aufgabe 16
Welche Anomalien kennst du und was beschreiben sie?

## Aufgabe 16
Insert, Update und Delete

Anomalien treten dann auf, wenn Daten innerhalb einer Entität manipuliert werden;

Insert-Anomalie: 
beispielsweise werden in einem Formular entsprechende Felder nicht ausgefüllt, die für die Integrität des Datensatzes relevant wären; das System kann möglicherweise mit diesen unvollständigen Datensätzen nicht umgehen
(oder jemand schafft eine SQL-Injection und zerstört die Datenbank… wer weiß)

Update-Anomalie:
bestehende Daten (z.B. eines Amazon-Kundenkontos) werden aktualisiert und bei der Übertragung auf den Server passiert ein Fehler, sodass ein zuvor mit einem Wert versehenes Attribut plötzlich keinen Wert mehr enthält , oder dieser Wert ggf. doppelt eingetragen ist

Delete-Anomalie:
bei der Löschung von Daten (z.b. eines Kundenkontos) kann es passieren, dass nicht alle relevanten Attribute  aus allen betroffenen Entitäten gelöscht werden, und diese Fragmente können im Worst Case künftige Interaktionen mit der Datenbank erschweren
