# Demo Playbooks

Für die Chemnitzer Linuxtage 2025

## Ziel

Playbooks zur Demonstration der Funktionalität der Verbindungen

Der Vollständigkeit halber, aber vbergleichsweise trivial; Verbindungen zu Linux Hosts per SSH
Vorbereitung der Hosts und Ansible-User auf den Hosts wird vorausgesetzt

## Playbooks

### pb_bench_win.yml

Kleine Playbook zum Vergleich der Laufzeiten von Ansible Tasks

#### Tasks

1. Ensure the benchmark user exists
2. Ensure correct description (Windows) / shell of the benchmark user (Linux)
3. Ensure a temporary file exists
4. Ensure service is running
5. Ensure the benchmark user is removed

### pb_whoami.yml


Playbook zur Verifikation der Funktionmalität von Verbindungsaufbau und Become

#### Rückgabewerte

1. Name des resultierenden Users auf den Zielmaschinen
   - Mit become: true -> User Name nach Privilege Escalation
2. Name des Ansible Ausführenden
   - Bei Start von der Kommandozeile ist das der am Host angemeldete User
   - Unter AAP, AWX & Co ist das der eingeloggte User der den Job gestartet hat

Eine Weiche auf Grundlage von Ansible Facts (ansible_os_family) unterscheidet zw. Linux und Windows

Gibt das Playbook keine Fehler zurück, funktioniert mindestens der Verbindungsaufbau

## Ansible Config

Diese Config enthält ein paar grundlegende Parameter für die Demo
Weiterhin ein paar Best Practices sowie persönliche Defaults
