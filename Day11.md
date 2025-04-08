### Uwierzytelnianie w Active Directory

- **Kerberos** - nowsza wersja, działająca na aktualnych systemach.
- **NetNTLM** - starsza wersja, wykorzystywana w starszych systemach.

#### Kerberos:
Kerberos działa na zasadzie pobierania od użytkownika loginu i hasła oraz modelu **TGT (Ticket Granting Ticket)**. TGT umożliwia dostęp do dalszych zasobów w Active Directory. Aby uzyskać dostęp do konkretnego serwisu, używamy **TGS (Ticket Granting Service)**.

Kerberos działa także w kontekście **Golden Ticket**, który pozwala na tworzenie kont administracyjnych na kontrolerach domeny. Jest to cel, który obierają osoby chcące uzyskać uprawnienia administracyjne. Taki ticket może mieć nawet 10 lat!

Aby zapobiec nadużyciom związanym z **Golden Ticket**, warto regularnie monitorować konto **krbtgt** oraz zmieniać hasła (przynajmniej dwukrotnie, aby uwzględnić również klucz awaryjny).

**SPN (Service Principal Name)** to identyfikator służący do wskazania konkretnego serwisu w AD, aby uzyskać **TGS**.

#### NetNTLM:
W starszym modelu **NetNTLM** uwierzytelnianie działało na poziomie NTLM hash + challenge-response. Użytkownik musiał wprowadzić ciąg znaków, a odpowiedź była wykorzystywana do dalszego procesu uwierzytelniania.

---

### Hierarchia w Active Directory

W **Active Directory** możemy odnosić się do struktury **lasu (forest)**, w którym znajdują się **drzewa (domains)**, a w nich **organizacyjne jednostki (OU)**, komputery, użytkownicy itp.

W ramach **lasu** możemy utworzyć wiele drzew, które mogą współpracować ze sobą w ramach zaufania.

---

### Relacja zaufania w Active Directory

Załóżmy, że mamy dwie domeny: **Domena A** i **Domena B**. Jeżeli **Domena A** zaufa **Domenie B**, użytkownicy z **Domeny B** będą mogli wprowadzać zmiany w **Domenie A** (w zależności od poziomu zaufania).

---

### Sieci LAN

W sieciach LAN wyróżniamy kilka podstawowych topologii:

- **Topologia gwiazdy** - Aby przerwać działanie sieci, wystarczy zniszczyć switcha, ponieważ wszystkie urządzenia są połączone centralnie.
- **Topologia pierścienia** - Odcięcie jednego komputera z sieci może zakłócić komunikację w całym pierścieniu.
- **Topologia magistrali** - Zbyt duża liczba zapytań powoduje przeciążenie i może prowadzić do awarii sieci.

**Sieci LAN** są zazwyczaj bezpieczniejsze od publicznych, ponieważ trudniej jest z nich wykraść dane, ale nie jest to niemożliwe.
