### Podstawy działania sieci komputerowych

#### Czym jest sieć?
Sieć komputerowa to grupa połączonych ze sobą urządzeń (komputery, serwery, routery, przełączniki itp.), które mogą wymieniać dane. Sieci można podzielić na **lokalne (LAN)** i **rozległe (WAN)**.

- **Sieć lokalna (LAN)** – działa w obrębie np. domu, biura, szkoły.
- **Sieć prywatna** – ma adresy IP niewidoczne bezpośrednio w Internecie (np. 192.168.x.x).

#### Jak urządzenia komunikują się w sieci?
Aby komputery mogły się widzieć i wymieniać dane, potrzebne są urządzenia sieciowe, takie jak:
- **Przełącznik (switch)** – łączy komputery w sieci lokalnej.
- **Router** – łączy sieć lokalną z Internetem i zarządza ruchem.
- **DHCP (Dynamic Host Configuration Protocol)** – serwer DHCP przydziela dynamicznie adresy IP komputerom w sieci.

Jeśli komputery znajdują się w tej samej **podsieci**, mogą się ze sobą bezpośrednio komunikować.

#### Adresy MAC i IP
- **MAC (Media Access Control)** – unikalny adres przypisany do karty sieciowej każdego urządzenia, używany do identyfikacji w sieci lokalnej.
- **IP (Internet Protocol)** – adres logiczny, który pozwala urządzeniom komunikować się w Internecie lub sieci lokalnej.

#### IPv4 vs. IPv6
- **IPv4** – tradycyjny system adresowania (np. 192.168.1.1), ale liczba dostępnych adresów jest ograniczona.
- **IPv6** – nowsza wersja protokołu z ogromną pulą adresów IP, szeroko stosowana w dużych firmach i nowoczesnych sieciach.

#### Jak działa pingowanie?
`ping` to narzędzie używane do sprawdzania, czy dane urządzenie w sieci jest osiągalne i jakie ma opóźnienie. Ping działa w oparciu o **ICMP (Internet Control Message Protocol)**.

- `ping 8.8.8.8` – sprawdza połączenie z serwerem Google DNS.
- Pokazuje czas odpowiedzi (ms) i informuje, czy pakiety nie zostały utracone.

#### Co to jest **8.8.8.8**?
To publiczny serwer DNS Google. Można go używać jako alternatywy dla domyślnych serwerów DNS od dostawcy internetu, ponieważ często jest szybszy i bardziej niezawodny.
