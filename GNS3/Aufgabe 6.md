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

#### Neue VLAN Bridge erstellen

Führe den folgenden Befehl aus:

```cmd
/interface bridge add name=bridge1 protocol-mode=none vlan-filtering=yes
```	

#### Einen Port (Only Untagged) zu einer Bridge hinzufügen (z.B. für ein Endgerät)
```cmd
/interface bridge port add bridge=bridge1 comment="VLAN 101 – Buchhaltung" frame-types=admit-only-untagged-and-priority-tagged hw=no interface=ether4 pvid=101
```
```cmd
/interface bridge port add bridge=bridge1 comment="VLAN 102 – Entwicklung" frame-types=admit-only-untagged-and-priority-tagged hw=no interface=ether5 pvid=102
```
```cmd
/interface bridge port add bridge=bridge1 comment="VLAN 103 – Verkauf" frame-types=admit-only-untagged-and-priority-tagged hw=no interface=ether6 pvid=103
```

#### Einen Port (Only Tagged) zu einer Bridge hinzufügen

```cmd
/interface bridge port add bridge=bridge1 frame-types=admit-only-vlan-tagged hw=no interface=ether8
```
#### Ein VLAN einer Bridge hinzufügen, sowie «tagged» und «untagged» ports definieren.
```cmd
/interface bridge vlan add bridge=bridge1 comment="VLAN 101" tagged=ether8 untagged=ether4 vlan-ids=101
```	
```cmd
/interface bridge vlan add bridge=bridge1 comment="VLAN 102" tagged=ether8 untagged=ether5 vlan-ids=102
```		
```cmd
/interface bridge vlan add bridge=bridge1 comment="VLAN 103" tagged=ether8 untagged=ether6 vlan-ids=103
```	
#### Hostnamen Setzen auf SW1 und SW2
```cmd 
/system identity set name=SW1
```
```cmd
/system identity set name=SW2
```

#### **Teste ob Pings Funktionieren**

![alt text](image-1.png)
![alt text](image-2.png)

## 6.2. Übung 4 – Praxisnahes VLAN Beispiel mit Router und DHCP Server

In der Praxis erhält jedes VLAN ein eigenes Subnetz (Grundregeln: Ein Subnetz pro VLAN), ein Default Gateway, einen DHCP Server. In dieser Aufgabe erweitern Sie Ihr Netzwerk aus Übung 3 mit diesen Komponenten.

### 6.2.1 Lernziele

Sie können einen DHCP-Server konfigurieren. Sie können einen DNS-Server konfigurieren. Sie können einen Router für mehrere Subnetze konfigurieren.

### 6.2.2 Aufgabe

![](image-3.png)

Meine Subnetze:  
192.168.20.0/24  
192.168.30.0/24  
192.168.40.0/24  

### 6.2.3 Konfiguration

Auf R1 füge 3 VLAN Interfaces hinzu
```cmd
/interface vlan add interface=ether2 vlan-id=101 name=ether2_vlan101
```	
```cmd
/interface vlan add interface=ether2 vlan-id=102 name=ether2_vlan102
```	
```cmd
/interface vlan add interface=ether2 vlan-id=203 name=ether2_vlan103
```	

Verteile Host adressen auf die VLANs
```cmd
/ip address add address=192.168.20.1/24 interface=ether2_vlan101
```	
```cmd
/ip address add address=192.168.30.1/24 interface=ether2_vlan102
```	
```cmd
/ip address add address=192.168.40.1/24 interface=ether2_vlan103
```		

Gehe auf SW1 und füge ether2 als Tagged Port für die drei VLANs hinzu

```cmd
/interface bridge vlan set numbers=0 tagged=ether8,ether2 untagged=ether4
/interface bridge vlan set numbers=1 tagged=ether8,ether2 untagged=ether5
/interface bridge vlan set numbers=2 tagged=ether8,ether2 untagged=ether6


/interface bridge port add bridge=bridge1 interface=ether2
/interface bridge vlan add bridge=bridge1 tagged=ether2 vlan-ids=101,102,103
```