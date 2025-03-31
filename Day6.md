# Wprowadzenie do Windowsa

## Zapisywanie plików
System Windows obsługuje różne systemy plików, w tym:
- **FAT16** – starszy system plików, obsługuje pliki do 2 GB.
- **FAT32** – ulepszona wersja FAT16, obsługuje pliki do 4 GB.
- **NTFS** – aktualnie najczęściej używany system plików, obsługuje duże pliki, szyfrowanie, uprawnienia dostępu oraz funkcję **Alternate Data Streams (ADS)** – dodatkowe metadane ukryte w plikach.

Klikając prawym przyciskiem myszy na folder/pliki i wybierając **Właściwości**, możemy przypisać różne prawa dostępu do plików w zależności od użytkownika.

---

## Folder Windows/System32
Folder **C:\Windows\System32** zawiera kluczowe pliki systemowe Windows. Warto również znać zmienną systemową `%windir%`, która wskazuje na główny katalog systemu Windows (zwykle `C:\Windows`).

---

## Dodawanie użytkowników
Istnieją różne sposoby dodania użytkownika w Windows:
1. **Przez GUI**:
   - Otwórz **Użytkownicy** w wyszukiwarce Windows → Dodaj nowego użytkownika.
2. **Przez `lusrmgr.msc`**:
   - Otwórz `Run` (`Win + R`) → wpisz `lusrmgr.msc` → Zarządzaj lokalnymi użytkownikami
   - **Przez CMD**:
   - Aby dodać użytkownika do grupy administratorów:
     ```cmd
     net localgroup Administratorzy [nazwa_użytkownika] /add
     ```

---

## Panel sterowania
**Panel sterowania** to miejsce, gdzie możemy zarządzać systemem, siecią, kontami użytkowników oraz zabezpieczeniami, takimi jak firewall.

---

## Menedżer zadań
Menedżer zadań (`Ctrl + Shift + Esc`) pozwala:
- Sprawdzać specyfikację komputera.
- Zarządzać działającymi procesami.
- Monitorować wydajność systemu i zamykać niechciane aplikacje.

---

## Konfiguracja systemu (`msconfig`)
Pozwala na:
- Zarządzanie sposobem uruchamiania systemu.
- Włączanie i wyłączanie usług systemowych.
- Dostęp do narzędzi diagnostycznych.

---

## Zarządzanie komputerem (`compmgmt.msc`)
### 🔹 Harmonogram zadań (`taskschd.msc`)
Pozwala na automatyczne wykonywanie zadań w określonych godzinach lub warunkach.

### 🔹 Podgląd zdarzeń (`eventvwr.msc`)
Rejestruje logi systemowe i pomaga diagnozować błędy.

### 🔹 Foldery udostępnione
Wyświetla wszystkie foldery udostępnione w sieci.

### 🔹 Użytkownicy i grupy lokalne (`lusrmgr.msc`)
Zarządzanie użytkownikami oraz ich uprawnieniami.

### 🔹 Wydajność (`perfmon`)
Monitorowanie wydajności systemu oraz analizy wykorzystania zasobów.

### 🔹 Menedżer urządzeń (`devmgmt.msc`)
Pozwala na kontrolę sprzętu, instalację i odinstalowanie sterowników.

### 🔹 Zarządzanie dyskami (`diskmgmt.msc`)
Pozwala na:
- Tworzenie i usuwanie partycji.
- Formatuje i zarządza przestrzenią dyskową.

### 🔹 Usługi (`services.msc`)
Zarządzanie usługami systemowymi (włączanie, wyłączanie, automatyczne uruchamianie).

---

## Informacje o systemie (`msinfo32`)
`msinfo32` dostarcza szczegółowych informacji o systemie, w tym:
- **Sprzęt** – procesor, RAM, płyta główna.
- **Komponenty** – karta graficzna, dyski, urządzenia wejściowe.
- **Oprogramowanie** – wersja systemu, zmienne środowiskowe (`Environment Variables`).

---

## Monitor zasobów (`resmon`)
Pozwala sprawdzić:
- Obciążenie procesora, pamięci RAM, dysku i sieci.
- Wyszukać procesy powodujące spowolnienia systemu.

---

## Edytor Rejestru (`regedit`)
Rejestr systemu Windows to baza danych przechowująca ustawienia systemowe i aplikacji.
- **HKEY_LOCAL_MACHINE (HKLM)** – ustawienia globalne dla systemu.
- **HKEY_CURRENT_USER (HKCU)** – ustawienia dla aktualnego użytkownika.
- **HKEY_CLASSES_ROOT (HKCR)** – informacje o skojarzeniach plików.
- **HKEY_USERS (HKU)** – profile użytkowników.
- **HKEY_CURRENT_CONFIG (HKCC)** – informacje o bieżącej konfiguracji sprzętowej.
