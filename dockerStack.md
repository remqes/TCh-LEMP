<h2>Laboratorium programowania aplikacji w chmurach obliczeniowych.</h2>

### P10.2. Na poprzednim laboratorium opracowany był plik docker-compose.yml opisujący usługę LEMP. Bazując na tym rozwiązaniu (przy tych samych założeniach co do funkcjonalności) należy:

1. Opracować plik [docker-stack.yml](https://github.com/remqes/TCh-LEMP/blob/main/docker-stack.yml) pozwalający na wdrożenie usługi w klastrze Swarm.

2. Plik musi posiadać deklarację dotyczące polityki restartu mikrousług oraz ich lokalizacji na węzłach (jeśli to niezbędne). Ustawienia tych parametrów muszą być uzasadnione w sprawozdaniu.

`restart-policy:
   condition: on-failure`
 
 Dana deklaracja powoduje ponowne uruchomienie kontenera w przypadku, kiedy praca kontenera zostanie zakończona z powodu błędu. Docker rekomenduje stosowanie politykę restartu mikrousług, ponieważ wtedy kontenery są uruchamiane we właściwej kolejności.

3. Plik powinien zawierać deklarację ilości replik. Proszę w sprawozdaniu uzasadnić, które z mikrousług warto brać pod uwagę przy decyzjach o skalowaniu a które skalowane być nie mogą.

`replicas: 1`

Mikrousługi, które nie muszą być skalowane, aby aplikacja działała prawidłowo to serwery bazy danych, aplikacje do monitorowania oraz usługi backendowe, natomiast skalowane mogą być usługi frontendowe.

Uruchomienie usługi w klastrze Swarm.
![docker-deploy](/images/images/docker10-deploy.PNG)

Poprawność działania dla poszczególnych mikrousług.
![docker-nginx](/images/docker10-nginx.PNG)
![docker-services](/images/docker10-services.PNG)
![docker-db](/images/docker10-phpmyadmin.PNG)

Widok aplikacji monitorowania zasobów w klastrze:
![docker-visualizer](/images/docker10-visualizer.PNG)
