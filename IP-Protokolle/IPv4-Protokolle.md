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
### Wenn der Client nicht schaffen tut die IP-Adresse zu bekommen wird bei ihm 0.0.0.0 als default Wert angezeigt 
## Es gibt 2 Redundanzmodelle:
### Kooperativ
#### Mehrere Servern mit selben Adressen-Pool die immer abgeglichen wird
#### Entweder jeder Server antwortet auf Anfrage oder Ein Server, und die anderen werden zur Standbyservern
##### Standbyserver = Server der Einspringt wenn der Hauptserver defekt ist

### nicht Kooperativ
#### Jeder Server hat eigene Adressen-Pool
#### Wenn ein Server ausfällt kann ein anderer Übernehmen
##### Adressen-Pool müsste dementsprechend groß sein
