---
layout: step
number: 8
title: Petle
permalink: step8/
---

Często chcemy, by nasz kod wykonał się kilkukrotnie, nie wiedząc jednocześnie, ile dokładnie razy ma się powtórzyć.

Nasz problem rozwiązują wtedy **pętle**

## Pętla `for`

Pętla `for` służy do powtarzania kodu ograniczoną liczbę razy.

Stwórzmy nowy plik.

```python
easy_python = ["ABC", "It's easy as 1 2 3", "As simple as do re mi"]

for txt in easy_python:
    print(txt, len(txt))
```

Pętla wykona się dla każdego elementu naszej tablicy.

Pętla składa się z dwóch części:

1. Deklaracji pętli, `for txt in easy_python`. Deklaracja pętli określa po prostu, jak nasza pętla ma działać.

2. Ciała pętli, czyli kodu który ma się wykonać za każdym powtórzeniem pętli.

Deklaracja pętli składa się ze słowa kluczowego `for` i trzech kolejnych elementów.

1. Pierwszym elementem jest zmienna sterująca `txt`. Może mieć dowolną nazwę, jaką będziemy wykorzystywać w ciele pętli.
   Tworzymy zmienną `txt`, która będzie przechowywać informację o elemencie, który właśnie wykorzystujemy.

2. Drugim elementem jest warunek: `in`
   Warunek ten sprawdzany jest przez każdym wykonaniem pętli - jej ciało wykona się tylko wtedy, jeżeli nasz warunek jest prawdziwy - tzn bierzemy kolejny, niepusty element z listy (a jeżeli jest fałszywy, pętla się kończy, nie mamy więcej elementów w liście).

3. Trzecim wyrażeniem jest sekwencja elementów czyli lista: `easy_python`.


#### `range()`

Innym sposobem stworzenia pętli `for` jest zadanie ile razy ma wykonać się pętla. Funkcja range() - range(start, stop, krok) nie tworzy bezpośrednio listy, zamiast tego zwraca zakres liczb. Zawsze od start do stop(bez wartości stopu!).

```python
for i in range(5):  # i = 0, 1, 2, 3, 4 -> domyślnie od zera [0, 5) 
    print(i)

for i in range(10, 50, 10):  # i = 10, 20, 30, 40 -> [10, 50) co 10
    print(i)

```

Stwórzmy nowy przykład, w którym, na której podasz jaka wiadomość ma się wyświetlić - i ile razy ma to zrobić.

```python
user_message = input("Podaj wiadomość: ")
number = int(input("Podaj ile razy: "))

for i in range(number): 
    print(i, user_message)

```

Teraz nasza zmienna `i` porusza się (*iteruje*) po zakresie liczb. Staje się więc naszym licznikiem- ile razy wykonaliśmy polecenie w środku pętli.

To jeszcze jeden przykład na pętlę `for`. Utwórz plik `heroes.py`:

```python
heros = ["Knight"] * 3 + ["Killer"] + ["Wizard"] * 2
print(heros)  # lista -> ['Knight', 'Knight', 'Knight', 'Killer', 'Wizard', 'Wizard']

for h in heros:
    if(p == "Killer"):
        print("Found the killer!")
```

#### Zadanie 1

Utwórz pętlę, która wypisze liczby od 20 do 40 co drugą wartość

#### Zadanie 2

Zmodyfikuj kod `heroes.py` tak, aby listę bohaterów podawał użytkownik. Dodatkowo jeśli osoba `Killer` nie znajduje się na liście wypisz "There's no Killer".

```python
number_of_heros = int(input("Number of heros: "))

heros = []
for _ in range(number_of_heros):
  person = input("Personality type:  ")
  heros.append(person)

print(heros)  # ['Knight', 'Knight', 'Knight', 'Killer', 'Wizard', 'Wizard']

check_killer = False

for hero in heros:
    if(hero.lower() == "killer"):
        print("Found the killer!")
        check_killer = True

if check_killer == False:
  print("There's no Killer")
else:
  print("There's a Killer!")
```
{: .solution }


## Pętla `while`

Istnieje też inna pętla, pętla `while`.  W pętle `while` powtarzają pewne działanie określoną liczbę razy, aż do momentu spełnienia warunku albo tak długo jak warunek jest spełniony. 

Od razu przejdźmy do przykładu:

```python
price = 150

while (price > 100):
    print(price, "zł - za drogo")
    print("Poczekam aż będzie lepsza promocja")
    price = price - 20

print("Już poza pętlą")
print(price, "$ to super promocja!")
```

Pętla while również składa się z 2 części:

1. Deklaracji pętli `while (price > 100):`.

2. Ciała pętli oznaczonego wcięciem.

Jeśli się przyjrzymy jej konstrukcja jest bardzo prosta:

1. Słowo kluczowe `while` (*kiedy, dopóki*)

2. Warunek w nawiasach (nawiasy opcjonalne), jest sprawdzany po każdym wykonaniu, a pętla wykonuje się dopóki nasz warunek zwraca wartość `True`, na początku cena 150 jest większa od 100. W ciele pętli obniżamy cenę. Kiedy cena `price` przestanie być większa od 100, czyli zwróci wartość logiczną `False`, wyjdziemy z ciała pętli. 


Spójrzmy na kolejny przypadek. Teraz wykorzystamy moduł random. Pozwala on dodać do naszego kodu odrobinę losowości. Za pomocą metody `randrange()` będziemy losować liczby od 0 do 100. Składnia Pythona jest na tyle prosta, że nie musisz znać dosłownie każdej linijki, by zrozumieć ogół działania poniższego programu:


```python
import random

bird = "duck"
while bird != "pigeon":
    print("waiting...")
    if(random.randrange(0, 101) < 30):
        bird = "pigeon"

print("Hurray, I'm a pigeon!")
```

W poniższych zadaniach możesz użyć zarówno pętli `for` jak i `while`.


#### Zadanie 1

Pobierz od użytkownika tytuły kilku filmów. Poproś użytkownika o ich ocenienie. Wyświetl pary film i ocena.

```python
movie = input("Tytul filmu: ")
grade = input("Ocena filmu w skali 1-10: ")

print("Film pt. " + movie)
print("oceniasz na ", grade)
```

W razie potrzeby możesz podejrzeć rozwiązanie. Oczywiście, to tylko propozycja. Twój kod może wyglądać inaczej i również działać prawidłowo ;)


```python
number_of_movies = int(input("Podaj liczbę filmów do ocenienia"))

movies_list = []
grades_list = []

# ------- rozwiązanie for -------
for nr in range(number_of_movies):
    movie = input("Tytul filmu: ")
    grade = input("Ocena filmu w skali 1-10: ")
    movies_list.append(movie)
    grades_list.append(grade)
    
# ------ rozwiązanie while ------
i = 0
while (i < number_of_movies):
    i = i + 1
    movie = input("Tytul filmu: ")
    grade = input("Ocena filmu w skali 1-10: ")
    movies_list.append(movie)
    grades_list.append(grade)

for i in range(number_of_movies):
    print("Film pt.", movie, " : ", grade)
```
{: .solution }



#### Zadanie 2

Napisz program, który znajdzie wszystkie liczby, które są podzielne przez 7, ale nie są wielokrotnością 5, między 2000 a 3200 (obie wartości uwzględnione).


```python
for num in range(2000, 3201):
    if num % 7 == 0 and num % 5 != 0:
        print(num)
```
{: .solution }


Jeżeli ten etap mamy za sobą, to czas na kolejny krok naszej Pythonowej przygody!


