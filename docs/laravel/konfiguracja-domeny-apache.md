---
title: "Laravel - Konfiguracja domeny dla Apache"
---

## Włączenie wymaganych modułów dla Apache
- `sudo a2enmod rewrite`
- `sudo systemctl restart apache2.service`

## Dodawanie nowej konfiguracji
- przykład:
  - projekt laravel jest w folderze */var/www/test*
  - chcemy skonfigurować domenę *test.local*

- w katalogu: */etc/apache2/sites-available* tworzymy nowy plik o nazwie odpowiadającej naszej domenie: `sudo nano test.conf`
- wklejamy zawartość pliku:
  ```
  <VirtualHost *:80>
          ServerName test.local
          ServerAlias www.test.local
          DocumentRoot /var/www/test/public
      <Directory /var/www/test>
          Options Indexes FollowSymLinks
          AllowOverride All
          Require all granted
      </Directory>

      ErrorLog ${APACHE_LOG_DIR}/error.log
      CustomLog ${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>

  ```
  - *ServerName* to podstawowa nazwa domeny/adres URL pod którym strona będzie dostępna w przeglądarce
  - *DocumentRoot* ma wskazywać na folder publiczny projektu laravel
  - w *<Directory* podajemy główną ścieżkę do projektu laravel
- aktywujemy plik konfiguracyjny: `sudo a2ensite test.conf`
- `sudo systemctl restart apache2`
- otwieramy plik hosts `sudo nano /etc/hosts`
- pod obecnymi wpisami, dodajemy:
  ```
  127.0.0.1       test.local
  ```
- wpisujemy w przeglądarce adres *test.local*
- w przypadku problemów pliki błędów apache znajdują się w katalogu */var/log/apache2*
- alternatywy: [Laravel Homestead](https://laravel.com/docs/11.x/homestead)