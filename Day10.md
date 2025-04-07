# Active Directory – notatki SOC

## Co to jest Active Directory?
Active Directory (AD) to usługa katalogowa od Microsoftu, służąca do zarządzania użytkownikami, komputerami, grupami, zasobami sieciowymi i zasadami w środowiskach domenowych (Domain Services).

---

## Konta z `$` na końcu – co to oznacza?
W AD konta z nazwą kończącą się na `$` to **konta komputerów** (maszyn), a nie użytkowników.

### Jak to działa?
- Kiedy komputer dołącza do domeny, AD tworzy obiekt konta komputera.
- Przykłady nazw kont:
  - `PC-01$`
  - `SRV-FILE$`
- Konto to służy do **uwierzytelniania komputera w domenie** – np. przy logowaniu użytkownika.

### Dlaczego `$`?
Znak `$` oznacza, że konto jest ukryte w GUI – nie widać go w standardowych listach użytkowników.

---

## Organizational Units (OU) – co to jest?
OU to **logiczne jednostki organizacyjne** w AD, które grupują użytkowników, komputery lub inne obiekty, by łatwiej nimi zarządzać.

### Jak dodawać OU:
1. Otwórz `Active Directory Users and Computers`
2. PPM na domenie → **New** → **Organizational Unit**

### Usuwanie OU:
- Domyślnie chronione są przed przypadkowym usunięciem.
- Aby usunąć, przejdź do **Properties → Object → odznacz „Protect from accidental deletion”**

---

## Zmiana hasła użytkownika przez PowerShell
Aby jako administrator zmienić hasło użytkownika:
```powershell
Set-ADAccountPassword [Nazwa użyt.] -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
```
Aby wymusić zmianę hasła przy następnym logowaniu:
```powershell
Set-ADUser -ChangePasswordAtLogon $true -Identity [Nazwa użyt.] -Verbose
```

Wymaga modułu `ActiveDirectory` i odpowiednich uprawnień domenowych.

---

## Delegate Control – co to jest?
Funkcja pozwalająca nadać wybranym użytkownikom **częściowe uprawnienia administracyjne** do określonych OU, np.:
- Resetowanie haseł
- Tworzenie nowych kont
- Modyfikowanie grup użytkowników

### Jak nadać delegację:
1. PPM na OU → **Delegate Control...**
2. Dodaj użytkownika lub grupę
3. Wybierz konkretne uprawnienia (np. resetowanie haseł)

---

## GPO – Group Policy Object
GPO to zestawy zasad konfiguracyjnych, które automatycznie stosują się do użytkowników i komputerów w domenie.

### Tworzenie GPO:
1. `gpmc.msc` → prawym na OU/domenie → **Create a GPO in this domain...**
2. Link GPO do odpowiedniego OU lub całej domeny

### Ważne pojęcia:
- **Scope** – zakres działania GPO
- **Linking** – przypisanie GPO do kontenerów (OU, domena)
- **Inheritance** – dziedziczenie zasad z wyższych poziomów (np. domena → OU)

### Wymuszenie natychmiastowej aktualizacji zasad:
```bash
gpupdate /force
```
