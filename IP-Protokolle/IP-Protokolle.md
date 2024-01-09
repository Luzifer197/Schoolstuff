# IPv4
## Grundlegende Informationen
### Erfunden am
#### 1982
### Bitlänge
#### 32 Bit
### Anzahl der Adressen
#### 2^32
#### 4,294 Milliarden
### Schreibweise
#### 192.168.1.1
#### Subnetzmaske
##### zeigt welche bit zur Host und Netz-Anteil der Adresse gehört
##### Dotted-Schreibweise: 255.255.255.0
##### Slash-Schreibweise: /24
###### Hier gibst du die Stelle an das getrennt wird, hier ist es ab den 24 Bit
## Header-IPv4
### Header
#### Präamble
##### 56 Bit langes 1ser und 0er zur Taktsynchronisation
#### SFD (Start Frame Delimiter)
##### Bitmuster(1010110001) zur anzeige der Eigentliche Framebeginn
#### DA (Destination Adress)
##### Empfänger-Marc Adresse (Broadcast = FF:FF:FF:FF:FF:FF)
#### SA (Source Address)
##### Sende Marc Address
#### LEN (Lenght)
##### Länge des Folgende Datensatz
### Body
#### Data
##### Der Eigentliche Datensatz
### Trailer
#### PAD (Padding)
##### Dient zum Auffühllen des Datenfeldes auf 46 Bits
#### FCS (Frame Check Sequenz)
##### Rahmenprüfsumme zur Fehlererkennung
## Adressen-Klassen sind Folgende:
### Klasse A
#### von 10.0.0.0 - 10.255.255.255
#### ID: 10.0.0.0/8
### Klasse B
#### von 172.16.0.0 - 172.31.255.255
#### ID: 172.16.0.0/12
### Klasse C
#### von 192.168.0.0 - 192.168.255.255
#### ID: 192.168.0.0/16
## NAT (Network Adress Translation)
### Adressen Übersetzer von Privatnetzwerke und Öffentliche Netzwerke

## ARP (Address Resolution Protocol)
### Ermöglicht ein Gerät lokal nach den dazugehörige MAC-Adresse zur ein IP-Adresse zu finden und zu Speichern
### Wenn die MAC-Adresse nicht in ARP-Tabelle ist wird ein ARP-Broadcast gesendet "Ich such den Gerät mit IP 192.168.2.2, brauche deine MAC-Adresse"
### Das Gerät mit den IP-Adresse 192.168.2.2 antwortet mit seinen MAC-Adresse
### Die MAC-Adresse wird dan in den ARP Tabelle gespeichert

## DNS (Dynamic Name solution)
### Der DNS Server übersetzt Symbolische Adressen in IP-Adressen wie z.b. Google.de

## DHCP (Domain Host Configurature Protokoll)
### Ermöglicht die Automatisierte Verteilung von IP-Konfigurationen (IP-Adresse, Subnetzmaske, DNS-Server, Gateway, ...) durch DHCP-Server an DHCP-Client
### Hat folgende Parametern:
#### Permament: Der DHCP-Client kann die ihm aus dem Adresspool zugeteilte Adresse auf unbestimmte Zeit nutzen
#### Statisch: Der DHCP-Client erhält eine bestimmte für ihn reservierte Adresse zugeteilt er erhält somit immer dieselbe Adresse
#### Dynamic: Der DHCP-Client erhält ein die ihm aus den Adresspool zugeteilte Adresse eine bestimmte Zeit
### diese Gültigskeitsdauer nennt sich Lease
### Lease-Time wird nach folgende Sachen Bestimmt:
#### Von Anzahl der IP-Adressen
#### Häufigkeit der Änderungen wichtiger DHCP-Server
#### Von die Client
#### Von der Art der Arbeitsstationen im Netz
#### der Zeitspanne die es dauert, bis die Störungen die zu Nichterreichbarkeit von DHCP-Server führt
### Die Anfrage läuft diese Schritte ab:
#### DHCP-Discover: von DHCP-Client Aufforderung per Broadcast an alle DHCP-Server 
#### DHCP-Offer: Antwort auf DHCP-Discover mit Angebot einer IP-Konfiguration
#### DHCP-Request: Annehmen des DHCP-Offers eines Server und gleichzeitig ablehnen der Angeboten andere Server.
#### DHCP-ACK: Bestätigung des DHCP-Servers, dass Konfiguration verwenden kann.
### Um doppelte IP-Adressen in Netz zu vermeiten tut der DHCP-Client am ende des DHCP-Ark noch ARP-Request stellen

# IPv6
## Grundlegende Informationen
### Erfunden am
#### 1998
### Bitlänge
#### 128 Bit
### Anzahl der Adressen
#### 16^128
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

