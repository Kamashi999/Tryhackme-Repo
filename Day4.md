# HTTP i HTTPS

## Co to jest HTTP?
HTTP (HyperText Transfer Protocol) to protokół komunikacyjny używany do przesyłania danych w sieci WWW. Umożliwia przesyłanie dokumentów hipertekstowych, takich jak strony internetowe, obrazy czy pliki multimedialne. HTTP jest protokołem bezstanowym, co oznacza, że nie przechowuje informacji o poprzednich interakcjach.

## Co to jest HTTPS i czym się różni od HTTP?
HTTPS (HyperText Transfer Protocol Secure) to rozszerzona wersja HTTP, która wykorzystuje protokół TLS/SSL do szyfrowania przesyłanych danych. Główne różnice to:
- **Bezpieczeństwo**: HTTPS chroni dane przed przechwyceniem i manipulacją.
- **Szyfrowanie**: Dane są zabezpieczone poprzez certyfikaty SSL/TLS.
- **Zaufanie**: Przeglądarki oznaczają strony HTTPS jako bezpieczne.

## Budowa URL
URL (Uniform Resource Locator) to adres zasobu w sieci. Składa się z kilku części:
- **Schemat**: Określa protokół (np. `http://` lub `https://`).
- **Domena**: Adres serwera (np. `example.com`).
- **Port** (opcjonalny): Domyślnie 80 dla HTTP i 443 dla HTTPS.
- **Ścieżka**: Określa konkretny zasób (np. `/strona.html`).
- **Parametry**: Dodatkowe informacje (np. `?id=123`).
- **Fragment**: Kotwica wewnątrz strony (np. `#sekcja`).

## Przykładowy request HTTP
```http
GET / HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Referer: https://google.com
```

### Odpowiedź serwera:
```http
HTTP/1.1 200 OK
Server: Apache
Date: Mon, 27 Mar 2025 12:00:00 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 1024
```

## Metody HTTP
- **GET** – Pobiera zasób z serwera.
- **POST** – Wysyła dane do serwera.
- **PUT** – Aktualizuje cały zasób na serwerze.
- **DELETE** – Usuwa zasób.

## Statusy HTTP
- **Informacyjne (1xx)** – Wstępne informacje (np. 100 Continue).
- **Success (2xx)** – Operacja zakończona sukcesem (np. 200 OK).
- **Redirection (3xx)** – Przekierowania (np. 301 Moved Permanently).
- **Client Error (4xx)** – Błędy po stronie klienta (np. 404 Not Found).
- **Server Error (5xx)** – Błędy serwera (np. 500 Internal Server Error).

## Nagłówki HTTP
- **Host**: Określa domenę docelową.
- **User-Agent**: Identyfikuje przeglądarkę/klienta.
- **Content-Length**: Określa długość treści.
- **Accept-Encoding**: Informuje serwer, jakie formaty kompresji są akceptowane.

## Pliki cookie
Cookies to dane przechowywane przez przeglądarkę i wysyłane do serwera przy każdej wizycie. Przykładowo:
1. Klient wysyła żądanie do serwera.
2. Serwer odpowiada i ustawia cookie `name=Adam`.
3. Przy następnej wizycie klient automatycznie wysyła to cookie, a strona może wyświetlić `Welcome back, Adam!`.
