---
title: "Ubuntu - Instalacja"
---


# Instalacja apache

- `sudo apt update`
- `sudo apt install apache2`

# Instalacja mariadb

- `sudo apt update`
- `sudo apt install mariadb-server`
- odpowiedzi do pytań:
	- `Switch to unix_socket authentication [Y/n]` **n**
	- `Change the root password? [Y/n]` **y**
	- jako hasło wpiszcie i potwierdźcie np. **123**
	- `Remove anonymous users? [Y/n]` **y**
	- `Disallow root login remotely? [Y/n]` **y**
	- `Remove test database and access to it? [Y/n]` **y**
	- `Reload privilege tables now? [Y/n]` **y**
- `sudo mysql_secure_installation`

# Instalacja phpmyadmin

- `sudo apt install libapache2-mod-php`
- `sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl`
- `sudo ln -s /etc/phpmyadmin/apache.conf` 
- `sudo ln -s /etc/apache2/conf-available/phpmyadmin.conf`
- `sudo a2enconf phpmyadmin.conf`
- `sudo systemctl restart apache2`
- dodatkowe komendy jeśli phpmyadmin się nie zainstaluje:
	- `sudo dpkg-reconfigure phpmyadmin – spacją zaznacz apache`
- lub
	- `sudo apt update`
	- `sudo apt upgrade`	
	- `sudo apt install apache2 php php-mysql`
	- `sudo apt install phpmyadmin`
	- uruchom apache wpisz w przegladarce: http://localhost/phpmyadmin powinno się 	pojawić okno z bazami danych 
- jeśli apache nie wykryje żadnego php, błąd dla phpmyadmin:
	- `sudo a2enmod php[version]` - zamiast **[version]** podajcie waszą obecną wersję php
	- `systemctl restart apache2.service`
	- wejdźcie na http://localhost/phpmyadmin i sprawdźcie czy zaczęło działać

# Node i composer (alternatywa nvm do node i npm)

- `sudo apt install nodejs`
- `sudo apt install php-cli unzip composer`
- `sudo apt-get install composer`
- `sudo apt install npm`
- `sudo apt-get update`
- `sudo apt-get install curl`
- alternatywa nvm: https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating

# Docker + trzeba dodać do grupy docker

- `curl -fsSL https://get.docker.com/ | sh`
- `sudo docker run hello-world`
- `sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/`
- `local/bin/docker-compose`
- `sudo chmod +x /usr/local/bin/docker-compose`


