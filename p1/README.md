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
  - <a href="https://www.gnupg.org/howtos/de/index.html" target="_blank">gpg how to</a>
  - <a href="https://www.gnupg.org/howtos/de/GPGMiniHowto-4.html#ss4.1" target="_blank">encrypt</a>
  - <a href="https://www.gnupg.org/howtos/de/GPGMiniHowto-5.html#GPG-Minihowto-signaturen" target="_blank">signieren</a>
  ```shell
  # encrypt/decrypt
  gpg [--decrypt] [Datei]
  gpg --encrypt Empfänger [Datei]
  # signieren
  gpg -s (oder --sign) [Datei]
  ```

  ## tcpdump
  <a href="https://danielmiessler.com/study/tcpdump/" target="_blank">tcpdump tutorial</a>
  ```shell
  # Options
  -n = no name resolving (raw IPs)
  -X = ascii + hex content
  -S = seqnos are absolute rather than relative
  -s number = amount of bytes to be grepped (0 = snaplength ~ all) default 96 bytes
  -i any = listen on all interfaces
  -q = less protocol information
  -c2 <protocol> = only with this protocol e.g. ICMP or TCP
  -w capture_file = create a dump
  -r capture_file = read in a dump
  ```

  ## nmap
  <a href="http://nmap.org/book/man.html" target="_blank">nmap tutorial</a>
  ```shell
  # Example
  nmap -v scanme.nmap.org                                      
  nmap 
    -s*
    -v # verbose
    -p1-65535 # range of ports
    -O # OS detection                       
                             
  -s*
    sU - Udp,
    sN - TCP, 
    sF - Fin, 
    sO IP, 
    -b (ftp bounce scan)
    sV service version scan

  -6 ip-v6-scan

  -A: Enable OS detection, version detection, script scanning, and traceroute
                                                                 
  Evasion:
        -f Fragmentation of packets
        -D decoys
        -S spoofing
                   
  nmap -sUNO -A -v -p1-65535
  nmap -A -v users.informatik.haw-hamburg.de
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

nur diese, kann zu rechtlichen Schwierigkeiten führen dies Wahllos zu betreiben

Ziel: Analysieren und Vergleichen von nmap Daten







