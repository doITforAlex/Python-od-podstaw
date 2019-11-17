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

```
>>> print('Cześć', name, 'jak się masz?')
```

Zmienna name została wyświetlona, i ma taką zawartość jak została podana przez `input()`

Możemy to zapisać krócej:

```
>>> age = input('Ile masz lat?')

>>> print('To już', age, 'lat!')
```

Funkcja [input() - dokumentacja](https://docs.python.org/3/library/functions.html#input)

