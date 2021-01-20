# Modul242 Dokumentation für die LB3

Unsere Dokumentation zur Leistungsbeurteilung 3

## Inhaltsverzeichnis:
1 [Allgemeine Bewertungskriterien](#Allgemein)<br>
&nbsp;1.1 [K1: Umgebung auf eigenem Notebook eingerichtet und voll funktionsfähig](#K1)<br>
&nbsp;1.2 [K2: Eigene Lernumgebung ist eingerichtet](#K2)<br>
&nbsp;1.3 [K3: IoTKit](#K3)<br>
&nbsp;1.4 [K4: Gateway / Edge](#K4)<br>
&nbsp;1.5 [K5: (Cloud) Dienst](#K5)<br>
&nbsp;1.6 [K6: Zusätzliche Bewertungspunkte](#K6)<br>
2 [Unsere Idee](#Idee)<br>
3 [Unsere Arbeitsaufteilung](#Arbeitsaufteilung)<br>
4 [Unsere Lösung](#Lösung)<br>
&nbsp;4.1 [Netzwerkplan](#Netzwerkplan)<br>
5 [Konfiguration/Installation](#Konfiguration)<br>
&nbsp;5.1 [IoKit](#IoKit)<br>
&nbsp;5.2 [Gateway](#Gateway)<br>
&nbsp;5.2.1 [VPN](#Gateway)<br>
&nbsp;5.3 [Cloud](#Cloud)<br>
6 [Testprotokolle](#Testprotokolle)<br>
7 [Persönlicher Wissensstand und Reflexion](#Wissensstand)<br>
&nbsp;7.1 [Adam](#Adam)<br>
&nbsp;7.2 [Alex](#Alex)<br>
&nbsp;7.3 [Even](#Even)<br>
&nbsp;7.4 [Jason](#Jason)<br>

## 1 Allgemeine Bewetungskriterien <a name="Allgemein"></a>
### 1.1 K1: Umgebung auf eigenem Notebook eingerichtet und voll funktionsfähig <a name="K1"></a>

- Account auf os.mbed.com erstellt
- Serial Driver installiert
- Terminal Programm installiert

### 1.2 K2: Eigene Lernumgebung ist eingerichtet <a name="K2"></a>

- Dokumentation vorhanden
- Persönlicher Wissenstand in Bezug auf die wichtigsten Themen ist dokumentiert (IoT, Sensoren, Aktoren, Service)
- Wichtige Lernschritte sind dokumentiert
- Anhand der Dokumentation können Dritte das Projekt nachbauen

### 1.3 K3: IoTKit <a name="K3"></a>

- Beispiel Programm verwendet
- Beispiel Programm geringfügig abgeän-dert, z.B. nur URL 
- Beispiel Programm erweitert, z.B. mehr Sensordaten senden oder andere Daten.

### 1.4 K4: Gateway / Edge <a name="K4"></a>

- Eigenen Gateway/Edge aufgesetzt (Rasp-berry Pi, VMs etc.)
- Gateway Dienst installiert, z.B. MQTT Bro-ker mosquitto
- Zusätzlichen Dienst, für Workflow Abhand-lung, z.B. Node-RED installiert
- Weiteren Gateway / Protokoll Dienst instal-liert und funktionsfähig

### 1.5 K5: (Cloud) Dienst <a name="K5"></a>

- (Cloud) Dienst aus den Beispielen verwen-det
- Neuen, welcher nicht in den Beispielen vorkommt, Dienst verwendet
- Eigenen (Cloud) Dienst implementiert
- Kommunikation erfolgt verschlüsselt, z.B. mittels HTTPSoder mittels VPN

### 1.6 K6: Zusätzliche Bewertungspunkte <a name="K6"></a>
- Allgemein (Kreativität, Komplexität, Um-fang)
- Umsetzung eigener Ideen
- Persönlicher Lernentwicklung (Vergleich Vorwissen –Wissenszuwachs)
- Reflexion

# 2 Unsere Idee: <a name="Idee"></a>
Unser System besteht aus folgenden Teile:
- IoTKit
- Raspberry Pi,Gateway/MQTT Broker
- Cloud/Note-Red
# 3 Arbeitsaufteilung: <a name="Arbeitsaufteilung"></a> 
Wir arbeiten alle gemeinsamm an der Dokumentation und individuell arbeiten wir an folgenden Bestandteile:
- Even, IoKit 
- Adam, IoKit
- Alex, Gateway, MQTT Broker
- Jason, Cloud, Note-Red

# 4 Unsere Lösung: <a name="Lösung"></a>
 
## 4.1 Netzwerkplan: <a name="Netzwerkplan"></a>


# 5 Konfiguration/Installation: <a name="Konfiguration"></a>
## 5.1 IoKit Konfiguration: <a name="IoKit"></a>
## 5.2 Gateway/ MQTT Broker: <a name="Gateway"></a>
### 5.2.1 VPN: <a name="VPN"></a>
Konfiguration des VPN auf dem Raspberry Pi.

-Raspi updaten:
sudo apt-get update
sudo apt-get upgrade
-Raspi konfigurieren
sudo raspi-config -> Hostnamen und Netzwerk anpassen
-PiVPN installieren
curl -L https://install.pivpn.io | bash

![MC-Connecten](https://github.com/Even-Dietrich/Modul300/blob/master/LB3/img/MC-Connecten.png)
## 5.3 Cloud: <a name="Cloud"></a>

## 6 Testprotokolle: <a name="Testprotokolle"></a><br>

# 7 Persönlicher Wissensstand und Reflexion: <a name="Wissensstand"></a><br>
## 7.1 Adam: <a name="Adam"></a><br>
## 7.2 Alex: <a name="Alex"></a><br>
## 7.3 Even: <a name="Even"></a><br>
## 7.4 Jason: <a name="Jason"></a><br>
