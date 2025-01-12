# Dokumentacja Projektowa Systemu Rezerwacji Hotelowej

## Wprowadzenie

Niniejszy dokument opisuje projekt systemu rezerwacji hotelowej. System ma na celu umożliwienie klientom rezerwacji pokoi, a personelowi zarządzanie pokojami i obsługę gości.

## Diagram Przypadków Użycia (Use Case Diagram)

*   **Aktorzy:**
    *   Klient
    *   Pracownik hotelu
*   **Przypadki użycia:**
    *   **Klient:**
        *   **Przeglądanie dostępnych pokoi:**
            *   **Warunki wstępne:** Klient jest na stronie głównej systemu.
            *   **Główne kroki:**
                1.  System wyświetla listę dostępnych pokoi.
                2.  Klient może przeglądać szczegóły każdego pokoju (zdjęcia, opis, cena).
                3.  Klient może filtrować pokoje według różnych kryteriów (np. typ pokoju, cena).
            *   **Warunki końcowe:** Klient przegląda listę dostępnych pokoi.
            *   **Wyjątki:** Brak dostępnych pokoi, błąd połączenia z bazą danych.
        *   **Rezerwacja pokoju:**
            *   **Warunki wstępne:** Klient jest zalogowany i przegląda listę dostępnych pokoi.
            *   **Główne kroki:**
                1.  Klient wybiera pokój i daty pobytu.
                2.  System sprawdza dostępność pokoju w wybranych terminach.
                3.  System prosi o potwierdzenie rezerwacji.
                4.  Klient potwierdza rezerwację.
                5.  System zapisuje rezerwację w bazie danych.
                6.  System wyświetla potwierdzenie rezerwacji.
            *   **Warunki końcowe:** Rezerwacja została zapisana w systemie.
            *   **Wyjątki:** Pokój niedostępny, błąd płatności, błąd zapisu do bazy danych.
        *   **Anulowanie rezerwacji:**
            *   **Warunki wstępne:** Klient jest zalogowany i ma aktywne rezerwacje.
            *   **Główne kroki:**
                1.  Klient wybiera rezerwację do anulowania.
                2.  System prosi o potwierdzenie anulowania.
                3.  Klient potwierdza anulowanie.
                4.  System anuluje rezerwację w bazie danych.
                5.  System wyświetla potwierdzenie anulowania.
            *   **Warunki końcowe:** Rezerwacja została anulowana.
            *   **Wyjątki:** Brak rezerwacji do anulowania, błąd zapisu do bazy danych.
        *   **Logowanie do systemu:**
            *   **Warunki wstępne:** Klient jest na stronie logowania.
            *   **Główne kroki:**
                1.  Klient podaje login i hasło.
                2.  System weryfikuje dane logowania.
                3.  System loguje klienta do systemu.
            *   **Warunki końcowe:** Klient jest zalogowany do systemu.
            *   **Wyjątki:** Nieprawidłowy login lub hasło, błąd połączenia z bazą danych.
        *   **Rejestracja w systemie:**
            *   **Warunki wstępne:** Klient jest na stronie rejestracji.
            *   **Główne kroki:**
                1.  Klient podaje dane rejestracyjne (imię, nazwisko, email, hasło).
                2.  System weryfikuje, czy email nie jest już zarejestrowany.
                3.  System zapisuje dane klienta w bazie danych.
                4.  System wyświetla potwierdzenie rejestracji.
            *   **Warunki końcowe:** Klient jest zarejestrowany w systemie.
            *   **Wyjątki:** Email już zarejestrowany, błąd zapisu do bazy danych.
    *   **Pracownik hotelu:**
        *   **Zarządzanie pokojami (dodawanie, edycja, usuwanie):**
             *   **Warunki wstępne:** Pracownik jest zalogowany do systemu.
             *   **Główne kroki:**
                1.  Pracownik wybiera opcję zarządzania pokojami.
                2.  System wyświetla opcje: dodawanie, edycja, usuwanie.
                3.  Pracownik wybiera jedną z opcji.
                4.  W zależności od wybranej opcji, system prosi o odpowiednie dane (np. numer pokoju, typ, opis, cena).
                5.  System zapisuje zmiany w bazie danych.
                6.  System wyświetla potwierdzenie operacji.
             *   **Warunki końcowe:** Pokój został dodany, edytowany lub usunięty.
             *   **Wyjątki:** Błąd zapisu do bazy danych, nieprawidłowe dane.
        *   **Potwierdzanie rezerwacji:**
            *   **Warunki wstępne:** Pracownik jest zalogowany do systemu i ma dostęp do listy rezerwacji.
            *   **Główne kroki:**
                1.  Pracownik przegląda listę rezerwacji.
                2.  Pracownik wybiera rezerwację do potwierdzenia.
                3.  System prosi o potwierdzenie.
                4.  Pracownik potwierdza rezerwację.
                5.  System zmienia status rezerwacji na "potwierdzona".
                6.  System wyświetla potwierdzenie.
            *   **Warunki końcowe:** Rezerwacja została potwierdzona.
            *   **Wyjątki:** Brak rezerwacji do potwierdzenia, błąd zapisu do bazy danych.
        *   **Obsługa gości (zameldowanie, wymeldowanie):**
            *   **Warunki wstępne:** Pracownik jest zalogowany do systemu.
            *   **Główne kroki:**
                1.  Pracownik wybiera opcję obsługi gości.
                2.  System wyświetla opcje: zameldowanie, wymeldowanie.
                3.  Pracownik wybiera jedną z opcji.
                4.  W zależności od wybranej opcji, system prosi o odpowiednie dane (np. imię, nazwisko, numer rezerwacji, numer pokoju).
                5.  System rejestruje zameldowanie lub wymeldowanie gościa.
                6.  System wyświetla potwierdzenie operacji.
            *   **Warunki końcowe:** Gość został zameldowany lub wymeldowany.
            *   **Wyjątki:** Brak rezerwacji, błąd zapisu do bazy danych.
        *   **Przeglądanie rezerwacji:**
            *   **Warunki wstępne:** Pracownik jest zalogowany do systemu.
            *   **Główne kroki:**
                1.  Pracownik wybiera opcję przeglądania rezerwacji.
                2.  System wyświetla listę rezerwacji.
                3.  Pracownik może przeglądać szczegóły każdej rezerwacji.
            *   **Warunki końcowe:** Pracownik przegląda listę rezerwacji.
            *   **Wyjątki:** Brak rezerwacji, błąd połączenia z bazą danych.
        *   **Logowanie do systemu:**
            *   **Warunki wstępne:** Pracownik jest na stronie logowania.
            *   **Główne kroki:**
                1.  Pracownik podaje login i hasło.
                2.  System weryfikuje dane logowania.
                3.  System loguje pracownika do systemu.
            *   **Warunki końcowe:** Pracownik jest zalogowany do systemu.
            *   **Wyjątki:** Nieprawidłowy login lub hasło, błąd połączenia z bazą danych.

## Diagramy Aktywności (Activity Diagrams)

### Rezerwacja Pokoju

Opis diagramu aktywności dla rezerwacji pokoju:

1.  **Start:** Proces rozpoczyna się, gdy klient chce zarezerwować pokój.
2.  **Wyświetl dostępne pokoje:** System prezentuje klientowi listę dostępnych pokoi wraz z ich opisami i cenami.
3.  **Wybór pokoju:** Klient wybiera konkretny pokój.
4.  **Podanie danych:** Klient podaje swoje dane osobowe oraz daty pobytu.
5.  **Sprawdzenie dostępności:** System sprawdza, czy wybrany pokój jest dostępny w podanych terminach.
6.  **Dostępny?**
    *   **Tak:** Przejdź do punktu 7.
    *   **Nie:** System informuje klienta o braku dostępności i wraca do punktu 2 (wyświetlenie dostępnych pokoi).
7.  **Potwierdzenie rezerwacji:** System wyświetla podsumowanie rezerwacji.
8.  **Akceptacja rezerwacji:** Klient akceptuje rezerwację.
9.  **Zapisanie rezerwacji:** System zapisuje rezerwację w bazie danych.
10. **Wyświetlenie potwierdzenia:** System wyświetla potwierdzenie rezerwacji wraz z numerem rezerwacji.
11. **Koniec:** Proces rezerwacji zakończony.

### Zarządzanie Pokojami

Opis diagramu aktywności dla zarządzania pokojami:

1.  **Start:** Proces rozpoczyna się, gdy pracownik hotelu chce zarządzać pokojami.
2.  **Wyświetl menu zarządzania pokojami:** System prezentuje pracownikowi opcje zarządzania pokojami (dodawanie, edycja, usuwanie).
3.  **Wybór opcji:** Pracownik wybiera jedną z opcji: dodawanie, edycja lub usuwanie pokoju.
4.  **Dodawanie pokoju:**
    *   System prosi o podanie danych nowego pokoju (numer, typ, opis, cena).
    *   System zapisuje nowy pokój w bazie danych.
    *   Przejdź do punktu 8.
5.  **Edycja pokoju:**
    *   System prosi o podanie numeru pokoju do edycji.
    *   System wyświetla dane wybranego pokoju.
    *   System prosi o wprowadzenie zmian.
    *   System zapisuje zmiany w bazie danych.
    *   Przejdź do punktu 8.
6.  **Usuwanie pokoju:**
    *   System prosi o podanie numeru pokoju do usunięcia.
    *   System usuwa pokój z bazy danych.
    *   Przejdź do punktu 8.
7.  **Potwierdzenie:** System wyświetla potwierdzenie wykonania operacji.
8.  **Koniec:** Proces zarządzania pokojami zakończony.

### Logowanie do Systemu

Opis diagramu aktywności dla procesu logowania:

1.  **Start:** Proces rozpoczyna się, gdy użytkownik (klient lub pracownik hotelu) chce zalogować się do systemu.
2.  **Wybór roli:** Użytkownik wybiera swoją rolę (klient lub pracownik hotelu).
3.  **Podanie danych logowania:** System prosi o podanie danych logowania (login i hasło).
4.  **Weryfikacja danych:** System weryfikuje dane logowania w bazie danych.
5.  **Poprawne dane?**
    *   **Tak:** System loguje użytkownika i przechodzi do odpowiedniego interfejsu (klienta lub pracownika). Przejdź do punktu 7.
    *   **Nie:** System wyświetla komunikat o błędzie i wraca do punktu 3 (podanie danych logowania).
6.  **Dostęp do systemu:** Użytkownik ma dostęp do odpowiednich funkcji systemu.
7.  **Koniec:** Proces logowania zakończony.

### Rejestracja Użytkownika

Opis diagramu aktywności dla procesu rejestracji:

1.  **Start:** Proces rozpoczyna się, gdy użytkownik (klient) chce zarejestrować się w systemie.
2.  **Wybór rejestracji:** Użytkownik wybiera opcję rejestracji.
3.  **Podanie danych rejestracyjnych:** System prosi o podanie danych rejestracyjnych (imię, nazwisko, email, hasło).
4.  **Weryfikacja danych:** System weryfikuje, czy podany email nie jest już zarejestrowany.
5.  **Email zajęty?**
    *   **Tak:** System wyświetla komunikat o błędzie i wraca do punktu 3 (podanie danych rejestracyjnych).
    *   **Nie:** Przejdź do punktu 6.
6.  **Zapisanie danych:** System zapisuje dane użytkownika w bazie danych.
7.  **Potwierdzenie rejestracji:** System wyświetla potwierdzenie rejestracji.
8.  **Koniec:** Proces rejestracji zakończony.

### Anulowanie Rezerwacji

Opis diagramu aktywności dla procesu anulowania rezerwacji:

1.  **Start:** Proces rozpoczyna się, gdy klient chce anulować rezerwację.
2.  **Logowanie:** Klient loguje się do systemu.
3.  **Wyświetlenie rezerwacji:** System wyświetla listę rezerwacji klienta.
4.  **Wybór rezerwacji:** Klient wybiera rezerwację do anulowania.
5.  **Potwierdzenie anulowania:** System prosi o potwierdzenie anulowania rezerwacji.
6.  **Anulowanie?**
    *   **Tak:** System anuluje rezerwację i przechodzi do punktu 7.
    *   **Nie:** System wraca do punktu 3 (wyświetlenie rezerwacji).
7.  **Potwierdzenie anulowania:** System wyświetla potwierdzenie anulowania rezerwacji.
8.  **Koniec:** Proces anulowania rezerwacji zakończony.

### Zmiana Rezerwacji

Opis diagramu aktywności dla procesu zmiany rezerwacji:

1.  **Start:** Proces rozpoczyna się, gdy klient chce zmienić rezerwację.
2.  **Logowanie:** Klient loguje się do systemu.
3.  **Wyświetlenie rezerwacji:** System wyświetla listę rezerwacji klienta.
4.  **Wybór rezerwacji:** Klient wybiera rezerwację do zmiany.
5.  **Wybór nowych danych:** Klient wybiera nowe daty lub pokój.
6.  **Sprawdzenie dostępności:** System sprawdza, czy wybrany pokój jest dostępny w nowych terminach.
7.  **Dostępny?**
    *   **Tak:** Przejdź do punktu 8.
    *   **Nie:** System informuje klienta o braku dostępności i wraca do punktu 5 (wybór nowych danych).
8.  **Potwierdzenie zmiany:** System wyświetla podsumowanie zmiany rezerwacji.
9.  **Akceptacja zmiany:** Klient akceptuje zmianę rezerwacji.
10. **Zapisanie zmiany:** System zapisuje zmianę rezerwacji w bazie danych.
11. **Wyświetlenie potwierdzenia:** System wyświetla potwierdzenie zmiany rezerwacji.
12. **Koniec:** Proces zmiany rezerwacji zakończony.

### Obsługa Gościa

Opis diagramu aktywności dla obsługi gościa (zameldowanie i wymeldowanie):

1.  **Start:** Proces rozpoczyna się, gdy gość przybywa do hotelu (zameldowanie) lub chce opuścić hotel (wymeldowanie).
2.  **Wybór operacji:** Pracownik hotelu wybiera, czy gość się melduje, czy wymeldowuje.
3.  **Zameldowanie:**
    *   System prosi o podanie danych gościa (imię, nazwisko, numer rezerwacji).
    *   System sprawdza rezerwację.
    *   System przydziela pokój (jeśli nie był wcześniej przydzielony).
    *   System rejestruje zameldowanie gościa.
    *   Przejdź do punktu 6.
4.  **Wymeldowanie:**
    *   System prosi o podanie danych gościa (imię, nazwisko, numer pokoju).
    *   System sprawdza dane gościa.
    *   System rejestruje wymeldowanie gościa.
    *   Przejdź do punktu 6.
5.  **Potwierdzenie:** System wyświetla potwierdzenie wykonania operacji (zameldowania lub wymeldowania).
6.  **Koniec:** Proces obsługi gościa zakończony.

## Diagramy

### Diagram Przypadków Użycia

Diagram przypadków użycia przedstawia interakcje między aktorami (klient, pracownik hotelu) a systemem. Aktorzy wykonują różne przypadki użycia, takie jak rezerwacja pokoju, zarządzanie pokojami, logowanie do systemu, itp.

<img src="diagrams/use_case_diagram.svg" alt="Diagram przypadków użycia" width="458" height="739">

### Diagramy Aktywności

Diagramy aktywności opisują przepływ pracy w systemie dla różnych przypadków użycia. Każdy diagram przedstawia sekwencję kroków, które są wykonywane w ramach danego przypadku użycia. Przykłady diagramów aktywności to rezerwacja pokoju, zarządzanie pokojami, logowanie do systemu, itp.

### Diagramy Sekwencji

Diagramy sekwencji przedstawiają interakcje między obiektami w systemie w czasie. Pomagają zrozumieć, jak różne komponenty systemu współpracują ze sobą, aby zrealizować dany przypadek użycia.

[Diagram sekwencji logowania](examples/Diagram-sekwencji-Logowanie.svg)

<img src="examples/Diagram-sekwencji-Logowanie.svg" alt="Diagram sekwencji logowania" width="300" height="400">

[Diagram aktywności rezerwacji pokoju](diagrams/activity_diagram_rezerwacja.svg)

<img src="diagrams/activity_diagram_rezerwacja.svg" alt="Diagram aktywności rezerwacji pokoju" width="200" height="300">


[Diagram aktywności zarządzania pokojami](diagrams/activity_diagram_zarzadzanie_pokojami.svg)

<img src="diagrams/activity_diagram_zarzadzanie_pokojami.svg" alt="Diagram aktywności zarządzania pokojami" width="200" height="300">


[Diagram aktywności logowania](diagrams/activity_diagram_logowanie.svg)

<img src="diagrams/activity_diagram_logowanie.svg" alt="Diagram aktywności logowania" width="200" height="300">


[Diagram aktywności rezerwacji pokoju](diagrams/activity_diagram_rezerwacja.svg)

<img src="diagrams/activity_diagram_rezerwacja.svg" alt="Diagram aktywności rezerwacji pokoju" width="200" height="300">


[Diagram aktywności zarządzania pokojami](diagrams/activity_diagram_zarzadzanie_pokojami.svg)

<img src="diagrams/activity_diagram_zarzadzanie_pokojami.svg" alt="Diagram aktywności zarządzania pokojami" width="200" height="300">


[Diagram aktywności logowania](diagrams/activity_diagram_logowanie.svg)

<img src="diagrams/activity_diagram_logowanie.svg" alt="Diagram aktywności logowania" width="200" height="300">


[Diagram aktywności zmiany rezerwacji](diagrams/activity_diagram_zmiana_rezerwacji.png)

<img src="diagrams/activity_diagram_zmiana_rezerwacji.svg" alt="Diagram aktywności zmiany rezerwacji" width="200" height="300">


### Diagramy Klas

Diagramy klas przedstawiają strukturę danych systemu, w tym klasy, ich atrybuty i relacje między nimi. Diagramy klas opisują modele danych, takie jak Użytkownik, Pracownik, Gość, Pokój, Rezerwacja.

[Diagram klas]
<img src="diagrams/class_diagram.svg" alt="Diagram klas" width="458" height="398">
<img src="diagrams/class_diagram_uzytkownik.svg" alt="Diagram klas użytkownika" width="200" height="200">
<img src="diagrams/class_diagram_pracownik.svg" alt="Diagram klas pracownika" width="200" height="200">

## Opis Modeli Danych

### Model Użytkownik

*   `id_uzytkownika`: INTEGER (Primary Key, Autoincrement)
*   `login`: TEXT (Unique, Not Null, Max Length: 50)
*   `haslo`: TEXT (Not Null, Min Length: 8)
*   `email`: TEXT (Unique, Not Null, Format: email)
*   `rola`: TEXT (Not Null, Default: 'klient', Enum: 'klient', 'pracownik')

### Model Pracownik

*   `id_pracownika`: INTEGER (Primary Key, Autoincrement)
*   `imie`: TEXT (Not Null, Max Length: 50)
*   `nazwisko`: TEXT (Not Null, Max Length: 50)
*   `email`: TEXT (Unique, Not Null, Format: email)
*   `telefon`: TEXT (Max Length: 20)
*   `login`: TEXT (Unique, Not Null, Max Length: 50)
*   `haslo`: TEXT (Not Null, Min Length: 8)
*   `rola`: TEXT (Not Null, Default: 'recepcjonista', Enum: 'recepcjonista', 'menadżer')
    *   **Relacje:**
        *   Pracownik ma relację *jeden-do-jednego* z tabelą `Użytkownicy` (jeden pracownik ma jedno konto użytkownika).

### Model Gość

*   `id_klienta`: INTEGER (Primary Key, Autoincrement)
*   `imie`: TEXT (Not Null, Max Length: 50)
*   `nazwisko`: TEXT (Not Null, Max Length: 50)
*   `email`: TEXT (Unique, Not Null, Format: email)
*   `telefon`: TEXT (Max Length: 20)
    *   **Relacje:**
        *   Gość ma relację *jeden-do-wielu* z tabelą `Rezerwacje` (jeden gość może mieć wiele rezerwacji).

### Model Pokój

*   `id_pokoju`: INTEGER (Primary Key, Autoincrement)
*   `numer_pokoju`: TEXT (Unique, Not Null, Max Length: 10)
*   `typ_pokoju`: TEXT (Not Null, Enum: 'jednoosobowy', 'dwuosobowy', 'apartament')
*   `opis`: TEXT (Max Length: 200)
*   `dostepny`: BOOLEAN (Not Null, Default: True)
*   `data_utworzenia`: DATETIME (Not Null, Default: current_timestamp)
*   `data_modyfikacji`: DATETIME (Not Null, Default: current_timestamp)
    *   **Relacje:**
        *   Pokój ma relację *jeden-do-wielu* z klasą `HistoriaZmianPokoju` (jeden pokój może mieć wiele wpisów w historii zmian).
        *   Pokój ma relację *jeden-do-wielu* z klasą `Cennik` (jeden pokój może mieć wiele wpisów w cenniku).

### Model HistoriaZmianPokoju

*   `id_zmiany`: INTEGER (Primary Key, Autoincrement)
*   `pokoj_id`: INTEGER (Foreign Key referencing Pokój, Not Null)
*   `data_zmiany`: DATETIME (Not Null, Default: current_timestamp)
*   `typ_zmiany`: TEXT (Not Null, Enum: 'dane', 'status')
*   `stara_wartosc`: TEXT (Max Length: 200)
*   `nowa_wartosc`: TEXT (Max Length: 200)
*   `uzytkownik`: TEXT (Not Null, Max Length: 50) (kto dokonał zmiany)

### Model Dostawca

*   `id_dostawcy`: INTEGER (Primary Key, Autoincrement)
*   `nazwa`: TEXT (Unique, Not Null, Max Length: 50) (np. "Booking.com", "Airbnb", "Expedia")
*   `umowa_od`: DATETIME (Not Null) (data rozpoczęcia współpracy)
*   `umowa_do`: DATETIME (data zakończenia współpracy)
*   `provision`: REAL (Not Null, Min: 0, Max: 1) (procent prowizji)
    *   **Relacje:**
        *   Dostawca ma relację *jeden-do-wielu* z klasą `Cennik` (jeden dostawca może mieć wiele wpisów w cenniku).

### Model Cennik

*   `id_cennika`: INTEGER (Primary Key, Autoincrement)
*   `pokoj_id`: INTEGER (Foreign Key referencing Pokój, Not Null)
*   `typ_cennika_id`: INTEGER (Foreign Key referencing TypCennika, Not Null)
*   `dostawca_id`: INTEGER (Foreign Key referencing Dostawca, Not Null)
*   `cena_bazowa`: REAL (Not Null, Min: 0) (cena bazowa hotelu)
*   `cena_ostateczna`: REAL (Not Null, Min: 0) (cena po uwzględnieniu prowizji)
*   `data_obowiazywania_od`: DATETIME (Not Null)
*   `data_obowiazywania_do`: DATETIME
*   `ostatnia_synchronizacja`: DATETIME (data ostatniej synchronizacji z API dostawcy)
    *   **Relacje:**
        *   Cennik ma relację *wiele-do-jednego* z klasą `Dostawca` (wiele cenników może być powiązanych z jednym dostawcą).

### Mechanizm Synchronizacji Cen

System posiada mechanizm automatycznej synchronizacji cen z zewnętrznymi dostawcami (np. Booking.com, Airbnb). Synchronizacja odbywa się poprzez dedykowane API dostawców i obejmuje następujące kroki:

1.  **Pobranie tokenu autoryzacyjnego:**
    *   System loguje się do API dostawcy używając poświadczeń (login i hasło).
    *   System wysyła żądanie POST do endpointu `/auth/token` z danymi logowania w formacie JSON.
    *   Przykładowe zapytanie:
        ```json
        {
            "login": "user",
            "haslo": "password"
        }
        ```
    *   System otrzymuje token dostępowy ważny przez określony czas w formacie JSON.
    *   Przykładowa odpowiedź:
        ```json
        {
            "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
        }
        ```
    *   W przypadku błędu logowania, system otrzymuje kod błędu 401 i komunikat o błędzie.
        ```json
        {
            "error": "Nieprawidłowe dane logowania"
        }
        ```

2.  **Pobranie aktualnych cen:**
    *   System wysyła żądanie GET do endpointu `/rooms/prices` z tokenem autoryzacyjnym w nagłówku `Authorization`.
    *   Przykładowe zapytanie:
        ```
        GET /rooms/prices
        Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
        ```
    *   System otrzymuje aktualne ceny dla każdego pokoju w formacie JSON.
    *   Przykładowa odpowiedź:
        ```json
        [
            {
                "id_pokoju": 1,
                "cena": 100.00
            },
            {
                "id_pokoju": 2,
                "cena": 150.00
            }
        ]
        ```
    *   W przypadku błędu, system otrzymuje kod błędu i komunikat o błędzie.
        ```json
        {
            "error": "Błąd pobierania cen"
        }
        ```

3.  **Walidacja i przetwarzanie danych:**
    *   System sprawdza poprawność otrzymanych danych (np. czy ceny są liczbami).
    *   System przelicza ceny uwzględniając prowizję dostawcy (np. cena * (1 - prowizja)).
    *   System aktualizuje ceny w lokalnej bazie danych.

4.  **Logowanie zmian:**
    *   Każda zmiana ceny jest logowana w historii zmian.
    *   System zapisuje datę i czas synchronizacji, starą cenę, nową cenę, id pokoju i id dostawcy.
    *   System wysyła powiadomienie o zmianach cen (np. email do administratora).
    *   W przypadku niepowodzenia synchronizacji, system loguje błąd i wysyła powiadomienie do administratora.

**Harmonogram synchronizacji:**

*   Automatyczna synchronizacja co 6 godzin.
*   Możliwość ręcznego wywołania synchronizacji przez pracownika.
*   Alerty w przypadku niepowodzenia synchronizacji (np. email do administratora).

**Obsługa błędów:**

*   System obsługuje błędy połączenia z API dostawcy (np. timeout, brak połączenia).
*   System obsługuje błędy autoryzacji (np. nieprawidłowy token).
*   System obsługuje błędy parsowania danych (np. nieprawidłowy format JSON).
*   System loguje wszystkie błędy i wysyła powiadomienia do administratora.

**Bezpieczeństwo:**

*   Poświadczenia dostawców (login i hasło) przechowywane są w zaszyfrowanej formie.
*   Komunikacja z API odbywa się przez HTTPS.
*   Implementowany jest mechanizm ograniczania liczby żądań (rate limiting), aby uniknąć przeciążenia API dostawcy.

### Model TypCennika

*   `id_typu`: INTEGER (Primary Key, Autoincrement)
*   `nazwa`: TEXT (Unique, Not Null, Max Length: 50) (np. "sezon niski", "sezon wysoki", "promocja")
*   `opis`: TEXT (Max Length: 200)
*   `dostawca_id`: INTEGER (Foreign Key referencing Dostawca, nullable)
    *   **Relacje:**
        *   TypCennika ma relację *wiele-do-jednego* z klasą `Dostawca` (opcjonalnie, wiele typów cenników może być powiązanych z jednym dostawcą).

### Model Rezerwacja

*   `id_rezerwacji`: INTEGER (Primary Key, Autoincrement)
*   `id_klienta`: INTEGER (Foreign Key referencing Gość, Not Null)
*   `id_pokoju`: INTEGER (Foreign Key referencing Pokój, Not Null)
*   `data_od`: DATE (Not Null)
*   `data_do`: DATE (Not Null)
*   `status`: TEXT (Not Null, Default: 'oczekująca', Enum: 'potwierdzona', 'anulowana', 'oczekująca')
    *   **Relacje:**
        *   Rezerwacja ma relację *wiele-do-jednego* z tabelą `Goście` (jeden gość może mieć wiele rezerwacji).
        *   Rezerwacja ma relację *wiele-do-jednego* z tabelą `Pokoje` (jeden pokój może mieć wiele rezerwacji).

## Opis Interfejsu Użytkownika

### Ekran Logowania
*   Pola: Login, Hasło
*   Przyciski: Zaloguj, Rejestracja

### Ekran Rejestracji
*   Pola: Imię, Nazwisko, Email, Hasło
*   Przyciski: Zarejestruj, Powrót do logowania

### Ekran Główny Klienta
*   Wyświetla: Listę dostępnych pokoi, opcję rezerwacji, opcję przeglądania rezerwacji, opcję anulowania rezerwacji, opcję zmiany rezerwacji
*   Przyciski: Wyloguj

### Ekran Główny Pracownika
*   Wyświetla: Opcje zarządzania pokojami, opcje obsługi gości, opcję przeglądania rezerwacji
*   Przyciski: Wyloguj

### Mockupy Ekranów

#### Ekran Logowania
![Mockup ekranu logowania](examples/mockup_logowanie.png)
*   **Opis:** Ekran logowania umożliwia użytkownikom (klientom i pracownikom) zalogowanie się do systemu.
*   **Elementy:**
    *   Pola tekstowe: Login, Hasło
    *   Przyciski: Zaloguj, Rejestracja (przenosi do ekranu rejestracji)
    *   Komunikaty: Informacje o błędach logowania (np. nieprawidłowy login lub hasło)
*   **Zachowanie:**
    *   Po wprowadzeniu poprawnych danych logowania, użytkownik jest przekierowywany do odpowiedniego ekranu głównego (klienta lub pracownika).
    *   Po wprowadzeniu niepoprawnych danych logowania, wyświetlany jest komunikat o błędzie.
    *   Przycisk "Rejestracja" przenosi do ekranu rejestracji.

#### Ekran Rejestracji
![Mockup ekranu rejestracji](examples/mockup_rejestracja.png)
*   **Opis:** Ekran rejestracji umożliwia nowym użytkownikom (klientom) zarejestrowanie się w systemie.
*   **Elementy:**
    *   Pola tekstowe: Imię, Nazwisko, Email, Hasło
    *   Przyciski: Zarejestruj, Powrót do logowania (przenosi do ekranu logowania)
    *   Komunikaty: Informacje o błędach rejestracji (np. nieprawidłowy email, hasło za krótkie)
*   **Zachowanie:**
    *   Po wprowadzeniu poprawnych danych rejestracyjnych, użytkownik jest rejestrowany w systemie i przekierowywany do ekranu logowania.
    *   Po wprowadzeniu niepoprawnych danych rejestracyjnych, wyświetlany jest komunikat o błędzie.
    *   Przycisk "Powrót do logowania" przenosi do ekranu logowania.

#### Ekran Główny Klienta
![Mockup ekranu głównego klienta](examples/mockup_klient.png)
*   **Opis:** Ekran główny klienta umożliwia klientom przeglądanie dostępnych pokoi, rezerwację pokoi, przeglądanie i anulowanie rezerwacji.
*   **Elementy:**
    *   Lista dostępnych pokoi (z filtrowaniem i sortowaniem)
    *   Opcje rezerwacji (wybór dat, pokoju)
    *   Opcje przeglądania rezerwacji (lista rezerwacji, szczegóły rezerwacji)
    *   Opcje anulowania rezerwacji
    *   Opcje zmiany rezerwacji
    *   Przycisk: Wyloguj
*   **Zachowanie:**
    *   Wyświetla listę dostępnych pokoi z możliwością filtrowania i sortowania.
    *   Umożliwia wybór pokoju i dat rezerwacji.
    *   Umożliwia przeglądanie listy rezerwacji i szczegółów rezerwacji.
    *   Umożliwia anulowanie rezerwacji.
    *   Umożliwia zmianę rezerwacji.
    *   Przycisk "Wyloguj" wylogowuje użytkownika z systemu.

#### Ekran Główny Pracownika
![Mockup ekranu głównego pracownika](examples/mockup_pracownik.png)
*   **Opis:** Ekran główny pracownika umożliwia pracownikom zarządzanie pokojami, obsługę gości i przeglądanie rezerwacji.
*   **Elementy:**
    *   Opcje zarządzania pokojami (dodawanie, edycja, usuwanie)
    *   Opcje obsługi gości (zameldowanie, wymeldowanie)
    *   Opcje przeglądania rezerwacji
    *   Przycisk: Wyloguj
*   **Zachowanie:**
    *   Umożliwia zarządzanie pokojami (dodawanie, edycja, usuwanie).
    *   Umożliwia obsługę gości (zameldowanie, wymeldowanie).
    *   Umożliwia przeglądanie listy rezerwacji.
    *   Przycisk "Wyloguj" wylogowuje użytkownika z systemu.

### Dostępność

System został zaprojektowany z myślą o dostępności dla osób niepełnosprawnych.

*   **Nawigacja klawiaturą:** Wszystkie elementy interfejsu są dostępne za pomocą klawiatury.
*   **Alternatywne teksty:** Wszystkie obrazy posiadają alternatywne teksty.
*   **Kontrast:** Kolory interfejsu zapewniają odpowiedni kontrast.
*   **Czytniki ekranu:** System jest kompatybilny z czytnikami ekranu.

### Walidacja Formularzy

System posiada walidację formularzy po stronie klienta i serwera.

*   **Walidacja po stronie klienta:** Walidacja jest wykonywana w przeglądarce użytkownika, aby zapewnić szybką informację zwrotną.
*   **Walidacja po stronie serwera:** Walidacja jest wykonywana na serwerze, aby zapewnić bezpieczeństwo danych.
*   **Komunikaty o błędach:** System wyświetla jasne i zrozumiałe komunikaty o błędach.

## Opis Bazy Danych

### Tabela Użytkownicy
*   `id_uzytkownika`: INTEGER PRIMARY KEY
*   `login`: TEXT
*   `haslo`: TEXT
*   `email`: TEXT
*   `rola`: TEXT (klient, pracownik)

### Tabela Pracownicy
*   `id_pracownika`: INTEGER PRIMARY KEY
*   `imie`: TEXT
*   `nazwisko`: TEXT
*   `email`: TEXT
*   `telefon`: TEXT
*   `login`: TEXT
*   `haslo`: TEXT
*   `rola`: TEXT (np. recepcjonista, menadżer)
*   **Relacje:**
    *   Pracownik ma relację *jeden-do-jednego* z tabelą `Użytkownicy` (jeden pracownik ma jedno konto użytkownika).

### Tabela Goście
*   `id_klienta`: INTEGER PRIMARY KEY
*   `imie`: TEXT
*   `nazwisko`: TEXT
*   `email`: TEXT
*   `telefon`: TEXT
*   **Relacje:**
    *   Gość ma relację *jeden-do-wielu* z tabelą `Rezerwacje` (jeden gość może mieć wiele rezerwacji).

### Tabela Pokoje
*   `id_pokoju`: INTEGER PRIMARY KEY
*   `numer_pokoju`: TEXT
*   `typ_pokoju`: TEXT (np. jednoosobowy, dwuosobowy, apartament)
*   `opis`: TEXT
*   `cena`: REAL
*   `dostepny`: BOOLEAN
*   **Relacje:**
    *   Pokój ma relację *jeden-do-wielu* z tabelą `Rezerwacje` (jeden pokój może być zarezerwowany wiele razy).

### Tabela Rezerwacje
*   `id_rezerwacji`: INTEGER PRIMARY KEY
*   `id_klienta`: INTEGER
*   `id_pokoju`: INTEGER
*   `data_od`: DATE
*   `data_do`: DATE
*   `status`: TEXT (potwierdzona, anulowana, oczekująca)
*   **Relacje:**
    *   Rezerwacja ma relację *wiele-do-jednego* z tabelą `Goście` (jeden gość może mieć wiele rezerwacji).
    *   Rezerwacja ma relację *wiele-do-jednego* z tabelą `Pokoje` (jeden pokój może mieć wiele rezerwacji).

## Technologie Użyte

*   **Język programowania:** Python
*   **Framework:** Flask
*   **Baza danych:** SQLite
*   **Biblioteka ORM:** SQLAlchemy
*   **Biblioteki do integracji API:**
    *   `requests` - do komunikacji HTTP z API dostawców (wersja 2.31.0)
    *   `celery` - do zarządzania zadaniami okresowymi (synchronizacja cen) (wersja 5.3.6)
    *   `redis` - jako broker wiadomości dla Celery (wersja 4.6.0)
    *   `cryptography` - do szyfrowania poświadczeń API (wersja 41.0.7)
*   **Wersje używanych bibliotek i frameworków:**
    *   Python 3.11
    *   Flask 3.0.0
    *   SQLAlchemy 2.0.23
    *   SQLite 3.44.0
*   **Konfiguracja środowiska:**
    *   Wymagania systemowe:
        *   Zainstalowany Python 3.11
        *   Zainstalowany pip (menadżer pakietów Pythona)
        *   Zainstalowany virtualenv (opcjonalnie, zalecane)
    *   Narzędzia do zarządzania zależnościami:
        *   pip (do instalacji pakietów Pythona)
        *   virtualenv (do tworzenia izolowanych środowisk Pythona)
*   **Instalacja zależności:**
    *   Aby zainstalować zależności, użyj polecenia: `pip install -r requirements.txt`

## Plan Testów

*   **Testy jednostkowe:** Testowanie poszczególnych funkcji i klas.
*   **Testy integracyjne:** Testowanie interakcji między różnymi modułami systemu.
*   **Testy akceptacyjne:** Testowanie systemu z perspektywy użytkownika.
*   **Testy bezpieczeństwa:** Testowanie systemu pod kątem luk bezpieczeństwa.
*   **Testy synchronizacji cen:**
    - Testowanie poprawnego pobierania tokenu autoryzacyjnego
    - Testowanie parsowania odpowiedzi z API dostawców
    - Testowanie mechanizmu aktualizacji cen
    - Testowanie obsługi błędów (timeout, nieprawidłowe dane, wygaśnięcie tokenu)
    - Testowanie mechanizmu powiadomień o zmianach cen
*   **Narzędzia do testowania:**
    *   **pytest:** Używany do testów jednostkowych i integracyjnych.
    *   **requests:** Używany do testowania API.
    *   **Selenium:** Używany do testów akceptacyjnych (UI).
*   **Automatyzacja testów:**
    *   Testy jednostkowe i integracyjne są automatycznie uruchamiane przy każdej zmianie kodu.
    *   Testy akceptacyjne są uruchamiane regularnie (np. raz dziennie).
*   **Testy wydajnościowe:**
    *   **Load testing:** Testowanie systemu pod obciążeniem, aby sprawdzić jego wydajność i stabilność.
    *   **Stress testing:** Testowanie systemu w ekstremalnych warunkach, aby sprawdzić jego odporność na awarie.
*   **Testy bezpieczeństwa:**
    *   **Penetration testing:** Testowanie systemu pod kątem luk bezpieczeństwa.
    *   **SQL Injection testing:** Testowanie systemu pod kątem podatności na ataki SQL Injection.
    *   **XSS testing:** Testowanie systemu pod kątem podatności na ataki XSS.
*   **Szczegółowy plan testów:**
    *   **Testy jednostkowe:**
        *   Testowanie poszczególnych funkcji i klas (np. modele danych, logika biznesowa).
        *   Pokrycie kodu testami na poziomie 80%.
    *   **Testy integracyjne:**
        *   Testowanie interakcji między różnymi modułami systemu (np. moduł rezerwacji, moduł pokoi).
        *   Testowanie komunikacji z bazą danych.
    *   **Testy akceptacyjne:**
        *   Testowanie systemu z perspektywy użytkownika (np. rezerwacja pokoju, logowanie, zarządzanie pokojami).
        *   Testowanie interfejsu użytkownika (UI).
    *   **Testy API:**
        *   Testowanie wszystkich endpointów API (np. GET, POST, PUT, DELETE).
        *   Testowanie poprawności odpowiedzi (kody statusu, format JSON).
        *   Testowanie autoryzacji i autentykacji.
    *   **Testy synchronizacji cen:**
        *   Testowanie poprawnego pobierania tokenu autoryzacyjnego.
        *   Testowanie parsowania odpowiedzi z API dostawców.
        *   Testowanie mechanizmu aktualizacji cen.
        *   Testowanie obsługi błędów (timeout, nieprawidłowe dane, wygaśnięcie tokenu).
        *   Testowanie mechanizmu powiadomień o zmianach cen.
    *   **Testy wydajnościowe:**
        *   Testowanie systemu pod obciążeniem (np. 100 jednoczesnych użytkowników).
        *   Testowanie czasu odpowiedzi serwera.
        *   Testowanie wykorzystania zasobów (CPU, pamięć).
    *   **Testy bezpieczeństwa:**
        *   Testowanie systemu pod kątem luk bezpieczeństwa (np. SQL Injection, XSS).
        *   Testowanie autoryzacji i autentykacji.
        *   Testowanie ochrony przed atakami.

## Architektura Systemu

System rezerwacji hotelowej będzie oparty na architekturze trójwarstwowej:

1.  **Warstwa prezentacji (UI):**
    *   Odpowiedzialna za interakcję z użytkownikiem.
    *   Zawiera interfejs użytkownika (ekrany logowania, rejestracji, główne ekrany klienta i pracownika).
    *   Używa Flask do obsługi żądań HTTP i renderowania szablonów HTML.

2.  **Warstwa logiki biznesowej (aplikacji):**
    *   Odpowiedzialna za logikę aplikacji, w tym obsługę rezerwacji, zarządzanie pokojami, autentykację użytkowników.
    *   Zawiera klasy i funkcje, które implementują przypadki użycia.
    *   Komunikuje się z warstwą prezentacji i warstwą danych.

3.  **Warstwa danych:**
    *   Odpowiedzialna za dostęp do danych w bazie danych.
    *   Używa SQLAlchemy do mapowania obiektowo-relacyjnego (ORM).
    *   Zawiera modele danych (klasy reprezentujące tabele w bazie danych).

**Komponenty:**

*   **Moduł Użytkowników:** Obsługuje logowanie, rejestrację i zarządzanie użytkownikami.
*   **Moduł Rezerwacji:** Obsługuje rezerwacje pokoi, anulowanie i zmiany rezerwacji.
*   **Moduł Pokoi:** Obsługuje zarządzanie pokojami (dodawanie, edycja, usuwanie).
*   **Moduł Gości:** Obsługuje dane gości.
*   **Moduł Pracowników:** Obsługuje dane pracowników.

**Interakcje:**

*   Warstwa prezentacji (UI) wysyła żądania HTTP do warstwy logiki biznesowej (aplikacji).
*   Warstwa logiki biznesowej przetwarza żądania, wykonuje operacje biznesowe i komunikuje się z warstwą danych.
*   Warstwa danych wykonuje operacje na bazie danych (CRUD - Create, Read, Update, Delete).

## Diagram Architektury Systemu

Poniżej przedstawiono diagram architektury systemu:

```mermaid
graph LR
    A[Użytkownik] --> B(Warstwa Prezentacji (UI));
    B --> C(Warstwa Logiki Biznesowej (Aplikacja));
    C --> D(Warstwa Danych);
    D --> E[Baza Danych];
    C --> F(Kolejka Zadań (Celery));
    F --> G[Redis];
    B --> H(Load Balancer);
    H --> I(Serwery Aplikacji);
    I --> C;
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#ccf,stroke:#333,stroke-width:2px
    style G fill:#ccf,stroke:#333,stroke-width:2px
```

### Opis Komponentów

*   **Użytkownik:** Klient lub pracownik hotelu korzystający z systemu.
*   **Warstwa Prezentacji (UI):**
    *   Odpowiedzialna za interakcję z użytkownikiem.
    *   Zawiera interfejs użytkownika (ekrany logowania, rejestracji, główne ekrany klienta i pracownika).
    *   Używa Flask do obsługi żądań HTTP i renderowania szablonów HTML.
    *   Komunikuje się z warstwą logiki biznesowej za pomocą żądań HTTP.
*   **Warstwa Logiki Biznesowej (Aplikacja):**
    *   Odpowiedzialna za logikę aplikacji, w tym obsługę rezerwacji, zarządzanie pokojami, autentykację użytkowników.
    *   Zawiera klasy i funkcje, które implementują przypadki użycia.
    *   Komunikuje się z warstwą prezentacji i warstwą danych.
    *   Wykorzystuje wzorzec projektowy MVC (Model-View-Controller).
*   **Warstwa Danych:**
    *   Odpowiedzialna za dostęp do danych w bazie danych.
    *   Używa SQLAlchemy do mapowania obiektowo-relacyjnego (ORM).
    *   Zawiera modele danych (klasy reprezentujące tabele w bazie danych).
    *   Wykorzystuje wzorzec projektowy Repository.
*   **Baza Danych:**
    *   Przechowuje dane systemu (użytkowników, pokoje, rezerwacje, gości).
    *   Wykorzystuje SQLite jako bazę danych.
*   **Kolejka Zadań (Celery):**
    *   Odpowiedzialna za obsługę zadań asynchronicznych (np. synchronizacja cen).
    *   Wykorzystuje Celery do zarządzania zadaniami.
*   **Redis:**
    *   Wykorzystywany jako broker wiadomości dla Celery.
    *   Wykorzystywany jako cache do przechowywania często używanych danych.
*   **Load Balancer:**
    *   Rozdziela ruch między serwerami aplikacji.
    *   Zapewnia skalowalność i dostępność systemu.
*   **Serwery Aplikacji:**
    *   Serwery, na których działa aplikacja.
    *   Każdy serwer może obsługiwać część ruchu.

### Wzorce Projektowe

System wykorzystuje następujące wzorce projektowe:

*   **MVC (Model-View-Controller):** Wzorzec projektowy używany w warstwie logiki biznesowej do oddzielenia logiki aplikacji od interfejsu użytkownika.
*   **Repository:** Wzorzec projektowy używany w warstwie danych do oddzielenia logiki dostępu do danych od logiki biznesowej.
*   **Singleton:** Wzorzec projektowy używany do tworzenia jednej instancji klasy (np. połączenie z bazą danych).
*   **Factory:** Wzorzec projektowy używany do tworzenia obiektów (np. obiekty modeli danych).

### Komunikacja Między Komponentami

*   **Warstwa Prezentacji (UI) <-> Warstwa Logiki Biznesowej (Aplikacja):** Komunikacja odbywa się za pomocą żądań HTTP (GET, POST, PUT, DELETE).
*   **Warstwa Logiki Biznesowej (Aplikacja) <-> Warstwa Danych:** Komunikacja odbywa się za pomocą interfejsów (np. Repository).
*   **Warstwa Logiki Biznesowej (Aplikacja) <-> Kolejka Zadań (Celery):** Komunikacja odbywa się za pomocą brokera wiadomości (Redis).

Dzięki tej architekturze system jest skalowalny, łatwy w utrzymaniu i rozwijaniu.

**Interakcje:**

*   Warstwa prezentacji wysyła żądania do warstwy logiki biznesowej.
*   Warstwa logiki biznesowej przetwarza żądania i komunikuje się z warstwą danych.
*   Warstwa danych wykonuje operacje na bazie danych.

## Plan Wdrożenia

1.  **Konfiguracja serwera:** Przygotowanie serwera do hostowania aplikacji.
2.  **Instalacja oprogramowania:** Instalacja niezbędnego oprogramowania (Python, Flask, itp.).
3.  **Konfiguracja bazy danych:** Konfiguracja bazy danych SQLite.
4.  **Wdrożenie aplikacji:** Wdrożenie aplikacji na serwerze.
5.  **Testowanie w środowisku produkcyjnym:** Przeprowadzenie testów w środowisku produkcyjnym.
6.  **Uruchomienie systemu:** Uruchomienie systemu dla użytkowników.
7.  **Monitoring:** Monitorowanie działania systemu.

## Opis API

### Użytkownicy

*   **POST /users/register:** Rejestracja nowego użytkownika.
*   **POST /users/login:** Logowanie użytkownika.
*   **GET /users/{id}:** Pobranie danych użytkownika o podanym ID.

### Pokoje

*   **GET /rooms:** Pobranie listy wszystkich pokoi.
*   **GET /rooms/{id}:** Pobranie danych pokoju o podanym ID.
*   **POST /rooms:** Dodanie nowego pokoju (tylko dla pracowników).
*   **PUT /rooms/{id}:** Edycja danych pokoju o podanym ID (tylko dla pracowników).
*   **DELETE /rooms/{id}:** Usunięcie pokoju o podanym ID (tylko dla pracowników).

### Rezerwacje

*   **GET /reservations:** Pobranie listy wszystkich rezerwacji.
*   **GET /reservations/{id}:** Pobranie danych rezerwacji o podanym ID.
*   **POST /reservations:** Dodanie nowej rezerwacji.
*   **PUT /reservations/{id}:** Edycja danych rezerwacji o podanym ID.
*   **DELETE /reservations/{id}:** Anulowanie rezerwacji o podanym ID.
*   **GET /reservations/user/{user_id}**: Pobranie rezerwacji dla danego użytkownika.

### Goście

*   **GET /guests:** Pobranie listy wszystkich gości.
*   **GET /guests/{id}:** Pobranie danych gościa o podanym ID.
*   **POST /guests:** Dodanie nowego gościa.
*   **PUT /guests/{id}:** Edycja danych gościa o podanym ID.
*   **DELETE /guests/{id}:** Usunięcie gościa o podanym ID.

Opis diagramu klas dla pracowników hotelu:

*   **Klasa Pracownik:**
    *   `id_pracownika`: int (identyfikator pracownika)
    *   `imie`: string (imię pracownika)
    *   `nazwisko`: string (nazwisko pracownika)
    *   `email`: string (adres email pracownika)
    *   `telefon`: string (numer telefonu pracownika)
    *   `login`: string (login pracownika)
    *   `haslo`: string (hasło pracownika)
    *   `rola`: string (rola pracownika np. "recepcjonista", "menadżer")

### Użytkownicy

#### POST /users/register

*   **Opis:** Rejestracja nowego użytkownika.
*   **Zapytanie:**
    ```json
    {
        "login": "nowy_uzytkownik",
        "haslo": "haslo123",
        "email": "nowy@example.com"
    }
    ```
*   **Odpowiedź (201 Created):**
    ```json
    {
        "message": "Użytkownik zarejestrowany pomyślnie",
        "user_id": 123
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Odpowiedź (409 Conflict):**
    ```json
    {
        "error": "Użytkownik o podanym emailu już istnieje"
    }
    ```
*   **Parametry:**
    *   `login` (string, required): Login użytkownika.
    *   `haslo` (string, required): Hasło użytkownika.
    *   `email` (string, required): Email użytkownika.

#### POST /users/login

*   **Opis:** Logowanie użytkownika.
*   **Zapytanie:**
    ```json
    {
        "login": "uzytkownik",
        "haslo": "haslo123"
    }
    ```
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Zalogowano pomyślnie",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
    }
    ```
*   **Odpowiedź (401 Unauthorized):**
    ```json
    {
        "error": "Nieprawidłowy login lub hasło"
    }
    ```
*   **Parametry:**
    *   `login` (string, required): Login użytkownika.
    *   `haslo` (string, required): Hasło użytkownika.

#### GET /users/{id}

*   **Opis:** Pobranie danych użytkownika o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "id_uzytkownika": 123,
        "login": "uzytkownik",
        "email": "uzytkownik@example.com",
        "rola": "klient"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Użytkownik nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID użytkownika.

### Pokoje

#### GET /rooms

*   **Opis:** Pobranie listy wszystkich pokoi.
*   **Odpowiedź (200 OK):**
    ```json
    [
        {
            "id_pokoju": 1,
            "numer_pokoju": "101",
            "typ_pokoju": "jednoosobowy",
            "opis": "Pokój z widokiem na morze",
            "dostepny": true
        },
        {
            "id_pokoju": 2,
            "numer_pokoju": "102",
            "typ_pokoju": "dwuosobowy",
            "opis": "Pokój z balkonem",
            "dostepny": false
        }
    ]
    ```

#### GET /rooms/{id}

*   **Opis:** Pobranie danych pokoju o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "id_pokoju": 1,
        "numer_pokoju": "101",
        "typ_pokoju": "jednoosobowy",
        "opis": "Pokój z widokiem na morze",
        "dostepny": true
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Pokój nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID pokoju.

#### POST /rooms

*   **Opis:** Dodanie nowego pokoju (tylko dla pracowników).
*   **Zapytanie:**
    ```json
    {
        "numer_pokoju": "201",
        "typ_pokoju": "dwuosobowy",
        "opis": "Pokój z klimatyzacją"
    }
    ```
*   **Odpowiedź (201 Created):**
    ```json
    {
        "message": "Pokój dodany pomyślnie",
        "room_id": 3
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Odpowiedź (403 Forbidden):**
    ```json
    {
        "error": "Brak uprawnień"
    }
    ```
*   **Parametry:**
    *   `numer_pokoju` (string, required): Numer pokoju.
    *   `typ_pokoju` (string, required): Typ pokoju.
    *   `opis` (string, optional): Opis pokoju.

#### PUT /rooms/{id}

*   **Opis:** Edycja danych pokoju o podanym ID (tylko dla pracowników).
*   **Zapytanie:**
    ```json
    {
        "opis": "Pokój z widokiem na park"
    }
    ```
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Pokój zaktualizowany pomyślnie"
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Odpowiedź (403 Forbidden):**
    ```json
    {
        "error": "Brak uprawnień"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Pokój nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID pokoju.
    *   `opis` (string, optional): Opis pokoju.

#### DELETE /rooms/{id}

*   **Opis:** Usunięcie pokoju o podanym ID (tylko dla pracowników).
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Pokój usunięty pomyślnie"
    }
    ```
*   **Odpowiedź (403 Forbidden):**
    ```json
    {
        "error": "Brak uprawnień"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Pokój nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID pokoju.

### Rezerwacje

#### GET /reservations

*   **Opis:** Pobranie listy wszystkich rezerwacji.
*  **Odpowiedź (200 OK):**
    ```json
    [
        {
            "id_rezerwacji": 1,
            "id_klienta": 1,
            "id_pokoju": 1,
            "data_od": "2024-01-15",
            "data_do": "2024-01-20",
            "status": "potwierdzona"
        },
        {
            "id_rezerwacji": 2,
            "id_klienta": 2,
            "id_pokoju": 2,
            "data_od": "2024-02-01",
            "data_do": "2024-02-05",
            "status": "oczekująca"
        }
    ]
    ```

#### GET /reservations/{id}

*   **Opis:** Pobranie danych rezerwacji o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "id_rezerwacji": 1,
        "id_klienta": 1,
        "id_pokoju": 1,
        "data_od": "2024-01-15",
        "data_do": "2024-01-20",
        "status": "potwierdzona"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Rezerwacja nie znaleziona"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID rezerwacji.

#### POST /reservations

*   **Opis:** Dodanie nowej rezerwacji.
*   **Zapytanie:**
    ```json
    {
        "id_klienta": 1,
        "id_pokoju": 1,
        "data_od": "2024-03-01",
        "data_do": "2024-03-05"
    }
    ```
*   **Odpowiedź (201 Created):**
    ```json
    {
        "message": "Rezerwacja dodana pomyślnie",
        "reservation_id": 3
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Parametry:**
    *   `id_klienta` (integer, required): ID klienta.
    *   `id_pokoju` (integer, required): ID pokoju.
    *   `data_od` (date, required): Data rozpoczęcia rezerwacji.
    *   `data_do` (date, required): Data zakończenia rezerwacji.

#### PUT /reservations/{id}

*   **Opis:** Edycja danych rezerwacji o podanym ID.
*   **Zapytanie:**
    ```json
    {
        "status": "potwierdzona"
    }
    ```
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Rezerwacja zaktualizowana pomyślnie"
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Rezerwacja nie znaleziona"
    }
    ```
*   **Parametry:**
    *    `id` (integer, required): ID rezerwacji.
    *   `status` (string, optional): Status rezerwacji.

#### DELETE /reservations/{id}

*   **Opis:** Anulowanie rezerwacji o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Rezerwacja anulowana pomyślnie"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Rezerwacja nie znaleziona"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID rezerwacji.

#### GET /reservations/user/{user_id}

*   **Opis:** Pobranie rezerwacji dla danego użytkownika.
*   **Odpowiedź (200 OK):**
    ```json
    [
        {
            "id_rezerwacji": 1,
            "id_klienta": 1,
            "id_pokoju": 1,
            "data_od": "2024-01-15",
            "data_do": "2024-01-20",
            "status": "potwierdzona"
        },
        {
            "id_rezerwacji": 3,
            "id_klienta": 1,
            "id_pokoju": 2,
            "data_od": "2024-03-01",
            "data_do": "2024-03-05",
            "status": "oczekująca"
        }
    ]
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Użytkownik nie posiada rezerwacji"
    }
    ```
*   **Parametry:**
    *   `user_id` (integer, required): ID użytkownika.

### Goście

#### GET /guests

*   **Opis:** Pobranie listy wszystkich gości.
*   **Odpowiedź (200 OK):**
    ```json
    [
        {
            "id_klienta": 1,
            "imie": "Jan",
            "nazwisko": "Kowalski",
            "email": "jan.kowalski@example.com",
            "telefon": "123-456-789"
        },
        {
            "id_klienta": 2,
            "imie": "Anna",
            "nazwisko": "Nowak",
            "email": "anna.nowak@example.com",
            "telefon": "987-654-321"
        }
    ]
    ```

#### GET /guests/{id}

*   **Opis:** Pobranie danych gościa o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "id_klienta": 1,
        "imie": "Jan",
        "nazwisko": "Kowalski",
        "email": "jan.kowalski@example.com",
        "telefon": "123-456-789"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Gość nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID gościa.

#### POST /guests

*   **Opis:** Dodanie nowego gościa.
*   **Zapytanie:**
    ```json
    {
        "imie": "Piotr",
        "nazwisko": "Zieliński",
        "email": "piotr.zielinski@example.com",
        "telefon": "111-222-333"
    }
    ```
*   **Odpowiedź (201 Created):**
    ```json
    {
        "message": "Gość dodany pomyślnie",
        "guest_id": 3
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Parametry:**
    *   `imie` (string, required): Imię gościa.
    *   `nazwisko` (string, required): Nazwisko gościa.
    *   `email` (string, required): Email gościa.
    *   `telefon` (string, optional): Telefon gościa.

#### PUT /guests/{id}

*   **Opis:** Edycja danych gościa o podanym ID.
*   **Zapytanie:**
    ```json
    {
        "telefon": "444-555-666"
    }
    ```
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Gość zaktualizowany pomyślnie"
    }
    ```
*   **Odpowiedź (400 Bad Request):**
    ```json
    {
        "error": "Nieprawidłowe dane wejściowe"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Gość nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID gościa.
    *   `telefon` (string, optional): Telefon gościa.

#### DELETE /guests/{id}

*   **Opis:** Usunięcie gościa o podanym ID.
*   **Odpowiedź (200 OK):**
    ```json
    {
        "message": "Gość usunięty pomyślnie"
    }
    ```
*   **Odpowiedź (404 Not Found):**
    ```json
    {
        "error": "Gość nie znaleziony"
    }
    ```
*   **Parametry:**
    *   `id` (integer, required): ID gościa.

Opis diagramu klas dla użytkowników systemu:

*   **Klasa Użytkownik:**
    *   `id_uzytkownika`: int (identyfikator użytkownika)
    *   `login`: string (login użytkownika)
    *   `haslo`: string (hasło użytkownika)
    *   `email`: string (adres email użytkownika)
    *   `rola`: string (rola użytkownika np. "klient", "pracownik")

        *   Pokój ma relację *jeden-do-wielu* z klasą `Rezerwacja` (jeden pokój może być zarezerwowany wiele razy).

### Pokoje

Opis diagramu klas dla pokoi:

*   **Klasa Pokój:**
    *   `id_pokoju`: int (identyfikator pokoju)
    *   `numer_pokoju`: string (numer pokoju)
    *   `typ_pokoju`: string (np. "jednoosobowy", "dwuosobowy", "apartament")
    *   `opis`: string (opis pokoju)
    *   `cena`: decimal (cena za noc)
    *   `dostepny`: boolean (czy pokój jest dostępny)
    *   **Relacje:**
        *   Pokój ma relację *jeden-do-wielu* z klasą `Rezerwacja` (jeden pokój może być zarezerwowany wiele razy).

### Goście

Opis diagramu klas dla gości:

*   **Klasa Gość:**
    *   `id_klienta`: int (identyfikator klienta)
    *   `imie`: string (imię gościa)
    *   `nazwisko`: string (nazwisko gościa)
    *   `email`: string (adres email gościa)
    *   `telefon`: string (numer telefonu gościa)
    *   **Relacje:**
        *   Gość ma relację *jeden-do-wielu* z klasą `Rezerwacja` (jeden gość może mieć wiele rezerwacji).

## Skalowalność Systemu

System rezerwacji hotelowej został zaprojektowany z myślą o skalowalności, aby sprostać rosnącemu obciążeniu i liczbie użytkowników. Poniżej przedstawiono kluczowe aspekty skalowalności systemu:

### Skalowanie Horyzontalne

System może być skalowany horyzontalnie poprzez dodawanie nowych serwerów aplikacji. Każdy serwer może obsługiwać część ruchu, co pozwala na rozłożenie obciążenia.

*   **Load Balancing:** Ruch jest rozdzielany między serwerami za pomocą load balancera. Load balancer monitoruje obciążenie serwerów i kieruje żądania do najmniej obciążonego serwera.
*   **Bezstanowość Aplikacji:** Aplikacja jest bezstanowa, co oznacza, że nie przechowuje żadnych danych sesji. Dzięki temu każde żądanie może być obsłużone przez dowolny serwer.

### Skalowanie Bazy Danych

Baza danych może być skalowana w celu obsługi większej liczby zapytań i danych.

*   **Replikacja:** Baza danych może być replikowana na wiele serwerów. Replikacja pozwala na odczytywanie danych z wielu serwerów, co zwiększa wydajność odczytu.
*   **Partycjonowanie:** Baza danych może być partycjonowana na wiele serwerów. Partycjonowanie pozwala na rozłożenie danych na wiele serwerów, co zwiększa wydajność zapisu i odczytu.

### Zarządzanie Obciążeniem

System wykorzystuje mechanizmy zarządzania obciążeniem, aby zapewnić stabilność i wydajność.

*   **Kolejki Zadań:** Zadania asynchroniczne, takie jak synchronizacja cen, są obsługiwane przez kolejki zadań (Celery). Kolejki zadań pozwalają na rozłożenie obciążenia i uniknięcie przeciążenia serwerów.
*   **Cache:** System wykorzystuje cache do przechowywania często używanych danych. Cache pozwala na zmniejszenie liczby zapytań do bazy danych, co zwiększa wydajność.

### Technologie Skalowalności

System wykorzystuje następujące technologie do zapewnienia skalowalności:

*   **Flask:** Flask jest lekkim frameworkiem, który pozwala na łatwe skalowanie aplikacji.
*   **Celery:** Celery jest biblioteką do zarządzania zadaniami asynchronicznymi, która pozwala na rozłożenie obciążenia.
*   **Redis:** Redis jest bazą danych typu klucz-wartość, która jest wykorzystywana jako broker wiadomości dla Celery i jako cache.
*   **Load Balancer:** Load balancer rozdziela ruch między serwerami aplikacji.

### Plan Skalowania

1.  **Monitorowanie:** Monitorowanie obciążenia systemu za pomocą narzędzi monitorujących (np. Prometheus, Grafana).
2.  **Analiza:** Analiza danych monitorowania w celu identyfikacji wąskich gardeł.
3.  **Skalowanie:** Skalowanie systemu poprzez dodawanie nowych serwerów aplikacji, replikację bazy danych lub partycjonowanie bazy danych.
4.  **Testowanie:** Testowanie systemu po skalowaniu w celu upewnienia się, że działa poprawnie.

Dzięki tym mechanizmom system rezerwacji hotelowej jest w stanie obsłużyć rosnącą liczbę użytkowników i obciążenie, zapewniając stabilność i wydajność.

## Monitorowanie i Logowanie

System rezerwacji hotelowej został zaprojektowany z myślą o monitorowaniu i logowaniu, aby zapewnić stabilność i łatwość diagnozowania problemów. Poniżej przedstawiono kluczowe aspekty monitorowania i logowania systemu:

### Monitorowanie

System wykorzystuje narzędzia do monitorowania, aby śledzić wydajność i dostępność aplikacji.

*   **Narzędzia monitorujące:**
    *   **Prometheus:** System wykorzystuje Prometheus do zbierania metryk z aplikacji. Prometheus zbiera metryki z różnych źródeł, takich jak serwery aplikacji, bazy danych i kolejki zadań.
    *   **Grafana:** System wykorzystuje Grafana do wizualizacji metryk zebranych przez Prometheus. Grafana pozwala na tworzenie dashboardów, które pokazują wydajność systemu w czasie rzeczywistym.
*   **Metryki:**
    *   **Czas odpowiedzi:** Czas odpowiedzi serwera na żądania HTTP.
    *   **Obciążenie procesora:** Obciążenie procesora serwerów aplikacji.
    *   **Wykorzystanie pamięci:** Wykorzystanie pamięci serwerów aplikacji.
    *   **Liczba zapytań do bazy danych:** Liczba zapytań do bazy danych.
    *   **Liczba aktywnych rezerwacji:** Liczba aktywnych rezerwacji w systemie.
    *   **Liczba błędów:** Liczba błędów w systemie.
*   **Alerty:**
    *   System generuje alerty w przypadku przekroczenia progów metryk. Alerty są wysyłane do administratorów systemu, aby mogli szybko zareagować na problemy.
    *   Przykładowe alerty:
        *   Wysokie obciążenie procesora
        *   Niskie wykorzystanie pamięci
        *   Długi czas odpowiedzi
        *   Błędy w aplikacji

### Logowanie

System wykorzystuje logowanie do rejestrowania zdarzeń w systemie. Logi są wykorzystywane do diagnozowania problemów i analizy zachowania systemu.

*   **Logi aplikacji:**
    *   System loguje zdarzenia w aplikacji, takie jak:
        *   Logowanie i wylogowanie użytkowników
        *   Rezerwacje pokoi
        *   Zmiany w danych pokoi
        *   Błędy w aplikacji
    *   Logi są przechowywane w plikach tekstowych.
*   **Logi audytowe:**
    *   System loguje zdarzenia związane z bezpieczeństwem, takie jak:
        *   Zmiany w uprawnieniach użytkowników
        *   Nieudane próby logowania
    *   Logi audytowe są przechowywane w oddzielnych plikach.
*   **Poziomy logowania:**
    *   System wykorzystuje różne poziomy logowania, takie jak:
        *   DEBUG: Szczegółowe informacje o działaniu systemu.
        *   INFO: Informacje o ważnych zdarzeniach w systemie.
        *   WARNING: Ostrzeżenia o potencjalnych problemach.
        *   ERROR: Błędy w systemie.
        *   CRITICAL: Krytyczne błędy w systemie.
    *   Poziom logowania można konfigurować w pliku konfiguracyjnym.

### Technologie Monitorowania i Logowania

System wykorzystuje następujące technologie do monitorowania i logowania:

*   **Prometheus:** Do zbierania metryk.
*   **Grafana:** Do wizualizacji metryk.
*   **Python logging:** Do logowania zdarzeń w aplikacji.

Dzięki tym mechanizmom system rezerwacji hotelowej jest w stanie monitorować swoje działanie i szybko reagować na problemy, zapewniając stabilność i wydajność.

## Wdrożenie Ciągłe (CI/CD)

System rezerwacji hotelowej wykorzystuje praktyki CI/CD, aby zapewnić szybkie i bezpieczne wdrażanie zmian. Poniżej przedstawiono kluczowe aspekty CI/CD systemu:

### Narzędzia CI/CD

System wykorzystuje następujące narzędzia do CI/CD:

*   **GitHub Actions:** Do automatyzacji budowania, testowania i wdrażania aplikacji.
*   **Docker:** Do konteneryzacji aplikacji.
*   **Docker Hub:** Do przechowywania obrazów Docker.

### Proces Wdrażania

Proces wdrażania składa się z następujących kroków:

1.  **Zmiana kodu:** Programista wprowadza zmiany w kodzie i przesyła je do repozytorium GitHub.
2.  **Automatyczne budowanie:** GitHub Actions automatycznie buduje aplikację po każdej zmianie kodu.
3.  **Testowanie:** GitHub Actions automatycznie uruchamia testy jednostkowe, integracyjne i akceptacyjne.
4.  **Konteneryzacja:** GitHub Actions tworzy obraz Docker aplikacji.
5.  **Przechowywanie obrazu:** Obraz Docker jest przechowywany w Docker Hub.
6.  **Wdrożenie na serwerze:** Obraz Docker jest wdrażany na serwerze produkcyjnym.

### Środowiska Wdrożeniowe

System wykorzystuje następujące środowiska wdrożeniowe:

*   **Środowisko deweloperskie:** Środowisko, w którym programiści pracują nad kodem.
*   **Środowisko testowe:** Środowisko, w którym testowane są zmiany przed wdrożeniem na produkcję.
*   **Środowisko produkcyjne:** Środowisko, w którym działa aplikacja dla użytkowników.

### Automatyzacja Wdrożeń

System wykorzystuje automatyzację wdrożeń, aby zapewnić szybkie i bezpieczne wdrażanie zmian.

*   **Automatyczne wdrożenia:** Wdrożenia na środowisko testowe są automatyczne po każdej zmianie kodu.
*   **Wdrożenia na produkcję:** Wdrożenia na środowisko produkcyjne są wykonywane ręcznie po pozytywnym przejściu testów w środowisku testowym.

### Plan Wdrożenia

1.  **Konfiguracja GitHub Actions:** Konfiguracja GitHub Actions do automatycznego budowania, testowania i wdrażania aplikacji.
2.  **Konteneryzacja aplikacji:** Konteneryzacja aplikacji za pomocą Docker.
3.  **Konfiguracja Docker Hub:** Konfiguracja Docker Hub do przechowywania obrazów Docker.
4.  **Wdrożenie na serwerze:** Wdrożenie aplikacji na serwerze produkcyjnym.
5.  **Testowanie w środowisku produkcyjnym:** Przeprowadzenie testów w środowisku produkcyjnym.
6.  **Uruchomienie systemu:** Uruchomienie systemu dla użytkowników.
7.  **Monitoring:** Monitorowanie działania systemu.

Dzięki tym mechanizmom system rezerwacji hotelowej jest w stanie szybko i bezpiecznie wdrażać zmiany, zapewniając ciągłą dostępność i stabilność.

## Backup i Odzyskiwanie Danych

System rezerwacji hotelowej został zaprojektowany z myślą o bezpieczeństwie danych i możliwości ich odzyskania w przypadku awarii. Poniżej przedstawiono kluczowe aspekty backupu i odzyskiwania danych:

### Strategie Backupu

System wykorzystuje następujące strategie backupu:

*   **Pełny backup:** Pełny backup bazy danych jest wykonywany raz dziennie o godzinie 00:00. Pełny backup zawiera wszystkie dane z bazy danych.
*   **Backup przyrostowy:** Backup przyrostowy bazy danych jest wykonywany co 6 godzin. Backup przyrostowy zawiera tylko zmiany, które zostały wprowadzone od ostatniego pełnego backupu lub backupu przyrostowego.
*   **Backup logów:** Logi transakcyjne bazy danych są backupowane co godzinę. Logi transakcyjne zawierają informacje o wszystkich zmianach w bazie danych.

### Przechowywanie Backupów

Backupy są przechowywane w następujących lokalizacjach:

*   **Lokalny serwer:** Backupy są przechowywane na lokalnym serwerze w oddzielnym katalogu.
*   **Chmura:** Backupy są również przechowywane w chmurze (np. Amazon S3, Google Cloud Storage) w celu zapewnienia dodatkowej ochrony przed awariami.

### Proces Odzyskiwania Danych

Proces odzyskiwania danych składa się z następujących kroków:

1.  **Identyfikacja problemu:** Identyfikacja problemu, który spowodował utratę danych.
2.  **Wybór backupu:** Wybór odpowiedniego backupu do odzyskania danych.
3.  **Odzyskiwanie danych:** Odzyskiwanie danych z backupu.
4.  **Testowanie:** Testowanie odzyskanych danych w celu upewnienia się, że są poprawne.

### Testowanie Backupów

Backupy są regularnie testowane, aby upewnić się, że są poprawne i można z nich odzyskać dane.

*   **Testy odzyskiwania:** Testy odzyskiwania danych są wykonywane raz w miesiącu. Testy odzyskiwania danych polegają na odzyskaniu danych z backupu i sprawdzeniu, czy są poprawne.
*   **Testy integralności:** Testy integralności backupów są wykonywane codziennie. Testy integralności backupów polegają na sprawdzeniu, czy backupy nie są uszkodzone.

### Technologie Backupu i Odzyskiwania Danych

System wykorzystuje następujące technologie do backupu i odzyskiwania danych:

*   **SQLite:** SQLite jest bazą danych, która jest łatwa w backupowaniu i odzyskiwaniu.
*   **Python:** Python jest używany do automatyzacji procesu backupu i odzyskiwania danych.
*   **Narzędzia chmurowe:** Narzędzia chmurowe (np. Amazon S3, Google Cloud Storage) są używane do przechowywania backupów w chmurze.

Dzięki tym mechanizmom system rezerwacji hotelowej jest w stanie chronić dane przed utratą i szybko je odzyskać w przypadku awarii.

## Zarządzanie Projektem

System rezerwacji hotelowej jest rozwijany z wykorzystaniem metodyk zwinnych, aby zapewnić elastyczność i szybkie dostarczanie wartości. Poniżej przedstawiono kluczowe aspekty zarządzania projektem:

### Narzędzia do Zarządzania Projektem

System wykorzystuje następujące narzędzia do zarządzania projektem:

*   **Jira:** Do śledzenia zadań, bugów i postępów projektu.
*   **Confluence:** Do dokumentowania wymagań, decyzji i postępów projektu.
*   **Slack:** Do komunikacji w zespole.
*   **GitHub:** Do zarządzania kodem źródłowym i współpracy nad kodem.

### Metodologie

System jest rozwijany z wykorzystaniem następujących metodologii:

*   **Agile:** Metodologia zwinna, która pozwala na szybkie dostarczanie wartości i elastyczne reagowanie na zmiany.
*   **Scrum:** Framework zwinny, który definiuje role, wydarzenia i artefakty.
*   **Sprinty:** Prace są organizowane w sprinty, które trwają 2 tygodnie.
*   **Codzienne spotkania:** Zespół spotyka się codziennie, aby omówić postępy i problemy.
*   **Przeglądy sprintów:** Na koniec każdego sprintu zespół prezentuje postępy i zbiera feedback.
*   **Retrospektywy:** Na koniec każdego sprintu zespół analizuje proces i szuka możliwości ulepszenia.

### Role w Zespole

W zespole projektowym są następujące role:

*   **Product Owner:** Odpowiedzialny za wizję produktu i backlog.
*   **Scrum Master:** Odpowiedzialny za proces Scrum i usuwanie przeszkód.
*   **Zespół Deweloperski:** Odpowiedzialny za implementację systemu.

### Harmonogram i Kamienie Milowe

Projekt jest podzielony na etapy, z których każdy ma określone kamienie milowe.

*   **Etap 1:** Analiza wymagań i projektowanie systemu.
*   **Etap 2:** Implementacja podstawowych funkcjonalności (logowanie, rejestracja, rezerwacja).
*   **Etap 3:** Implementacja zaawansowanych funkcjonalności (zarządzanie pokojami, synchronizacja cen).
*   **Etap 4:** Testowanie i wdrożenie systemu.
*   **Etap 5:** Utrzymanie i rozwój systemu.

### Plan Zarządzania Projektem

1.  **Planowanie sprintu:** Na początku każdego sprintu zespół planuje prace do wykonania.
2.  **Realizacja zadań:** Zespół realizuje zadania zgodnie z planem sprintu.
3.  **Codzienne spotkania:** Zespół spotyka się codziennie, aby omówić postępy i problemy.
4.  **Przegląd sprintu:** Na koniec każdego sprintu zespół prezentuje postępy i zbiera feedback.
5.  **Retrospektywa:** Na koniec każdego sprintu zespół analizuje proces i szuka możliwości ulepszenia.
6.  **Monitorowanie postępów:** Postępy projektu są monitorowane za pomocą Jira.
7.  **Komunikacja:** Zespół komunikuje się za pomocą Slack.

Dzięki tym mechanizmom system rezerwacji hotelowej jest rozwijany w sposób efektywny i elastyczny, zapewniając szybkie dostarczanie wartości i wysoką jakość produktu.

System rezerwacji hotelowej został zaprojektowany z myślą o skalowalności, aby sprostać rosnącemu obciążeniu i liczbie użytkowników. Poniżej przedstawiono kluczowe aspekty skalowalności systemu:

### Skalowanie Horyzontalne

System może być skalowany horyzontalnie poprzez dodawanie nowych serwerów aplikacji. Każdy serwer może obsługiwać część ruchu, co pozwala na rozłożenie obciążenia.

*   **Load Balancing:** Ruch jest rozdzielany między serwerami za pomocą load balancera. Load balancer monitoruje obciążenie serwerów i kieruje żądania do najmniej obciążonego serwera.
*   **Bezstanowość Aplikacji:** Aplikacja jest bezstanowa, co oznacza, że nie przechowuje żadnych danych sesji. Dzięki temu każde żądanie może być obsłużone przez dowolny serwer.

### Skalowanie Bazy Danych

Baza danych może być skalowana w celu obsługi większej liczby zapytań i danych.

*   **Replikacja:** Baza danych może być replikowana na wiele serwerów. Replikacja pozwala na odczytywanie danych z wielu serwerów, co zwiększa wydajność odczytu.
*   **Partycjonowanie:** Baza danych może być partycjonowana na wiele serwerów. Partycjonowanie pozwala na rozłożenie danych na wiele serwerów, co zwiększa wydajność zapisu i odczytu.

### Zarządzanie Obciążeniem

System wykorzystuje mechanizmy zarządzania obciążeniem, aby zapewnić stabilność i wydajność.

*   **Kolejki Zadań:** Zadania asynchroniczne, takie jak synchronizacja cen, są obsługiwane przez kolejki zadań (Celery). Kolejki zadań pozwalają na rozłożenie obciążenia i uniknięcie przeciążenia serwerów.
*   **Cache:** System wykorzystuje cache do przechowywania często używanych danych. Cache pozwala na zmniejszenie liczby zapytań do bazy danych, co zwiększa wydajność.

### Technologie Skalowalności

System wykorzystuje następujące technologie do zapewnienia skalowalności:

*   **Flask:** Flask jest lekkim frameworkiem, który pozwala na łatwe skalowanie aplikacji.
*   **Celery:** Celery jest biblioteką do zarządzania zadaniami asynchronicznymi, która pozwala na rozłożenie obciążenia.
*   **Redis:** Redis jest bazą danych typu klucz-wartość, która jest wykorzystywana jako broker wiadomości dla Celery i jako cache.
*   **Load Balancer:** Load balancer rozdziela ruch między serwerami aplikacji.

### Plan Skalowania

1.  **Monitorowanie:** Monitorowanie obciążenia systemu za pomocą narzędzi monitorujących (np. Prometheus, Grafana).
2.  **Analiza:** Analiza danych monitorowania w celu identyfikacji wąskich gardeł.
3.  **Skalowanie:** Skalowanie systemu poprzez dodawanie nowych serwerów aplikacji, replikację bazy danych lub partycjonowanie bazy danych.
4.  **Testowanie:** Testowanie systemu po skalowaniu w celu upewnienia się, że działa poprawnie.

Dzięki tym mechanizmom system rezerwacji hotelowej jest w stanie obsłużyć rosnącą liczbę użytkowników i obciążenie, zapewniając stabilność i wydajność.