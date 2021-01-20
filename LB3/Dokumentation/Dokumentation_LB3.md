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
4 [Dokumenation](#Dokumenation)<br>
&nbsp;4.1 [MQTT (Message Queue Telemetry Transport)](#MQTT)<br>
&nbsp;4.2 [Mosquitto](#Mosquitto)<br>
&nbsp;4.3 [Node-red](#nodered)<br>
5 [Unsere Lösung](#Lösung)<br>
&nbsp;5.1 [Netzwerkplan](#Netzwerkplan)<br>
6 [Konfiguration/Installation](#Konfiguration)<br>
&nbsp;6.1 [IoKit](#IoKit)<br>
&nbsp;6.2 [Gateway](#Gateway)<br>
&nbsp;6.2.1 [VPN](#Gateway)<br>
&nbsp;6.3 [Cloud](#Cloud)<br>
7 [Testprotokolle](#Testprotokolle)<br>
8 [Persönlicher Wissensstand und Reflexion](#Wissensstand)<br>
&nbsp;8.1 [Adam](#Adam)<br>
&nbsp;8.2 [Alex](#Alex)<br>
&nbsp;8.3 [Even](#Even)<br>
&nbsp;8.4 [Jason](#Jason)<br>

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
# 4 Dokumenation: <a name="Dokumenation"></a>
## 4.1 MQTT (Message Queue Telemetry Transport): <a name="MQTT"></a>

Bei MQTT handelt es sich um ein Nachrichten Protokoll, das im Bereich der Machine to Machine Kommunikation genutzt wird. Dazu gehört vor allem das übertragen von Messdaten in Form von Nachrichten auch bei hoher Verzögerung oder bei einer niedrigen Bandbreite. Dazu verwendet das Protokoll die Ports 1883 und 8883 und kann über das TLS-Protokoll verschlüsselt werden.

Folgende Geräte können MQTT verwenden:
- Sensoren/Aktoren
- Mobiltelefone
- System in Fahrzeuge
- Laptops

Wie funktioniert MQTT?<br>
Die Kommunikation erfolgt über eine Publish-Subscribe-Kommunikation. Die Kommunikation besteht dabei immer aus zwei Teilnehmer, den Broker und den Clients. Dabei hat der Client die Aufgabe die Kommunikation mit den Nachrichten publish und subscriben zu gewährleisten. Der Broker ist dazu da, um die Nachrichten zu verwalten und zu verteilen. Die ganzen Nachrichten funktionieren über sogenannte Topics. 

![MQTT](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/MQTT.png)

MQTT Topics<br>
Ein Topic ist ein Stringe, der eine Art Betreff der jeweiligen Nachricht darstellt. Diese Topics müssen danach vom Client abonniert werden damit dieser die Messdaten sehen kann. Sollte man die Messdaten nicht mehr gebrauchen kann man ganz einfach das Topic wieder deabonnieren und schon sieht man die Daten nicht mehr. 

Vorteile von MQTT:
- Sensor und Endgerät müssen sich nicht kennen. Keine IP-Adresse oder MAC-Adresse wird benötigt. 
- Publish und Subscribe sind unabhängig voneinander. Können separat ausgeführt werden. 
-	Asynchrone ausführen, Funktionalität der Computer wird somit nicht gestört.
## 4.2 Mosquitto: <a name="Mosquitto"></a>

Bei Mosquitto handelt es sich um ein Open Source-Nachrichtenbroker, dieser implementiert die MQTT Protokolle 5.0, 3.1.1 und 3.1.
Mosquitto ist simpel aufgebaut und eignet sich für alle Geräte, vom Server bis zum Singel-Board-Computer. 

Durch die einfach Installation und die gute Dokumentation wurde Mosquitto zu einem sehr beliebten MQTT Broker. Dieser Broker kann wie alle Broker als Zustands-Datenbank verwendet werden, da die Daten der Kommunikationspartner behalten werden und so vom MQTT Brokere abgefragt werden kann. Mosquitto funktioniert mit dem Publisch/Subscribe Modells. Somiot eigenent sich dieser Broker sehr gut für IoTs (Internet of Things) Nachrichten. Dabei kommt es nicht darauf an, ob es sich um eine einfachen Sensore oder ein Mobiltelefon handelt. 

## 4.3 node-red : <a name="nodered"></a>

# 5 Unsere Lösung: <a name="Lösung"></a>

## 5.1 Netzwerkplan: <a name="Netzwerkplan"></a>
![Netzwerkplan](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/Netzwerkplan.jpg)<br>

# 6 Konfiguration/Installation: <a name="Konfiguration"></a>
## 6.1 IoKit Konfiguration: <a name="IoKit"></a>
## 6.2 Gateway/ MQTT Broker: <a name="Gateway"></a>
### 6.2.1 VPN: <a name="VPN"></a>
Konfiguration des VPN auf dem Raspberry Pi.

- Raspi updaten: <br>
```
sudo apt-get update <br>
```
```
sudo apt-get upgrade <br>
```
- Raspi konfigurieren <br>
```
sudo raspi-config <br>
```
- Hostnamen und Netzwerk anpassen <br>
- PiVPN installieren <br>
```
curl -L https://install.pivpn.io | bash <br>
```
- openssh wählen<br>
![chooseVPN](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/chooseVPN.png)<br>
- Portwählen (wir nehmen Standart)<br>
![port](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/Port.png)<br>
- DNS Server wählen<br>
![dns](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/DNS.png)<br>
- IP Wählen<br>
![ip](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/IP.png)<br>
- Router portforwarding einstellen<br>
![portforwarding](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/Portforwarding.png)<br>
- pivpn -a //neuer Benutzer einrichten<br>
![adduser](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/Usereinrichten.png)<br>
- Zertifikat vom Raspi hollen<br>
```
scp /home/pie/ovpns/testuser2.ovpn username@destination:/file/path (mit Passwort bestätigen)
```

## 6.3 Cloud: <a name="Cloud"></a> 
Als Cloud-Dienst haben wir Node-Red auf der TBZ-Cloud aufgesetzt. Das aufsetzen und einrichten war sehr einfach.

Ich konnte ganz einfach den Docker Befehl für Node-Red auf der VM absetzen:

```docker
    docker run -it -p 1880:1880 -v node_red_data:/data --name mynodered nodered/node-red
```

Danach konnte man auf das Webinterface zugreifen:

http://10.1.31.3:1880/

![Node-Red](https://github.com/Even-Dietrich/Modul-242/blob/master/LB3/img/node-red.png)


## 7 Testprotokolle: <a name="Testprotokolle"></a><br>

# 8 Persönlicher Wissensstand und Reflexion: <a name="Wissensstand"></a><br>
## 8.1 Adam <a name="Adam"></a><br>

## 8.2 Alex <a name="Alex"></a><br>

## 8.3 Even <a name="Even"></a><br>
### Vorwissen:
Wir hatten in einem Modul schon einmal mit IoT-Geräte zu tun. Somit war mir der Begriff schon bekannt und ich konnte mir schon mal ein Bild vom Modul 242 machen. 
Ich hatte aber noch nie etwas mit den IoTKits zu tun und wusste nicht wie diese funktionieren. Somit werde ich mir dieses Wissen in diesem Modul noch aneignet müssen. 
### 06.01.21
Ich habe mich heute vor allem mit dem Mbed Compiler beschäfftigt. Meine Ziel war es das Gerät über mein privates WLAN ins Internet zu bekommen und das der MQTTPbulish soweit funktioniert, damit ich ein File habe welches ich nur noch einspielen muss damit es funktioniert. Ich lernte das Protokoll MQTT kennen und wie man ein IoKit ans Internet bringen kann. 
Was habe ich heute neu benutzt: 
https://ide.mbed.com/compiler
| File | Änderungen |
|--------|------------|
| main.cpp; |  // MQTT Brocker,  char* hostname = "URL des MQTT-Broker";|
| mbed_app.json; |  wifi-ssid : Value anpassen zu SSID vom Privaten WLAN |
| mbed_app.json; |  wifi-password : Value anpassen zu Passwort vom Privaten WLAN |

### 20.01.21
Ich lernte heute mehr über das Protokoll MQQT und was für ein nutzten die Topics dabei haben. Was genaue Mosquitto macht wusste ich vorher auch nicht wurde mir aber heute klar und weiss nun genau was für eine Aufgabe es hat. 
Dazu schrieb ich die Dokumentaion und setzte mich somit mit diesem Thema auseinander. 

## 8.4 Jason <a name="Jason"></a><br>
### Vorwissen:
Bei IoT-Geräten habe ich noch praktisch kein Vorwissen und werde mir alles in den nächsten 3-4 Wochen aneigenen und dokumentieren. 
### 06.01.21
Ich habe mich mit der Materie auseinandergesetzt und einwenig mit dem IoT-Board herum experimentiert. Zusätzlich habe ich mich an der TBZ-Cloud angemeldet und mich mit meiner VM verbunden. Auf der VM konnte ich ganz einfach einen Docker Befehl absetzten und die Cloud-Lösung ist bereits fertig.
### 20.01.21
Heute habe ich mich an die Dokumentation gemacht und zu node-red etwas mehr erfahren. Weiter war ich zur Unterstützung für meine Kollegen da.

