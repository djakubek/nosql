Zaliczenie    Autor: Daniel Jakubek
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

| Użyte programy        | Wersja                       |
|-----------------------|------------------------------|
| Bunzip2               | 1.0.6                        |
| Mongodb               | 3.0.7                        |
| Postgres              | 9.3.10                       |
| Iotop (program do monitorowania aktywności dyskowej                 | 0.6-1|
| Pgfutter              |


###Zadanie 2a - Mongodb 3.0.7
---------------------------------------------
Rozpakowywanie pliku RC_2015-01.bz2 (**rozmiar : 5,5 GB (5452413560 bajtów)**) wraz z importem do bazy danych
```sh
time bunzip2 -c RC_2015-01.bz2 | mongoimport --drop --host 127.0.0.1 -d test -c reddit
```
Zużycie zasobów (procesora, RAM'u, Sieci, Dysku):

![zasoby import](zasoby_import.png)

Odczyty/zapisy dysku Iotop

![disk read](disk_read.png)

Czas poświęcony na wykonanie importu bazy danych
![czas importu](czas_importu_mongodb.png)

Rozmiar plików bazy danych po zaimportowaniu 53,7 GB

**Czas:** 43 min 68 sek


###Zadanie 2b - Mongodb
----------------------------------------------------------------
Zliczenie zainportowanych rekordów

```sh
db.reddit.count()
```
**Iość zaimportowanych dokumentów:** 53 851 542

**Czas:** Natychmiast

###Zadanie 2c - Mongodb

**Zliczenie czterech autorów najwyżej ocenionych komentarzy**
```sh
db.reddit.find({},{_id:0, subreddit:1,author:1, score:true}).sort({score:-1}).limit(4)
```

**Wyniki**
```sh
{
  "subreddit": "AskReddit",
  "score": 6597,
  "author": "a1988eli"
}
{
  "subreddit": "tifu",
  "author": "GingaSnapzzz",
  "score": 6448
}
{
  "score": 6105,
  "author": "MAY01337",
  "subreddit": "tifu"
}
{
  "subreddit": "AskReddit",
  "score": 5835,
  "author": "rugtoad"
}
Fetched 4 record(s) in 187727ms
```
**Czas:** 3 minuty 12 sek

**Zliczenie wszystkich komentarzy dotyczących tematu BMW**

```sh
db.reddit.find({subreddit:"BMW"}).count()
```

**Wynik:** 11700 Myślałem ze więcej :)

**Czas:** 2 min 58 sek


Zanalezienie wszystkich komentarzy, których autorzy już nie istnieją
```sh
db.reddit.find({author: "[deleted]"}).count()
```

**Wynik przeszukiwania:**3 917 360 (Całkiem sporo)

![diskreaddbfind](disk_read_dbfind.png)

![diskreaddbzasob](zasoby_dbfind.png)

We wszystkich przypadkach komputer zachowywał się podobnie i wykazywał większe obciązenie dysku niż pozostałych zasobów. **Wniosek:** By przyspieszyć działanie wyszukwania, warto zaopatrzyć się w bardzo szybką macierz dyskową.

###Zadanie 2c - Mongodb
-----------------------------------------------------------------

[Mapka](map.geojson) LineString przedstawiająca dojaz na studia źródło [geojson.io](http://www.geojson.io)




##POSTGRES W przygotowaniu
Okazalo sie ze mam za mało miejsca na dysku 

###Zadanie 2a - Postgres 9.3.10
-----------------------------------------------------------------
Rozpakowałem bazde RC_2015-01 programem bunzip,potem zaimportowałem do Postgresa za pomocą programu [Pgfutter](https://github.com/lukasmartinelli/pgfutter). Czas rozpakowywania **15 min**, czas importu **34 min 46 sek**
, całkowity czas **49 min 46 sek**.

![psqlm](psql_import.png)

![psqld](psql_importd.png)



###Zadanie 2b - Postgres
-----------------------------------------------------------------

###Zadanie 2c - Postgres
-----------------------------------------------------------------

