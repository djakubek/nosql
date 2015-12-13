Zaliczenie
---------------------------------------------
Wykorzystany sprzet:

|X|Informacje o komputerze                             |
|-----------------------|------------------------------|
| Procesor              | Intel Core i7-3687U 2.60 GHz |
| Ilość rdzeni          | 2 fizyczne, 4 logiczne       |
| Pamięć                | 7,88 GB                      |
| Dysk                  | SSD PLEXTOR PX-128M6M 128 GB |
| System operacyjny     | Linux Ubuntu Gnome 14.04.3   |
| Typ systemu           | 64 - bit                     |
| Model komputera       | Ultrabook DELL XPS 14        |

|Użyte programy|Wersja|
|---------|-----------|
|Bunzip2  | 1.0.6     |
|Mongodb  | 3.0.7     |
|Postgres |           |


###Zadanie 2a - Mongodb
---------------------------------------------
Rozpakowywanie pliku RC_2015-01.bz2 (**rozmiar : 5,5 GB (5452413560 bajtów)**) wraz z importem do bazy danych Mongodb
```sh
time bunzip2 -c RC_2015-01.bz2 | mongoimport --drop --host 127.0.0.1 -d test -c reddit
```
Zużycie zasobów (procesora, RAM'u, Sieci, Dysku):

![zasoby import](zasoby_import.png)
![disk read](disk_read.png)

Czas poświęcony na wykonanie importu bazy danych do mongodb
![czas importu](czas_importu_mongodb.png)

Rozmiar plików po zaimportowaniu 53,7 GB

###Zadanie 2a - Postgres
-----------------------------------------------------------------

###Zadanie 2b - Mongodb
----------------------------------------------------------------
