---
layout: step
number: 5
title: Dane użytkownika
permalink: step5/
---

Do tej pory pisaliśmy kod, w którym wszystkie dane do zmiennych podawaliśmy samodzielnie. Zmienna `name` od razu dostawała wartość (np. przez `name = "Rita"`), co gdybyśmy chcieli tę zmienną zaktualizować o imię nowego użytkownika?

### input()

Potrzebujemy poznać kolejną funkcję wbudowaną input()

```
>>> print('Tu wpisz swoje imię: ')
>>> name = input()

```

Teraz konsola czeka na nasze działanie, aż wpiszemy ciąg znaków z klawiatury - nasze imię.
Kiedy je wpiszemy imię zostanie zapisane do zmiennej `name`.

Wyświetlmy je:


```
>>> print('Cześć', name, 'jak się masz?')
```

Zmienna name została wyświetlona, i ma taką zawartość jak została podana przez `input()`

Możemy to samo zapisać krócej, niech funkcja input od razu wyświetli pytanie:

```
>>> age = input('Ile masz lat?')

>>> print('To już', age, 'lat!')
```

Funkcja [input() - dokumentacja](https://docs.python.org/3/library/functions.html#input)

#### Zadania

1. Przypisz swoje imię do zmiennej o nazwie `my_name`.
2. Następnie przypisz swoje nazwisko do `my_surname`.
3. Połącz te dwa ciągi znaków w jeden.
4. Poproś użytkownika o imię oraz wiek, a następnie spraw by na ekranie pojawiło się przywitanie oraz informacja jak jest różnica wieku między Wami.


Sprawdź jeszcze:
```
>>> number = input("Wpisz tu 3: ")

>>> print(3 == number)
>>> type(3)
>>> type(number)
```

Number zostało odczytane jako string. Stąd:

```
>>> number = int(number)
>>> print(3 == number)
```

Zakończ pracę w trybie interaktywnym za pomocą komendy `exit()`.

Znowu jesteśmy w systemowym wierszu poleceń / terminalu.

Teraz przejdziemy do pracy w pliku - w naszym edytorze kodu.
