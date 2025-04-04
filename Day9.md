# Przydatne narzędzia i zasoby dla SOC (Security Operations Center)

## Strony do analizy bezpieczeństwa

### 1. **Shodan** ([https://www.shodan.io](https://www.shodan.io))
- Wyszukiwarka urządzeń podłączonych do internetu.
- Pozwala znaleźć serwery, kamery, bazy danych i inne urządzenia.

### 2. **Censys** ([https://censys.io](https://censys.io))
- Alternatywa dla Shodan, oferuje głębszą analizę.
- Indeksuje dane o infrastrukturze sieciowej.

### 3. **VirusTotal** ([https://www.virustotal.com](https://www.virustotal.com))
- Narzędzie do analizy plików i adresów URL pod kątem złośliwego oprogramowania.
- Sprawdza próbki w wielu silnikach antywirusowych.

### 4. **Have I Been Pwned** ([https://haveibeenpwned.com](https://haveibeenpwned.com))
- Pozwala sprawdzić, czy dane konta zostały ujawnione w wyciekach.

---

## Bazy danych podatności

### 1. **CVE – Common Vulnerabilities and Exposures** ([https://cve.mitre.org](https://cve.mitre.org))
- Globalna baza podatności.
- Można szukać według numeru CVE, np. `CVE-2024-1234`.
- Przydatne strony:
  - [https://nvd.nist.gov](https://nvd.nist.gov) (National Vulnerability Database)
  - [https://cve.mitre.org](https://cve.mitre.org)

### 2. **Exploit Database** ([https://www.exploit-db.com](https://www.exploit-db.com))
- Baza exploitów, które mogą wykorzystywać podatności z CVE.
- Szukanie exploitów:
  ```bash
  searchsploit CVE-2024-1234
  ```

### 3. **GitHub** ([https://github.com](https://github.com))
- Można znaleźć przykłady exploitów i narzędzi związanych z bezpieczeństwem.
- Wyszukiwanie podatności:
  ```bash
  site:github.com CVE-2024-1234
  ```

---

## Dokumentacja techniczna

### 1. **Linux Manual Pages** ([https://man7.org/linux/man-pages/](https://man7.org/linux/man-pages/))
- Oficjalna dokumentacja poleceń Linuxa.
- Przykład:
  ```bash
  man ipconfig
  ```

### 2. **Microsoft Windows Documentation** ([https://learn.microsoft.com](https://learn.microsoft.com))
- Dokumentacja Microsoftu, w tym opisy poleceń i API.
- Przykłady:
  - `ipconfig /all` – wyświetla konfigurację sieciową.
  - `netstat -an` – pokazuje aktywne połączenia.

### 3. **Dokumentacje produktów IT**
- Warto szukać oficjalnych dokumentacji produktów, np. Cisco, Palo Alto, Fortinet.

---

## OSINT – Wyszukiwanie informacji o osobach

### 1. **Źródła informacji**
- **Facebook** – znajomi, posty, lokalizacja.
- **X (dawniej Twitter)** – powiązania, komentarze.
- **LinkedIn** – historia zatrudnienia, kontakty.
- **Google Dorking** – wyszukiwanie zaawansowane:
  ```bash
  site:linkedin.com "[Imię Nazwisko]"
  site:facebook.com "[Imię Nazwisko]"
  ```

### 2. **Niebezpieczeństwa OSINT**
- Ujawnianie danych osobowych w mediach społecznościowych.
- Możliwość tworzenia fałszywych profili do zbierania informacji.
- Ryzyko socjotechniki i phishingu.
