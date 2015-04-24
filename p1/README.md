Praktikum 1
===========

<a href="https://pub.informatik.haw-hamburg.de/home/pub/prof/kossakowski_klaus-peter/sose2015/it-sicherheit/ITSW_SoSe15_Aufgabe1.pdf" target="_blank">IT Security p1</a>

# Basic stuff #
- netzbasierter Account auf Projektrechner
- Netzwerkdienste auf Port > 1024 
- Benutzername ubuntuXX 
  -> pwd wird mit angegeben
  -> HOME Verzeichnis pro Gruppe (aber alle auf einem Host)
- Host: itsec-support.informatik.haw-hamburg.de
- IP: 141.22.32.96

# Setup
  ## SSH
  Putty, Winscp

  ## Wireshark
  ...

  ## GPG
  ```shell
  # Some code
  gpg
  ```

  ## tcpdump
  ```shell
  # Some code
  tcpdump
  ```

  ## nmap
  ```shell
  # Some code
  nmap
  ```

# Aufgabe 1a: Sicherer Zugriff auf SSH-Server
1. SSH-Zugriff auf HOST:IP via password auth
2. Setup Pubblic SSH-Key
2.1 via SSH-agent?
2.2 pkey auth ohne password
3. reset pwd to a private one

Ziel: Setup für verschiedene SSH auth Strategien

# Aufgabe 1b: Netzwerkdaten mit Wireshark analysieren
Folgende Mitschnitte per Wireshark analysieren
- <a href="http://wiki.wireshark.org/SampleCaptures?action=AttachFile&do=get&target=http.cap" target="_blank">Wireshak Mitschnit 1</a>
- <a href="http://wiki.wireshark.org/SampleCaptures?action=AttachFile&do=get&target=smtp.pcap" target="_blank">Wireshak Mitschnit 2</a>

Ziel: Interessante Fakten ~> Email, Name, Sender, Empfänger etc. herausziehen und kopieren

# Aufgabe 1c: Netzwerkdaten aufzeichnen und Wireshark
nutzen -> Verschlüsselung funktioniert?
1. Auf HOST tcpdump um netzwerkdaten aufzuzeichen in ein traffic.libcap Format, 2mins aktive Session mit mehreren SSH-auths
2. per SSH traffic auf lokalen Server
3. wireshark + traffic

Ziel: identifizieren einer SSH-Verbindung innerhalb der traffic und payload überprüfen (Nutzdaten etc)

# Aufgabe 1d: Dateien verschlüsseln / signieren mit GPG
1. Mit GPG über GUI Public/Private-Key-Paar erzeugen.
2. Dummy name + email
3. verschlüsseln und signieren der libcap aus aufgabe 1b

Ziel:

# Aufgabe 1e:  Sicherheitscheck mit NMAP
nmap auf 
  - tiw.trusted-introducer.org
  - www.trusted-introducer.org
  - www.haw-hamburg.de
  - users.informatik.haw-hamburg.de
  - www.dfn-cert.de 

Ziel: Analysieren und Vergleichen von nmap Daten







