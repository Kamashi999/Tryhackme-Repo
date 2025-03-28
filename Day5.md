# HTML i jak wszystko ze sobą współgra?

## HTML i przeglądarka internetowa

Aby wyświetlić stronę internetową na naszym komputerze, przeglądarka wysyła zapytanie HTTP do serwera, który następnie zwraca stronę w postaci kodu HTML, CSS i JavaScript. Przeglądarka renderuje te zasoby i wyświetla stronę użytkownikowi.

Strona internetowa składa się z dwóch głównych komponentów:
1. **Front-End (Client-Side)** – jest to warstwa wizualna, którą widzi użytkownik.
2. **Back-End (Server-Side)** – kod źródłowy obsługujący logikę aplikacji i komunikację z bazą danych, do którego normalny użytkownik nie ma dostępu.

## Struktura HTML

Dokument HTML składa się z kilku kluczowych elementów:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Tytuł strony</title>
    <meta charset="UTF-8">
</head>
<body>
    <h1>Witaj na stronie!</h1>
    <p>To jest akapit tekstu.</p>
</body>
</html>
```
- `<!DOCTYPE html>` – Deklaracja typu dokumentu HTML5.
- `<html>` – Kontener dla całego dokumentu HTML.
- `<head>` – Zawiera metadane strony, np. `title` (tytuł strony) oraz `meta` (kodowanie znaków).
- `<body>` – Główna zawartość strony.
- `<h1>`, `<p>` – Nagłówki i akapity tekstu.

Dodatkowo HTML pozwala na:
- Wklejanie obrazków: `<img src="obrazek.jpg" alt="Opis">`
- Dodawanie klas i identyfikatorów: `<p class="class1" id="paragraf1">`.

## JavaScript (To nie to samo co Java)

JavaScript to język programowania uruchamiany po stronie klienta. Pozwala dodawać interaktywność do stron internetowych, np. dynamicznie zmieniać treść, obsługiwać formularze, komunikować się z serwerem poprzez AJAX.

Dzięki Node.js JavaScript może działać również po stronie serwera.

## Zagrożenia związane z HTML

### Błędy bezpieczeństwa
Kod źródłowy strony można zobaczyć poprzez **Ctrl + U** lub narzędzia deweloperskie (F12). Jeśli strona zawiera wrażliwe informacje w komentarzach HTML, mogą one zostać odczytane przez każdego.

### HTML Injection
Jeżeli aplikacja webowa nie waliduje poprawnie wprowadzanych danych, użytkownicy mogą wstrzykiwać własny kod HTML. Przykład ataku:
```html
<input type="text" name="name" value="<script>alert('Hacked!')</script>">
```
Wprowadzenie takiego kodu może prowadzić do ataków typu **XSS (Cross-Site Scripting)**.

## Jak przebiega żądanie do serwera?

1. Użytkownik wpisuje adres URL (np. `https://example.com`).
2. Przeglądarka sprawdza lokalny cache.
3. Jeśli adres IP nie jest znany, przeglądarka wysyła zapytanie do **serwera DNS**.
4. DNS zwraca adres IP serwera.
5. Przeglądarka łączy się z serwerem poprzez protokół HTTP/HTTPS.
6. Serwer odsyła odpowiedź (kod HTML, CSS, JS, obrazy).
7. Przeglądarka renderuje stronę użytkownikowi.

### CDN (Content Delivery Network)
CDN to sieć serwerów proxy rozproszonych geograficznie, które przechowują kopie statycznych zasobów (obrazy, CSS, JS), aby skrócić czas ładowania strony dla użytkowników z różnych lokalizacji.

## Serwery sieciowe
Serwer WWW przechowuje pliki strony i obsługuje żądania HTTP/HTTPS. Popularne technologie:
- **Apache** – Najczęściej używany serwer WWW.
- **Nginx** – Wysokowydajny serwer obsługujący duży ruch.
- **IIS** – Serwer od Microsoft.
- **Node.js** – Środowisko JavaScript na serwerze, często używane z frameworkiem Express.js.

Dostęp do plików strony na serwerze:
- **Linux**: `/var/www/html/`
- **Windows**: `C:\inetpub\wwwroot`

## Wirtualni hości
Na jednym serwerze może działać wiele stron. Ich rozdzielaniem zajmuje się serwer WWW na podstawie nagłówka `Host` w żądaniu HTTP.

## Skrypty i języki programowania
Po stronie serwera mogą działać różne technologie:
- **PHP** – Do dynamicznych stron i baz danych.
- **Python** – Skrypty i backend.
- **Node.js** – JavaScript na serwerze.
- **Ruby** – Frameworki typu Ruby on Rails.

## Dokładna droga dostępu do strony internetowej

1. Użytkownik wpisuje adres `tryhackme.com`.
2. Przeglądarka sprawdza lokalne cache.
3. Jeśli adres IP nie jest znany, zapytanie DNS wysyłane jest do serwera DNS.
4. Serwer DNS zwraca IP witryny.
5. Przeglądarka wysyła żądanie HTTP/HTTPS do serwera.
6. Żądanie przechodzi przez firewall (**WAF – Web Application Firewall**).
7. CDN wybiera najlepszy serwer do obsługi użytkownika.
8. Połączenie nawiązywane jest na porcie 80 (HTTP) lub 443 (HTTPS).
9. Serwer odbiera żądanie **GET /index.html**.
10. Strona wysyła zapytania do bazy danych.
11. Odpowiedź serwera (HTML, CSS, JS) jest zwracana.
12. Użytkownik widzi stronę w przeglądarce.
