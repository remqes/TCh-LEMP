<h2>Laboratorium programowania aplikacji w chmurach obliczeniowych.</h2>

###P9.2. Na poprzednich laboratoriach budowane były obrazy kontenerów z serwerem Apache, PHP.  W tym zadaniu należy zbudować prosty plik docker-compose.yml, który pozwoli na uruchomienie  znanej z innych zajęć, usługi LEMP wraz z phpMyAdmin. Stack LEMP składa się z następujących  usług składowych: 
- L - dla Linux;
- E - dla Nginx;
- M - dla MySQL;
- P - dla PHP;

Wobec tego projekt powinien zawierać cztery kontenery (usługi):
- jeden kontener dla Nginx, 
- jeden kontener dla PHP (PHP-FPM),
- jeden kontener dla MySQL, 
- jeden kontener dla phpMyAdmin. 

<h3>Założenia dla usługi:</h3>
- serwery są budowane zgodnie z dokumentacją obrazów bazowych dostępnych na DockerHub i umieszczonych tam plików Dockerfile (zbudowanie własnych obrazów a nie wykorzystanie z gotowych obrazów będzie wyżej oceniane).
- serwery PHP, MySQL, phpMyAdmin są przyłączone do sieci backend a Nginx do backend oraz frontend. Nginx ma wystawiony na świat zewnętrzy port 6666,
- serwer Nginx ma wyświetlać stronę startową php (index.php),
- serwer phpMyAdmin ma być dostępny na porcie 6001 i powinno być możliwe zalogowanie się do niego i założenie testowej bazy. 

Zbudowanie obrazów kontenerów za pomocą pliku docker-compose.yml. 
![docker-compose-up](/images/docker-compose-up.PNG)

Utworzenie bazy danych w kontenerze.
![docker-exec](/images/docker-exec.PNG)

Działanie usługi phpmyadmin oraz usługi nginx, która wyświetla zawartośc strony index.php.
![phpmyadmin](/images/phpmyadmin.PNG)
![nginx](/images/nginxphp.PNG)

Wygenerowanie reprezentacji graficznej dla pliku docker-compose.yml
![docker-compose-image-gen](/images/docker-image.PNG)
![docker-compose-image-view](/images/docker-image-view.PNG)