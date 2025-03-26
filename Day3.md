# ISO/OSI & DNS - Notatka

## Model ISO/OSI

Model **ISO/OSI (Open Systems Interconnection)** to teoretyczny model warstwowy, który opisuje sposób komunikacji w sieciach komputerowych. Składa się z **7 warstw**:

1. **Warstwa aplikacji** – interakcja z użytkownikiem (np. HTTP, FTP, SMTP).

**Ataki**: SQL Injection, Phishing.

2. **Warstwa prezentacji** – konwersja i kompresja danych (np. SSL/TLS, kodowanie znaków).

**Ataki**: Ataki na szyfrowanie (np. złamanie TLS 1.0), Zatrucie certyfikatów SSL.

3. **Warstwa sesji** – zarządzanie sesjami połączeń (np. RPC, NetBIOS).

**Ataki**: MITM (Man-in-the-Middle).

4. **Warstwa transportowa** – niezawodna transmisja danych (np. TCP, UDP).

**Ataki**: Port Scanning (np. nmap).

5. **Warstwa sieciowa** – adresowanie i routing (np. IP, ICMP).

**Ataki**: IP Spoofing, DDoS na warstwę sieciową.

6. **Warstwa łącza danych** – przesyłanie danych w sieci lokalnej (np. Ethernet, Wi-Fi).

**Ataki**: MAC Flooding, ARP Spoofing.

7. **Warstwa fizyczna** – transmisja bitów przez medium transmisyjne (np. kable, fale radiowe).

**Ataki**: Jamming attack, Podsłuch kabli.

ISO/OSI jest teoretycznym modelem, natomiast **TCP/IP** to bardziej praktyczny model stosowany w rzeczywistości.

---

## DNS (Domain Name System)

**DNS** to system zamiany nazw domenowych na adresy IP. Zamiast zapamiętywać **IPv4 (np. 192.168.1.1)** czy **IPv6 (np. 2001:db8::ff00:42:8329)**, możemy używać czytelnych nazw domenowych (np. `google.com`).

### **Hierarchia DNS**
DNS działa w modelu **hierarchicznym**, składającym się z kilku poziomów:

1. **Root DNS (.)** – najwyższy poziom, deleguje zapytania do serwerów TLD.
2. **TLD (Top-Level Domain)** – obsługuje domeny najwyższego poziomu (`.com`, `.org`, `.pl`).
3. **Serwery autorytatywne** – przechowują dane dotyczące konkretnej domeny (`example.com`).
4. **Serwery rekursywne** – pośredniczą w wyszukiwaniu adresu IP (np. serwery Google `8.8.8.8`).

### **Rodzaje DNS Records**
- **A** – przypisuje domenę do adresu IPv4.
- **AAAA** – przypisuje domenę do adresu IPv6.
- **CNAME** – alias do innej nazwy domenowej.
- **MX** – wskazuje serwer pocztowy dla domeny.
- **TXT** – przechowuje dodatkowe informacje (np. rekordy SPF, DKIM).

### **Jak działa zapytanie DNS (DNS Request)?**
1. Użytkownik wpisuje `example.com` w przeglądarce.
2. System sprawdza lokalny cache DNS.
3. Jeśli brak wpisu, zapytanie trafia do serwera rekursywnego.
4. Serwer rekursywny pyta serwer root DNS → TLD → autorytatywny serwer domeny.
5. Odpowiedź zwracana jest do użytkownika i cache'owana na przyszłość.

### **Ciekawostka: 8.8.8.8**
Adres `8.8.8.8` to publiczny serwer DNS należący do Google. Jest szybki i niezawodny.

---

## Podsumowanie
- Model **ISO/OSI** opisuje komunikację sieciową w 7 warstwach.
- **DNS** zamienia nazwy domenowe na adresy IP, działając w hierarchicznym modelu.
- Zapytania DNS przechodzą przez serwery rekursywne i autorytatywne.
- Rekordy DNS określają m.in. adresy IP (A, AAAA), aliasy (CNAME) i pocztę (MX).
