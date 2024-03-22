---
title: "Laravel - Roadmap"
---


# Junior


## PSR
- Co to jest i dlaczego jest stosowany


## Nazewnictwo
![nazewnictwo.jpg](./../assets/images/laravel_naming_convictions.png)


## Routing
- [DOC](https://laravel.com/docs/11.x/routing)
- Nazewnictwo
- Parametry
- Grupowanie
- Prefix
- Resource
- Metody (GET, Post, PUT, DELETE)


## Kontrolery
- [DOC](https://laravel.com/docs/11.x/controllers)
- Zwracanie widoku
  - z danymi
- zwracanie danych
  - [Statusy HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- Redirect
- [Walidacja danych](https://laravel.com/docs/11.x/validation)
  - W kontrolerze a osobnych plikach
  - Tablicy i zawartych w niej danych
  - Unique oraz Exists
    -  jak zwalidować email użytkownika, kiedy edytuje dane a email jest unikatowy i taki sam jak w bazie (chcemy to przepuścić)
    -  jak sprawdzić na etapie walidacji czy podany np. mail usera istnieje w bazie i jest
unikatowy
- Struktura Try/Catch
  -  wydzielenie kodu do serwisów (serwis to osobny plik np. ArticleService który zawiera klasę o takiej nazwie, odpowiada za wyjęcie funkcjonalności z kontrolera, tak żeby struktura kontrolera została jak najbardziej pomniejszona i wywoływała głównie funkcje serwisu bądź zwracała ich errory poprzez catch)


## Database
- [DOC](https://laravel.com/docs/11.x/migrations)
- Migracje
- Nazewnictwo migracji/tabel
- Nullable/required/default
- Relacje
  - nazewnictwo kluczy obcych i z czym się to wiąże
  - jak tworzymy relacje wiele do wielu (jakie nazwy przyjmuje wtedy tabela i klucze obce)
- Edytowanie migracji
  - dodawanie, kasowanie, edytowanie istniejacych kolumn bądź tabeli


## Modele
- [DOC](https://laravel.com/docs/11.x/eloquent%23eloquent-model-conventions)
- Czym jest model, jaką pełni funkcję i jak koresponduje z baza danych/migracją
- Nazewnictwo
- Relacje
  - Jakie wyróżniamy i jak zapiszemy hasManyThrough - wiele do wielu
- Fillable / hidden / ...
- Eloquent (create, update, delete, ...)
- Paginacja
- Resource (co to jest i czemu je używamy)
- Atrybuty
- Castowanie danych
- Traity
- Scope globalne i lokalne


## Seedy
- [DOC](https://laravel.com/docs/11.x/seeding)
- Nazewnictwo
- Wywoływanie konkretnego / wszystkich na raz
- Faker


## Tinker
- [DOC](https://laravel.com/docs/11.x/artisan#tinker)
- Co to jest i kiedy używamy


## Env / Config
- [DOC](https://laravel.com/docs/11.x/configuration#environment-configuration)


## Middleware
- [DOC](https://laravel.com/docs/11.x/middleware)
- Wywoływane / aplikowane do każdego routa web/api
- Wyciąganie danych requesta / routa w middleware


## Guardy
- Dodawanie nowego np: admin


## Auth
- [DOC](https://laravel.com/docs/11.x/authentication)
- Tworzenie i kasowanie sesji
- Wyciąganie danych użytkownika
- Api


## Blade
- [DOC](https://laravel.com/docs/11.x/blade)
- Wyciąganie danych zwracanych z kontrolera
- [Poznanie @if, @foreach, ...](https://laravel.com/docs/5.3/blade#if-statements)
- Formularze
  - Wysyłanie danych
  - CSRF token
    - [DOC](https://laravel.com/docs/11.x/csrf)
    - Co to jest, czemu i jak dodajemy do formularza
  - Czym różni się metoda GET od POST oraz kiedy używamy POST a PUT
  - Dzielenie blady na komponenty (@include, @section, ...)


## Maile
- [DOC](https://laravel.com/docs/11.x/mail)
- Tworzenie i wysyłanie maili
- Konfiguracja maila w .env


## API
- Róznica między web a api
- Jak wygląda struktura zwracanych danych
- Czym różnią się routy


## Tłumaczenia
- [DOC](https://laravel.com/docs/11.x/localization)
- używanie tłumaczeń w widokach oraz kontrolerach
- Bazowo mamy podstawowe tłumaczenia en, jak dodać np. pl ?
- zmiana aktualnego języka aplikacji
  - przez parametr w roucie
  -  przez daną locale w body zapytania (co projekt to inne podejście, sprawdź obie metody)
- w przypadku kiedy zwracamy dane kontrolera, jak zwrócisz przetłumaczony status? (np. Article created successfully! – Pomyślnie utworzono artykuł!)
-  jak dodać nowe tłumaczenia walidacji i je parametryzować


## Pliki
- [DOC](https://laravel.com/docs/11.x/filesystem)
- w laravelu bazowo pliki zapisywane są w folderze storage, skąd mamy do wyboru by były
publiczne bądź prywatne (zwracane przez funkcje kontrolera)
- jak zapisywać, podmieniać, usuwać oraz zwracać plik
- co to `storage-link` i co nam zapewnia
- jak wrzucić plik do `storage`, tak by był dostępny z folderu `public`


## PHP
- data types
- control structures
- function
- class / interface
- extending / implementation
- typo-hint
- exception
- namespace
- traits


## GIT
- [DOC](https://git-scm.com/docs)
- podstawowe komendy: `init`, `push`, `pull`, `checkout`, `merge`, `rebase`


## Composer
- [DOC](https://getcomposer.org/doc/01-basic-usage.md)
- podstawowe komendy: `require`, `install`, `update`, `remove`
- wersjonowanie paczek
- autoload


[Dodatkowe informacje](https://github.com/LaravelDaily/Laravel-Roadmap-Learning-Path)