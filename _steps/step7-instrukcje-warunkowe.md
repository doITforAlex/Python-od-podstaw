---
layout: step
number: 7
title: Instrukcje warunkowe
permalink: step7/
---

Nie zawsze chcemy, żeby nasz kod za każdym razem wykonywał te same czynności - czasem powinien robić inne rzeczy, na przykład reagując na to, co na stronie wpisał użytkownik.

Ale jak możemy kontrolować, co robi nasz program?

Za pomocą **instrukcji warunkowych**.

Tutaj poznajemy wyrażenie `if`.

Spójrz na przykład poniżej - sprawdzamy, czy użytkownik podał swoje imię i jeżeli tego nie zrobił, ustawiamy odpowiednią treść wiadomości z błędem.

```python
name = input("Podaj swoje imię: ")

if name == '':
    print('Musisz podać swoje imię!')
```

`if` składa się z dwóch części:

- warunku (możesz sobie wyobrazić, że to pytanie, które zadajemy naszemu kodowi, na przykład _"Czy imię użytkownika to pusty string?"_),
- kodu **po WCIĘCIU** (4 spacje lub 1 tabulacja) zawierającego instrukcje, które mają się wykonać, jeżeli nasz warunek jest prawdziwy (czyli jeżeli odpowiedzią na nasze pytanie jest _"Tak"_).

Na końcu możesz dodać też `else`, który określa, jaki kod się wykona, jeżeli nasz warunek nie zostanie spełniony.

```python
name = input("Podaj swoje imię: ")

if name == '':
    print('Musisz podać swoje imię!')
else:
    print(f"Hello {name}, co u Ciebie?")
```

Warunki przyjmują wartość wyrażeń logicznych, czyli tzw. **booleanów**.
Boolean pojawiło się w rozdziale o typach. To takie wyrażenie, którego wartość zostaje oszacowana jako `True` (prawdziwa) lub `False` (fałszywa) dzięki użyciu **operatorów warunkowych**.

Operator warunkowy, którego użyliśmy w powyższym przykładzie to **operator równości**, czyli **A jest równe B**. Jeżeli wartości po jego obu stronach są uznawane za takie same, warunek uznawany jest za prawdziwy (przyjmuje wartość `True`). Jeżeli wartości po obu stronach są różne, warunek nie jest uznawany za prawdziwy i przyjmuje wartość `False`.

Oprócz else, możemy obsłużyć dodatkowy warunek, specjalne zachowanie. 

```python
name = input("Podaj swoje imię: ")

if name == '':
    print('Musisz podać swoje imię!')
elif name == 'Rita':
    print('Oh, to znowy ty!')
else:
    print(f"Hello {name}, co u Ciebie?")
```

**Ogólny wzór dla instrukcji warunkowej if wygląda o tak:**

Wcięcia mają znaczenie! Stosujemy 4 spacje albo 1 tabulację (i się tego trzymamy w całym pliku)

```python
if warunek:
   # zrób coś
elif warunek:
  # jeśli powyższe się nie spełniło, to zrób coś innego
else:
  # zrób coś jeśli żadne z powyższych się nie wykonało
```

```
x = int(input("Podaj liczbę"))
if(x < 0): # nawiasy są opcjonalne
    print("mniej niż zero") # wcięcia są obowiązkowe
elif(x == 0): # else if
    # ciekawostka, polecenia mogą zostać umieszczone w jednej linii
    # jeżeli rozdzielimy je średnikiem
    print("zerooooooo"); print("oooooooooo") 
else:
    print(x, "to więcej niż", 0)
    print("Nadal jestem w warunku else!")

print("A teraz jestem poza warunkiem")

```


## Operatory warunkowe

Szybka powtórka i rozszerzenie na potrzeby tworzenia warunków ;) 

| Operator | Nazwa/Opis                                                  |
| -------- | ----------------------------------------------------------- |
| `==`     | Równość. Obie strony mają te same wartości.                 |
| `is`     | Równość ścisła. Wartość i typ obu stron musi być taka sama. |
| `!=`     | Brak równości. Strony mają różne wartości.                  |
| `is not` | Brak równości ścisłej. Różne wartości ALBO różne typy.      |
| `<`      | Mniejszy niż.                                               |
| `>`      | Większy niż.                                                |
| `<=`     | Mniejszy lub równy.                                         |
| `>=`     | Większy lub równy.                                          |

Większość z nich mówi sama za siebie - z wyjątkiem ścisłej równości i jej braku. Wyjaśnijmy sobie krótko, o co z nimi chodzi.

Jeżeli porównywane wartości będą różnych typów, zwykłe porównania (`==` i `!=`) najpierw przekonwertują je do tego samego typu, a dopiero potem dokonają porównania. Przykładowo, `12 == 12.0` zwróci nam `True` (gdyż obie strony równania mają wartość liczbową 12), ale `12 is 12.0` zwraca `False`, ponieważ sprawdzana jest wartość jak i dokładnie ten sam typ.


## Operatory logiczne

Umiemy już radzić sobie z porównaniem dwóch rzeczy. Ale co jeżeli mamy dokonać oceny bardziej skomplikowanych warunków? Wtedy z pomocą przychodzą nam **operatory logiczne**.

Spotykać się będziesz głównie z trzema z nich: `and`, `or` i `not`

### Operator `and` (**koniunkcja**, `i`)

Używamy go, kiedy każdy z poszczególnych warunków wyrażenia musi być prawdziwy.

```python
if age >= 18 and drive_licence:
  print("Możesz prowadzić auto")
```

Używając operatora `and` możesz łączyć ze sobą tyle warunków, ile tylko zapragniesz. One następnie będą sprawdzane od lewej do prawej i jeżeli tylko jeden z nich będzie fałszywy (będzie miał wartość `False`), całe wyrażenie będzie fałszywe. W przeciwnym razie całe wyrażenie będzie prawdziwe (będzie miało wartość `True`).


```python
if age >= 18 and drive_licence and enough_money:
  print("Możesz kupić auto")
```

### Operator `or` (**alternatywa**, `albo`)

`||` to operator alternatywy - używamy go, kiedy tylko jeden z poszczególnych warunków wyrażenia musi być prawdziwy.

```python
if age >= 18 or parent_agree:
  print("Możesz brać udział w warsztatach")
```

Tak samo jak w przypadku operatora `and`, używając operatora `or` możesz łączyć ze sobą tyle warunków, ile chcesz. One również sprawdzane są od lewej do prawej - różnica polega na tym, że w przypadku alternatywy, jeżeli którykolwiek z warunków wyrażenia będzie prawdziwy, prawdziwe będzie też całe wyrażenie.

### Operator `not` (**negacja**, `nie`)

W przeciwieństwie do operatorów `and` i `or`, negacja logiczna umieszczana jest przed wyrażeniem, żeby odwrócić jego wartość logiczną (z `True` na `False` albo z `False` na `True`).

```python
if not (age >= 18 or parent_agree):
    print("Przykro nam, nie możesz wziąć udziału w warsztacie")
```

#### Zadanie 1

Zmodyfikuj skrypt znany z poprzedniego rozdziału tak, aby wyświetlał użytkownikowi komunikaty w zależności od średniej ocen. Dla wyniku powyżej 7 - bardzo dobry, 5-7 przeciętny, 4 i mniej nie warto oglądać. 

```python
movie = input("Tytul filmu: ")
grade = input("Ocena filmu w skali 1-10: ")

print("Film pt. " + movie)
print("oceniasz na ", grade)
```

Spójrz tutaj jeśli potrzebujesz pomocy:

```python
movie = input("Tytul filmu: ")
grade = int(input("Ocena filmu w skali 1-10: "))
plot = int(input("Ocena scenariusza w skali 1-10: "))
music = int(input("Ocena muzyki w skali 1-10: "))

print("Film pt. " + movie)

avg = (grade + plot + music ) / 3
print("Film pt. ", movie, "oceniasz na", round(avg, 2))

if avg > 7:
    print("Bardzo dobry")
elif avg >= 5:
    print("Przeciętny")
else:
    print("Nie warto oglądać")

```
{: .solution }


#### Zadanie 2

Do kolejnego zadania musisz skorzystać z managera pakietów Pythona, aby zainstalować zewnętrzną bibliotekę. W konsoli (terminalu, wierszu poleceń) wykonaj wklej  poniższą komendę i naciśnij enter

```
pip install requests
```

Następnie wykorzystaj poniższy fragment kodu, aby wykonać zadanie

```python
import requests #skorzystaj z pakietu request

req = requests.get("http://numbersapi.com/random/year") # odpytujemy API
print(req.text)

"""
Sprawdź czy pobrany tekst ze strony zawiera liczbę "13"
Zapytaj użytkownika o dowolny ciąg znaków.
Sprawdź czy tekst ze strony zawiera też ciąg zadany przez użytkownika
"""
```


```python
import requests #skorzystaj z pakietu request

req = requests.get("http://numbersapi.com/random/year") # odpytujemy API

sentence = req.text

print(sentence)
if "13" in sentence:
    print("Pobrany tekst zawiera liczbę: 13")

word = input("Podaj wyraz do sprawdzenia")
if word in sentence:
    print(f"Pobrany tekst zawiera: {word}")
```
{: .solution }
