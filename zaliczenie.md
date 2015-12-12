Zaliczenie
---------------------------------------------
Wykorzystany sprzet:

|X|Informacje o komputerze                             |
|-----------------------|------------------------------|
| Procesor              | Intel Core i7-3687U 2.60 GHz |
| Pamięć                | 7,88 GB                      |
| Dysk                  | SSD 128 GB                   |
| System operacyjny     | Linux Ubuntu Gnome 14.04.3   |
| Typ systemu           | 64 - bit                     |
| Model komputera       | Ultrabook DELL XPS 14        |

|Użyte programy|Wersja|
|---------|-----------|
|Mongodb  |           |
|Postgres |           |
--------------------------------------------

###Zadanie 2a
Import pliku bazy danych do bazy Mongodb
```sh
time bunzip2 -c RC_2015-01.bz2 | mongoimport --drop --host 127.0.0.1 -d test -c reddit
```
