# Aufgabe 6 Labor Übung 

## 6.1. Übung 3 – VLANs programmieren und beobachten

Als klassische VLAN Aufgabe wird gerne die Aufteilung eines Netzwerkes für verschiedene Abteilungen verwendet. Jede Abteilung erhält dafür ein eigenes VLAN. Ihre Aufgabe besteht nun darin, dass Netzwerk in GNS3 aufzubauen, zu konfigurieren und Messungen mit Wireshark durchzuführen.
### 6.1.1. Lernziele

Sie sind in der Lage auf MikroTik Routern VLANs zu programmieren. Sie können VLAN Tags mit Wireshark auslesen.
### 6.1.2. Aufgabe

![alt text](grafik.png)


### 6.1.3 Ausführung der Befehle

**Ip Zuteilung**

192.168.20.0/24  
192.168.30.0/24  
192.168.40.0/24  
  
PC1:192.168.20.5  
PC2:192.168.30.5  
PC3:192.168.40.5  
PC4:192.168.20.6  
PC5:192.168.30.6  
PC6:192.168.40.6  

Führe aus auf jeweils angegebenen PC: ip (Adresse)