## TryHackMe & Cyberbezpieczeństwo
Dzisiaj zapoznałem się z platformą **TryHackMe**, eksplorując ścieżki kariery w **cyberbezpieczeństwie**.

Nauczyłem się podstawowych ataków, takich jak **Gobuster**, który może skanować strony internetowe, szukać luk w zabezpieczeniach i prowadzić do **backstage’u** lub panelu administratora.

Dowiedziałem się również, jak **analizować logi** oraz wykrywać podejrzaną aktywność na serwerze.


## Program w Pythonie – Połączenie z IP 192.168.0.1 na porcie 21
Dodatkowo stworzyłem prosty program w **Pythonie**, który próbuje nawiązać połączenie z serwerem FTP (**192.168.0.1:21**).

### Kod programu:
```python
import socket  # Importowanie modułu socket

ip = "192.168.0.1"
port = 21

# Tworzenie gniazda TCP
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.settimeout(3)  # Timeout na 3 sekundy

try:
    s.connect((ip, port))  # Próba połączenia
    print(f"Połączenie z {ip}:{port} udane!")
except socket.error:
    print(f"Nie udało się połączyć z {ip}:{port}")
finally:
    s.close()  # Zamknięcie gniazda
```

## Jak działa ten program?
import socket – Załadowanie modułu do obsługi sieci.

socket.socket(socket.AF_INET, socket.SOCK_STREAM) – Tworzy gniazdo (socket) do połączenia IPv4 (AF_INET) oraz TCP (SOCK_STREAM).

s.settimeout(3) – Ustawia limit czasu na 3 sekundy, jeśli serwer nie odpowie.

s.connect((ip, port)) – Próbuje połączyć się z danym adresem IP i portem.

Obsługa błędów (try-except-finally) – Zapobiega crashowi programu, jeśli serwer nie odpowiada.

s.close() – Zamyka połączenie po wykonaniu operacji.

## Gdzie szukać pomocy?
Oficjalna dokumentacja: https://docs.python.org/3/library/socket.html

Wyszukiwarka błędów: https://stackoverflow.com/

TryHackMe: https://tryhackme.com/

Dalszy plan: Rozwijać umiejętności z cyberbezpieczeństwa, uczyć się analizy sieci oraz zaawansowanej konfiguracji serwerów.
