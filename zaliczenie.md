Zaliczenie
---------------------------------------------
Wykorzystany sprzet:

|X|Informacje o komputerze                             |
|-----------------------|------------------------------|
| Procesor              | Intel Core i7-3687U 2.60 GHz |
| Ilość rdzeni          | 4                            |
| Pamięć                | 7,88 GB                      |
| Dysk                  | SSD 128 GB                   |
| System operacyjny     | Linux Ubuntu Gnome 14.04.3   |
| Typ systemu           | 64 - bit                     |
| Model komputera       | Ultrabook DELL XPS 14        |

|Użyte programy|Wersja|
|---------|-----------|
|Mongodb  | 3.0.7     |
|Postgres |           |
--------------------------------------------

###Zadanie 2a
Rozpakowywanie pliku RC_2015-01.bz2 wraz z importem do bazy danych Mongodb
```sh
time bunzip2 -c RC_2015-01.bz2 | mongoimport --drop --host 127.0.0.1 -d test -c reddit
```
Zużycie zasobów:
