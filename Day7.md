## Windows Update

Aktualizacje systemu zazwyczaj są udostępniane co miesiąc we wtorek drugiego tygodnia miesiąca (tzw. Patch Tuesday). Ich głównym celem jest zwiększenie bezpieczeństwa systemu oraz poprawa jego stabilności.

## Ochrona systemu Windows

Windows oferuje szeroką gamę mechanizmów ochrony, takich jak:
- **Ochrona antywirusowa** – zabezpiecza przed niepożądanym oprogramowaniem, wirusami i innymi zagrożeniami.
- **Firewall i ochrona sieci** – chroni przed atakami typu brute-force, może blokować adresy IP, z których w krótkim czasie wychodzi nadmierna liczba zapytań. Działa na poziomach: Domeny, Sieci Prywatnej (Lokalnej) oraz Publicznej. Użytkownik może również dodawać własne reguły, np. otwierając określone porty dla lokalnego serwera FTP.
- **Kontrola aplikacji (Windows SmartScreen)** – chroni przed phishingiem oraz złośliwym oprogramowaniem, a funkcja *Exploit Protection* zabezpiecza przed atakami wykorzystującymi luki w oprogramowaniu, np. keyloggery.
- **Bezpieczeństwo urządzeń** – moduł TPM (Trusted Platform Module) zapewnia dodatkową ochronę sprzętową przed nieautoryzowanym dostępem.

## BitLocker i jego działanie

BitLocker pozwala na szyfrowanie danych na dysku, co zapobiega ich przechwyceniu. Aby uzyskać dostęp do zaszyfrowanego dysku, wymagany jest klucz startowy (*startup key*), hasło lub PIN.

BitLocker jest zsynchronizowany z TPM, który przechowuje klucze szyfrowania w sposób niedostępny dla użytkownika. Dzięki temu, nawet jeśli ktoś fizycznie przełoży dysk do innego komputera, nie będzie w stanie uzyskać do niego dostępu.

## Shadow Copy (VSS – Volume Shadow Copy Service)

VSS pozwala na tworzenie migawek dysku, czyli kopii zapasowych. W interfejsie graficznym użytkownik może:
- Tworzyć punkty przywracania,
- Odtwarzać poprzednie wersje plików,
- Konfigurować harmonogram przywracania,
- Usuwać istniejące punkty przywracania.

Z punktu widzenia zespołów SOC, VSS może stanowić dodatkową warstwę ochrony przed atakami ransomware, ponieważ umożliwia odzyskanie zaszyfrowanych plików. Warto jednak pamiętać, że niektóre odmiany ransomware potrafią usuwać migawki.

## Uwaga

Powyższe mechanizmy zwiększają bezpieczeństwo systemu, jednak bez aktywnego zaangażowania użytkownika – poprzez regularne aktualizacje, ostrożność w sieci i świadome zarządzanie zabezpieczeniami – istnieje ryzyko włamania i utraty danych.
