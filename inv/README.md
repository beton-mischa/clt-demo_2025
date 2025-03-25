# Demo Inventory

Für die Chemnitzer Linuxtage 2025

## Ziel

Konfiguration der Connection-Parameter im Rahmen der Demo.

Verbindungen zu Windows Hosts

1. WinRM
2. PSRP
3. SSH

Der Vollständigkeit halber, aber vbergleichsweise trivial; Verbindungen zu Linux Hosts per SSH

Vorbereitung der Hosts und Ansible-User auf den Hosts wird vorausgesetzt

## Vorbereitete Connections

### demo-01.local

- Nur WinRM mit NTLM
- Keine Zertifikatsvalidierung
- Rudimentärer Verbindungsaufbau mit Username & Passwort

### demo-02.local

1. None
   - Nur PSRP mit NTLM über https
   - Keine Zertifikatsvalidierung
   - Rudimentärer Verbindungsaufbau mit Username & Passwort
2. None
   - PSRP mit NTLM über https
   - Mit Zertifikatsvalidierung
   - Rudimentärer Verbindungsaufbau mit Username & Passwort
3. Cert Authentication + PE
   - PSRP mit Zertifikats-Authentication
   - Keine Zertifikatsvalidierung
   - Verbindungsaufbau per Zertifikat
   - Zur Demonstration Credentials für anderen User die ignoriert werden
   - Mit Privilege Escalation
4. Cert Validation & Authentication (nicht funktional)
   - PSRP mit Zertifikats-Authentication
   - Mit Zertifikatsvalidierung
   - Ohne Privilege Escalation

### demo-03.local

- SSH zu OpenSSH Server auf Windows
- Credentials sind vorbereitet, bevorzugt wird SSH PubKey

### demo-04.local

- SSH zu OpenSSH Server auf Linux
- Globale Credentials, bevorzugt wird SSH PubKey

## Weitere Variablen

Alle anderen Variablen sind vorbereitet für Tests und Demonstration und größtenteils auskommentiert
Die Basis-Credentials in users_credentials.yml müssen neu erstellt werden
