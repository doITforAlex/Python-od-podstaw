---
layout: step
number: 2
title: Interpreter Pythona
permalink: step2/
---

W tej części rozpoczniemy zabawę z Pythonem, na razie w trybie interaktywnym czyli w konsolowym interpreterze.

Otwórz interpreter Pythona w wierszu poleceń na swoim komputerze.
Wpisz komendę `python`:


```
$ python
Python 3.7.2 (...)
Type "help", "copyright", "credits" or "license" for more information.
>>>
```


Wcześniej pracowaliśmy w linii poleceń `/` konsoli systemu operacyjnego i mogliśmy wydawać polecenia. Znak zachęty był oznaczany jako `~ $` lub `>`. Po uruchomieniu polecenia python zachęta zmieniła się na `>>>`. Dla nas oznacza to, że w tym możemy używać tylko poleceń z języka Python.

## Pierwszy kod w Pythonie

```
Python 3.7.2 (...)
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello World")
Hello World
```

Zastosowane polecenie *print()* to funkcja, która służy w Pythonie do wyświetlania tekstu (w konsoli)

## Python jako kalkulator

**Operacje arytmetyczne** pozwalają nam na wykonywanie na danych działań matematycznych, takich jak dodawanie, odejmowanie, dzielenie, itd.

**Operatory** to z kolei symbole, których używamy do przeprowadzania tych operacji, takie jak `+`, `-`, `=`, itd.

**Wyrażeniem** jest łączenie kilku danych i przeprowadzanie na nich działań matematycznych, by dostać nową wartość.

To wszystko jest nam znane od podstawówki, każda i każdy z nas potrafi wykonać podstawowe operacje matematyczne, ale czy potrafi je też Python?

## Operacje arytmetyczne

Wpisz w konsoli liczbę `205` i wciśnij enter.

Jak widzisz, liczba `205` została wyświetlona po raz kolejny. To konsola wykonuje działanie na liczbie, którą w niej wpisujesz i wyświetla wynik. Tak więc, jeżeli wpiszesz w niej po prostu pojedynczą liczbę, to właśnie ta liczba jest wynikiem działania, bo nie wykonujesz na niej żadnych operacji.

Spróbujmy teraz `205 + 103`

W konsoli wyświetliła się liczba `308`. W tym wyrażeniu przeprowadziliśmy operację arytmetyczną z użyciem operatora `+`, czyli dodawania.

Głównymi operatorami matematycznymi są:

- `+`: dodawanie
- `-`: odejmowanie
- `*`: mnożenie
- `/`: dzielenie
- `%`: modulo, czyli reszta z dzielenia

I tak samo jak w matematyce, stosujemy tu **kolejność wykonywania działań** i możemy używać nawiasów `(` i `)`.

I tak, na przykład:

- `100+50*2` to `200`, ale
- `(100+50)*2` to `300`.

A teraz pobaw się trochę - powpisuj różne wartości w konsoli i zobacz, jakie dostaniesz wyniki.

**Operator modulo**

Takiego operatora w szkole nie było, spójrzmy jak zachowuje się modulo:

```
>>>  print(5 % 2)
>>>  print(5 % 3)
>>>  print(5 % 4)
```

#### Zadania

Użyj Pythona, aby obliczyć
1. Ile godzin ma rok?
2. Ile sekund ma dekada?
3. Ile skrzydeł ma dwanaście tuzinów ważek?

### Ciekawostka: o co chodzi z `*` i `/`?

Dlaczego używamy `*` i `/` zamiast zwykłych symboli mnożenia i dzielenia?

Pierwsze klawiatury komputerowe były wzorowane na mechanicznych maszynach do pisania.

Osoby, które korzystały z takich maszyn nie potrzebowały ani symbolu mnożenia (bo mogły po prostu używać znaku `x`), ani symbolu dzielenia (bo mogły wpisać po prostu `-` i potem nadpisać na nim `:`, albo po prostu użyć samego znaku `:`). Ułamki z kolei zapisywano jako `1/2` czy `3/4`.

(Co prawda, maszyny z wyższej półki miewały specjalne klawisze z symbolami mnożenia i dzielenia, ale jakoś nigdy się to nie przyjęło).

Tak więc kiedy zaczęliśmy używać klawiatur komputerowych, "odziedziczyliśmy" to ograniczenie i wymyśliliśmy sposób, żeby je obejść - do ułamków i dzielenia używając znaku `/`, a do mnożenia `*`.

### Typy danych

Jak widzisz, wszystkie dane, na których do tej pory pracowaliśmy, to liczby. Ale co, jeżeli chcesz użyć czyjegoś imienia? Jak to zrobić?

Przyjrzyj się kodowi, który już napisaliśmy. W jaki sposób napisaliśmy wiadomość, która wyświetliła się po naciśnięciu przycisku?

### Operatory logiczne

Czy Python poradzi sobie z operacjami porównania? 

- `==`:    równa się 
- `!=`:    nie równa się
- `>`:    większe od
- `<`:    mniejsze od
- `>=`:    większe lub równe
- `<=`:    mniejsze lub równe

Od razu przetestujmy: 

```
>>>  print(5 == 4)     
>>>  print(5 != 4)     
>>>  print(5 > 2)    
>>>  print(5 < 3)    
>>>  print(3 >= 4)     
>>>  print(3 <= 4)     
>>>  print(False < True)
```

#### Zadania
Sprawdź w konsoli:

1. Czy 23 + 3 będzie się równać 15  + 12 ?
2. Czy dzielenie 29 przez 7 bez reszty wynosi 5?
3. Czy 27 podzielone przez 8 daje resztę 3?

