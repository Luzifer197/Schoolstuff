# IPv6
## Grundlegende Informationen
### Erfunden am
#### 1998
### Bitlänge
#### 128 bit
### Anzahl der Adressen
#### <340 Sextillionen
### Schreibweise 
#### 2001:0DB8:0000:0000:0000:0000:0000:FFFF
#### Heißt Hexadezimaldarstellung
#### wird für besser Lesbarkeit nach 4 Hexazahlen mit ":" getrennt.
#### Regelungen der Darstellung:
##### Führende 0 dürfen weggelassen werden: 2001:DB8:0:0:0:0:0:FFFF
##### Gruppen mit nur aus Nullern düffen mit "::" Weggelassen werden: 2001:DB8::FFFF
###### Die Kurzform "::" darf nur einmal vorkommen
##### Präfixangabe: IPv6-Adresse /Präfixangabe
#### Darstellung bei URI-Form ("Uniform Resource Identifier")
##### Um Kollisionen wegen den Syntax von Port zu vermeiden, wird die IPv6 in [...] gesetzt:
##### http://[IPv6-Adresse]:Port/Pfadname
## Header
### Kürzer als IPv4
### Felder
#### Version (4 Bit): Gibt an welche IP Version genutzt wird
#### Traffic Class (8 Bit): Zeigt die Priorität des Paketes
#### Flow Label (20 Bit): Kennzeichen von Pakete für schnellere Routing
#### Payload Length (16 Bit): Transportierte Lenge des IP Paketes
#### Next Header (8 Bit): Hier ist das Übergeordnete Transport Protokoll angegeben
#### Hop-Limit (8 Bit): Erhält die Hopanzahl wie lang der Paket leben soll (TTL-Feld IPv4):
#### Absenderadresse (128 Bit): Hier steht Quell-Adresse
#### Zieladresse (128 Bit): Hier steht Ziel-Adresse
## Adressbereiche
### Allgemeine Bereich:
#### Unspecified Addresse (::)
##### Wird verwendet, wenn eine IPv6-Adresse nicht spezifiziert ist
##### Merkmale
###### Alle bits sind auf 0 Gesetzt
###### Wird  als Platzhalter/Platzhalteradresse verwendet
###### Kann als Quelladresse in Anforderungen dienen, bei denen die genaue Adresse noch nicht bekannt ist
###### Kann nicht als Zieladresse in Paketen verwendet werden

#### Loopback Addresse (::1)
##### Dient dazu, eine Netzwerkverkehr zu sich selbst zu testen
##### Merkmale
###### Alle Bits außer dem Niedrigsten Wert sind auf 0 gesetzt
###### Repräsentiert den Lokalen Host
###### Verwendet für lokale Tests und Diagnosen
###### Funktioniert ähnlich wie die IPv4-Loopback-Adresse(127.0.0.1)

#### Link-Local-Addresse (Kürzung: LLA, Präfix: FE80)
##### Nur gültig innerhalb eines Netzwerksegments (Link)
##### Link-Local = Direkte Verbindung auf OSI Ebene 1 und 2
##### Merkmale
###### Automatisch auf jeder Netzwerkschnittstelle erstellt
###### Wird für die Kommunikation auf dem lokalen Netzwerksegment verwendet
###### Erfordert keine Konfiguration (z. B. durch DHCP)
###### Nicht routbar über das lokale Netzwerk hinaus

#### Unique Local Addresse (Kürzung: ULA, Präfix: Fc00 - fdff)
##### Für Private Lokale Netze 
##### Merkmale
###### fc:Entworfen für lokale Verwendung in privaten Netzwerken.
###### Nicht routbar im Internet.
###### Analog zu IPv4-Private-Adressen (z. B. 192.168.x.x).
###### Kann zur Verhinderung von Adresskonflikten in globalen Routern verwendet werden.

#### Global Unicast Addresse (Präfix: 2000::/3)
##### Öffentlicher Adressraum für den Interentverkehr
##### Merkmale
###### Global routbare Adressen im Internet
###### Eindeutige Identifikation von Geräten und Netzwerken
###### Subnetzpräfix werden von den Regionale Internet Regisitries (RIRs) zugewiesen
###### Ersetzt weitgehend den begrenzten Adressraum von IPv4

#### Multicast Addresse (Präfix: ff00::/8)
##### Zum Senden von Paketen an mehrer Empfänger Gleichzeitig
##### Merkmal
###### Identifiziert Gruppen von Empfängern
###### Kann für Multicast-Kommunikation in Netzwerken Verwendet werden
###### Unterstützt effiziente Ressourcennutzung durch das Senden an ausgewählte Gruppen