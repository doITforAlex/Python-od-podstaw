---
layout: step
number: 4
title: Typy danych
permalink: step4/
---

Tworzyliśmy zmienne, które przechowywały dane, ale jakie dane? Gdy patrzymy na napis wiemy, że jest napisem, czy na cyfry, mózg wie, żeby je potraktować jako policzalne wartości. Skąd wie to Python? Otórz dla komputera istnieją typy danych. W tym rozdziale poznasz podstawowe typy. *W czasie warsztatu nie poruszamy wszystkim typów, które są dostępne w Pythonie.*

Pierwsza rzecz na jaką trzeba zwrócić uwagę to dynamiczna zmiana typu:

```
>>> a = 26
>>> print(a)
>>> a = "Rita"
>>> print(a)
```

Dla Pythona powyższy kod jest zupełnie naturalny. Najpierw zmienna `a` przechowywała liczbę, a następnie do `a` ponownie przypisaliśmy wartość, tym razem jednak wartość tekstową. 

Nie we wszystkich językach programowania takie zachowanie jest dopuszczalne. W językach takich jak C++, C# czy Java zmienna ma z góry określony typ i próba zmiany typu powoduje błąd stąd ich nazwa **statycznie typowane**. Python jednak należy do grupy języków programowania **dynamicznie typowanych** (jak Ruby, JavaScript czy PHP).


### String

Ten typ już poznaliśmy: string - czyli łańcuch znaków = napis. String jest *sekwencją* dowolnych znaków, oznaczoną za pomocą apostrofów 'moj tekst' lub cudzysłowów "moj tekst". Stringi zazwyczaj przechowują słowa, zdania.

Przetestuj poniższy kod

```
>>> txt = "Hello world"
>>> welcome = "I’m Flynerd"
>>> type(txt)
>>> type(welcome)
```

Typ podpowiedziało nam z jakim typem danych pracujemy.

---

**Nadpisanie wartości**

```
>>> txt = "Flynerd"
>>> print(txt)
>>> txt = "3 + 4"
>>> print(txt)
>>> txt = "3" + "4"
>>> print(txt)
```

---

**Konkatenacja (łączenie) stringów**

```
>>> pp = "pen pineapple"
>>> ap = "apple pen"
>>> concatenation = pp + ap
```

Wyświetl powyższe zmienne

---

```
>>> welcome = "Hello"
>>> user_name = "Alicja"
>>> sentence = welcome + " " + user_name + ", welcome home!"
>>> print(sentence)
>>> mood = f"How are you today { user_name }"
>>> print(mood)
```

W ostatnim przykładze pojawiła się literka `f` przed ciągiem znaków, w ten sposób tworzymy **f-string**, string, który może zawierać jakąś zmienną w środku. U nas string "How are you today" zawiera zmienną przechowującą imię.

---


**Mnożenie napisów**

```
>>> letterA = "A"
>>> print(25 * letterA)
>>> print(letterA)
>>> letterB = "B"
>>> letterB = 5 * letterB
>>> print(letterB)
```

#### Zadania

Zajrzyj do dokumentacji - metody String! Możesz skorzystać z Google:

1. Utwórz zmienną, która będzie przechowywać imię pupila, a następnie wyświetl informację "Pogłaszcz {imie_pupila}, ucieszy się".
2. Zapisz swoje imię i nazwisko do dowolnej zmiennej. Ile znaków ma Twoje imię i nazwisko?
3. Zmień wszystkie litery imienia i nazwiska na drukowane.
4. Jaką metodą usunąć z ciągu znaków “Programujemy w Pythonie” literę `a`?
5. ⭐W jaki sposób zamienić ciąg znaków “123” na liczbę 123?

### Indeksowanie znaków

Każda sekwencja w Pythonie (np. ciąg znaków,  ciąg elementów na liście), jest **numerowana od 0** (tzw. indeksowana). 


![Indeksowanie](../assets/step-3b.png){:title="Indeksowanie sekwencji" class="img-responsive"}

```
>>> seq = "Monty Python"
>>> print(seq[0])
>>> print(seq[1])
>>> print(seq[2])

>>> print(seq[6:10]) # przycinanie
Pyth

>>> print(seq[-1])
>>> print(seq[-2])

>>> print(seq[-12:-7])
Monty
```

Przycinanie obywa się wg. wzoru: `[start:stop:krok]` albo `[-od_tylu]`
# zawsze od zera!

Przeanalizuj kolejne linie kodu, każdą wyświetl:

```python
cool_string = "The quick brown fox jumped over the lazy dog"

# sprawdź długość - liczbę znaków
length = len(cool_string)  # 44

index0 = cool_string[0]  # litera: 'T'
index5 = cool_string[5]  # litera: 'u'

# znajdź ostatnią literę
index_last = len(cool_string) - 1 # dlaczego musmy odjąć 1?
last_char = cool_string[index_last]  # litera: 'g'

cool_slice_to_end = cool_string[4:]  # 'quick brown fox jumped over the lazy dog'

reversed_string = cool_string[::-1]  # odwraca kolejność liter
```

#### Zadania

1. Utwórz zmienną zawierającą napis "Lorem ipsum dolor sit amet, consectetur adipiscing elit."
2. Wytnij i wyświetl samo słowo elit.
3. Usuń z napisu wszystkie literki "o"

### Liczby
Typ numeryczny przechowuje wartości liczbowe. Są to niezmienne typy danych, co oznacza, że ​​zmiana wartości dla danych liczbowych powoduje powstanie nowo przydzielonego obiektu.

W Pythonie wyróżniamy 3 typy liczbowe
- liczby całkowite (`int` - integer)
- zmiennoprzecinkowe (`float` - floating point)
- zespolone (`complex`)

Utworzymy sobie dwie rożne zmienne przechowujące liczby - całkowitą i dziesiętną (*zmiennoprzecinkową*), a następnie przeprowadzimy kilka operacji:

```
>>> a = 20
>>> b = 5.5
>>> print(a + b)
>>> print(a - b)
>>> print(a * b)
>>> print(a / b)
>>> print(a % b != 0)
```

**Sprawdź**:
```
type(a)
type(b)
```

### Konwersja typów
Na razie mówiliśmy jedynie o przeprowadzaniu operacji na wartościach tego samego typu (na przykład na dwóch liczbach). Ale co się stanie, jeżeli spróbujesz przeprowadzić operację na danych różnych typów? Chociażby pomnożyć string przez liczbę? Albo dodać do siebie string i liczbę?

```
>>> a = 20
>>> c = "30"
>>> print(a + c)
```

Zobaczymy błąd, gdyż typ liczbowy nie może zostać dodany do typu string!

Istnieją metody **int()** czy **float()**, za pomocą których dokonamy zmiany jednego typu na drugi, czyli dokonamy **konwersji typu**. Stąd nasz przykład powyżej możemy naprawić:

```
>>> a = 20
>>> c = int("30")
>>> print(a + c)
```

albo

```
>>> a = 20
>>> c = float("30")
>>> print(a + c)
```

To jeszcze szybki przegląd przez inne właściwości typu liczbowego.
---

Przypisanie wartości 3 do zmiennej a (int) oraz 4.1 do zmiennej b (float)

```
a, b = 3, 4.1
print("Zmienna a = ", a, "b = ", b)
```

Operator dzielenia zawsze zwraca wartość float

```
print(a / b)  # 0.7317073170731708
```

**Dzielenie "podłoga"**

```
print(a // b)  # 0.0
```

**Zmienna b (4.1) podniesiona do potęgi a (3)**

```
print(b**a)  # 68.9209999
```

## Listy
Lista (inaczej tablica) to struktura danych w Pythonie, która jest sekwencją elementów. Każda wartość znajdująca się na liście jest nazywana elementem. Jest to jeden z najczęściej używanych typów w Pythonie.

Nie ma co tracić czasu, przejdźmy do kodu!

Aby stworzyć listę elementów musimu użyć nawiasów kwadratowych `[]`.

```
>>> shopping_list = []
>>> print(shopping_list)
```

Utworzyliśmy pustą listę.

Zapełnijmy ją:

```
>>> shopping_list = ["chleb", "cebula", "ziemniaki", "czekolada"]
>>> grades = [1, 2, 3, 4, 5, 6]
>>> print(shopping_list)
>>> print(grades)
>>> type(shopping_list)
>>> type(grades)
```

**Łączenie list**
```
>>> concatenation = shopping_list + grades
>>> print(concatenation)
```

Weźmy pierwszy produkt z listy zakupów:
```
>>> shopping_list[1]
'cebula'
```
Jednak wynik jest jednak inny niż się spodziewamy. Kolejne elementy w tablicy są zawsze numerowane od 0, czyli:

```
>>> shopping_list[0]
'chleb'
```

### Metody typu list

**Dodawanie elementu na listę**
```
>>> my_arr = [3, 4]
>>> my_arr.append("milk")
>>> print(my_arr)
[3, 4, 'milk']

>>> another_arr = [4, 5, 8] 
>>> my_arr.append(another_arr) 
>>> print(my_arr)
[3, 4, 'milk', [4, 5, 8]]

>>> print(my_arr[3])
[4, 5, 8]
```

**Dodawanie wielu elementów na raz**
```
>>> my_arr.extend([1, 2, 3])
>>> print(my_arr)
[3, 4, 'milk', [4, 5, 8], 1, 2, 3]
Zdejmowanie elementu z listy
>>> number = my_arr.pop(1)
>>> print(my_array)
[3, 'milk', [4, 5, 8], 1, 2, 3]
>>> print(number)
4
```

**Podstawienie elementu - zastąpienie elementu tablicy innym elementem**
```
>>> sentence_arr = ['Ala', 'ma', 'kota', 'i rybki.']
>>> print(sentence_arr)
>>> sentence_arr[2] = 'psa'
>>> print(sentence_arr)
```

#### Zadania

Rzuć okiem na dokumentację: metody typów sekwencyjnych

1. Utwórz nową tablicę zawierającą liczby od 1 do 10 i przypisz ją do zmiennej.
2. Sprawdź czy lista zawiera liczbę 5.
3. Spraw, aby tablica przybrała postać [10, 9, 8, 7, 6, 5, 4, 3, 2, 1].
4. Spraw, aby liczby w tablicy [123, 1, 192, 21, 13, 9, 299] były uporządkowana rosnąco.
5. Do listy bogów greckich ["Zeus", "Hestia", "Hades", "Atena", "Afrodyta"] dodaj swoje imię, a następnie usuń wybraną postać. Podmień dowolnie wybraną postać na Apollo

## Boolean

Typy boolowskie inaczej zwane typami logicznymi posiadają tylko dwie wartości True / False

```
>>> print(1 == 1)
  True
>>> print(1 == 2)
  False
```

Zapis ma znaczenie! True (pierwsza litera wielka, reszta to małe litery). true, TRUE, tRUE nie zadziałają - tylko True jest poprawne (to samo dotyczy False).

Porównaj:
```
>>> type(True)
>>> type("True")
```

#### AND / OR / NOT
Poćwicz i pobaw się wartościami logicznymi wpisując następujące instrukcje:

```
>>> True and True
>>> False and True
>>> True or 1 == 1
>>> False or 1 == 1
>>> 1 != 2
>>> NOT True
```

---

Inne typy dostępne w Pythonie, których dzisiaj nie omówmy:
- krotki tuple, 
- zestawy set, 
- słowniki dict,
- zakresy range,
- sekwencje binarne np.bytes

---


