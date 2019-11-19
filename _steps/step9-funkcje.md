---
layout: step
number: 9
title: Funkcje
permalink: step9/
---

Funkcje pozwalają nam na dzielenie jednej wielkiej listy zadań w naszym programie na kilka mniejszych list. To takie jakby pisanie małych programików w większym programie. W Pythonie często używamy pojęcia funkcji i metody zamiennie. (Python jest całkowicie obiektowy, dlatego, każda funkcja jest metodą, nie będziemy się dzisiaj jednak zajmować teorią).

W Pythonie istnieje wiele funkcji wbudowanych - gotowych do użytku, dostarczonych jako część języka. W czasie warsztatów poznaliśmy ich kilka.

Funkcje standardowego wejścia `input()` i wyjścia `print()`.

Funkcje związane z **konwersją (*rzutowaniem*) typów**:

- `int()`
- `float()`
- `str()`
- `bool()`

i inne, którym nie zawsze poświęcamy dość uwagi:

- `type()`
- `len()`
- `range()`

```python
spell = 'Abrakadabra'
len(spell) # uzycie funkcji wbudowanej
print(spell.upper()) # uzycie metody na zmiennej typu string
```

## Funkcje

Możemy też pisać własne funkcje w Pythonie. Dzielenie całego kodu na funkcje sprawia, że zamiast jednego wielkiego programu mamy wiele małych programików. Ale co tak właściwie nam to daje?

1. Małe kawałki kodu łatwiej się pisze.
2. Małe kawałki kodu są łatwiejsze do przeczytania i zrozumienia.
3. Oszczędzamy czas, bo jednej funkcji możemy użyć w kilku miejscach (zasada **DRY** - *don't repeat yourself*)

A więc, pobawmy się funkcjami tworząc kolejny plik.

Czego się przy okazji nauczymy?

- **deklarowania** funkcji,
- **wywoływania** funkcji,
- **parametrów** i **argumentów** funkcji,
- **wartości zwracanych** przez funkcje.

Bierzmy się do roboty!

## Tworzymy funkcje 
Stwórz nowy plik z następującym kodem

```python
def say_hello():
    print('Hej!')
    print('Jak się masz?')

say_hello()
```
Spójrz jak zbudowana jest nasza funkcja:

1. Definicja metody: słowo kluczowe `def`, nazwa metody `say_hello`, oraz nawiasy okrągłe `()`.

2. Ciało funkcji, które zawiera listę zadań do wykonania


Poza funkcją, w głównej części programu mamy wywołanie funkcji `say_hello()`.

Dzięki temu, że funkcja jest "nad" główną częścią programu, a więc jest zdefiniowana poza główną częścią programu, możemy ją wywołać wielokrotnie:


```python
def say_hello():
    print('Hej!')
    print('Jak się masz?')

say_hello()
print('- Dzień dobry, całkiem w porządku')
say_hello()
print('- Cześć! Super!')
say_hello()
print('- No siema, ale weź już skończ')
```

### Przesłanie argumentu do funkcji
Bywa tak, że chcemy by nasza funkcja wykonywała bardziej skonkretyzowane zadania. Chcemy by dostała jakieś dane i je wykorzystała. Dlatego *funkcje przyjmują argumenty*.

```python
def say_hello(name):
    print('Hej', name)
    print('Jak się masz?')

say_hello("Anna")
```
Pewnie już widzisz, że wywoływanie funkcji jest naprawdę proste - po prostu podajesz nazwę funkcji, a za nią wpisujesz nawiasy okrągłe. Jeżeli chcesz przekazać do funkcji jakieś argumenty, wpisz je w tych nawiasach.

Nazwa argumentu to zmienna jakiej będziemy używać tylko w obrębie danej funkcji.
Dlatego nie możesz sprawdzić co zawiera zmienna `name` poza ciałem funkcji.

```python
def say_hello(name):
    print('Hej', name)
    print('Jak się masz?')

say_hello("Anna")
print(name) # !!! błąd
```

Zobacz jak możemy wielokrotnie wysłać imię do funkcji:


```python
def say_hello(name):
    print('Hej', name)
    print('Jak się masz?')

name1 = input('Podaj swoje imię: ')
say_hello(name1)
print('- Cześć!')

name2 = input('Podaj swoje imię: ')
say_hello(name2)
print('- Cześć!')

name3 = input('Podaj swoje imię: ')
say_hello(name3)
print('- Cześć!')
```

Widzisz, powtarzenie czynności? Chyba czas użyć pętlę!

```python
def say_hello(name):
    print('Hej', name)
    print('Jak się masz?')


for _ in range(3):
  user_name = input('Podaj swoje imię: ')
  say_hello(user_name) #wywołaliśmy funkcję wewnątrz pętli
  print('- Cześć!')

```

Jeszcze inna, mała, przykładowa funkcja:

```python
def my_mood(answer):
    print("Czuję się: ", answer)

user_mood = input("Jak się czujesz?")
my_mood(user_mood)
```
### Return

Zaczniemy od kodu porównamy kod funkcji, która **wyświetla** odpowiedź, z kodem funkcji, która **zwraca** odpowiedź. 

Co to oznacza?

```python
def say_hello(name):
    print('Witaj ' + name + '!') #wyświetla powitanie

girls = ['Ada', 'Julia', 'Ruby']
for g in girls:
    say_hello(g)
    print('🎈')
```

```python
def say_hello(name):
    welcome = 'Witaj ' + name + '!'
    return welcome # zwraca string z powitaniem 

girls = ['Ada', 'Julia', 'Ruby']
for g in girls:
    message = say_hello(g) # zapisujemy napis zwrócony przez funkcję
    print(message) # wyświetlamy napis
    print('🎈')
```

**Zapamiętaj:** `return` przerywa działanie funkcji i zwraca wartość z powrotem do miejsca, gdzie została wywołana funkcja.

#### Zadanie 1

Utwórz funkcję, która przyjmuje argument - liczbę punktów ze sprawdzianu na 50 i oblicza procentowy wynik. Poproś kilku użytkowników o podanie ich wyniku. Wyświetl im ile procent uzyskali ze sprawdzianu

```python
def test_result(points):
  return round(points/50, 2) # metoda round zaokrągla wynik


students = input(input("Podaj liczbę studentów: "))

for s in range(students):
  student_points = int(input("Podaj wynik punktowy ze egzaminu: "))
  result_proc = test_result(student_points)
  print(f"Student {s+1}, uzyskał wynik: {result_proc} %")
```
{: .solution }


#### Zadanie 2

Rozszerz zadanie 1 o wyświetlenie oceny na podstawie skali ocen:

- powyżej 90% - 5 (bdb) 
- powyżej 70% - 4 (db)
- powyżej 50% - 3 (dost)
- powyżej 30% - 2 (dop)
- 30% i mniej - 1 (ndst)

```python
def test_result(points):
  result = round(points/50, 2) 
  if result > 90:
    return "bdb"
  elif result > 70:
    return "db"
  elif result > 50:
    return "dost"
  elif result > 30:
    return "dop"
  else: 
    return "ndst"


students = input(input("Podaj liczbę studentów: "))

for s in range(students):
  student_points = int(input("Podaj wynik punktowy ze egzaminu: "))
  grade = test_result(student_points)
  print(f"Student {s+1}, uzyskał ocenę: {grade}")
```
{: .solution }

To już koniec nowych Pythonowych tematów, ale nie koniec naszego warsztatowego materiału. Możesz się sprawdzić, wykonując dodatkowe zadania!
