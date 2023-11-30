# Grundlegende Informationen
## Erfunden am
### 1998
## Bitlänge
### 128 bit
## Anzahl der Adressen
### <340 Sextillionen
## Schreibweise 
### 2001:0DB8:0000:0000:0000:0000:0000:FFFF
### Heißt Hexadezimaldarstellung
### wird für besser Lesbarkeit nach 4 Hexazahlen mit ":" getrennt.
### Regelungen der Darstellung:
#### Führende 0 dürfen weggelassen werden: 2001:DB8:0:0:0:0:0:FFFF
#### Gruppen mit nur aus Nullern düffen mit "::" Weggelassen werden: 2001:DB8::FFFF
##### Die Kurzform "::" darf nur einmal vorkommen
#### Präfixangabe: IPv6-Adresse /Präfixangabe
### Darstellung bei URI-Form ("Uniform Resource Identifier")
#### Um Kollisionen wegen den Syntax von Port zu vermeiden, wird die IPv6 in [...] gesetzt:
#### http://[IPv6-Adresse]:Port/Pfadname
# Header
## Kürzer als IPv4
## Felder
### Version (4 Bit): Gibt an welche IP Version genutzt wird
### Traffic Class (8 Bit): Zeigt die Priorität des Paketes
### Flow Label (20 Bit): Kennzeichen von Pakete für schnellere Routing
### Payload Length (16 Bit): Transportierte Lenge des IP Paketes
### Next Header (8 Bit): Hier ist das Übergeordnete Transport Protokoll angegeben
### Hop-Limit (8 Bit): Erhält die Hopanzahl wie lang der Paket leben soll (TTL-Feld IPv4):
### Absenderadresse (128 Bit): Hier steht Quell-Adresse
### Zieladresse (128 Bit): Hier steht Ziel-Adresse
# Adressbereiche
## Allgemeine Bereich:
### Link-Local-Adresse (Kürzung: LLA, Präfix: FE80)
#### Gilt nur für den Jeweilige Netzwersegment
#### Link-Local = Direkte Verbindung auf OSI Ebene 1 und 2
#### Wegen Abschaffung von Broadcast muss jede Gerät einen davon Besitzen
#### besitzt Neighbor Discovery was ARP (Address Resolution Protocol) Ablösen soll
#### Stateless Address Autoconfiguration (SLAAC) alternative zur DHCP
### Unique Local Address (Kürzung: ULA, Präfix: Fc00 - fdff)
#### Für Private Lokale Netze 
#### Man Unterscheidet zwischen fc und fd:
##### fc: unique local (zentral Verwaltet). Diese Adresse werden vom Provider vergeben
##### fd: uique local (lokal verwaltet). Diese Adressen können im eigenen lokalen Netzwerk verwendet werden
##### präfix mit FD sind für Lokal generierten Adressen vorgesehen
#### D