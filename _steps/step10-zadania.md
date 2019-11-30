---
layout: step
number: 10
title: Zadania
permalink: step10/
---

### 1. Warm Up 🧠

Przeanalizuj poniższy kod

```python
def menu(option):
    if option == 1:
        print("Jeden")
    elif option == 2:
        print("Dwa")
    elif option == 3:
        print("Trzy")
    elif option == 4:
        print("Cztery")
    else:
        print("Ohooo")


menu(1)
choice = 2
menu(choice)
menu(4)
```


### 2. Jedzenie dla leniwych 🍔

Utwórz menu użytkownika, w zależności od wybranej kategorii dania, zaproponuj użytkownikowi posiłek.

### 3. Choinka 🎄

Narysuj choinkę:
```
    +
   +++
  +++++
 +++++++
+++++++++
```

- użytkownik podaje rodzaj znaku
- użytkownik podaje wysokość choinki
- znak użytkownika nie może być literą ani cyfrą

### 4. Literki 🔠

Pobierz od użytkownika dowolny tekst i wyświetl tylko te znaki, które są na pozycjach parzystych. Wykonaj zadanie na dwa sposoby - za pomocą pętli oraz przez string slicing ( ‘abrakadabra’ -> ‘baaar’).

### 5. Co na prezent? 🎁
Stwórz listę pomysłów na prezent dla swoich bliskich. Kiedy nadarzy się okazja, aby dać im prezent (święta, urodziny, rocznicę), program losowo wybierze jeden (i być może miejsca, w których możesz go zdobyć).

### 6. Zakoduj tajną wiadomość 🕵️
```
PYTHON JEST SUPER
```

- stwórz plik `secret1.py` zaawierający algorytm, który zmieni powyższą wiadomość w ciąg ”RZUIPO-KFTU-TWRFS”
- wymyśl własny algorytm kodujący (możesz skorzystać z istniejących np. klasyczne/harcerskie) jako `secret2.py`
- napisz program `secret3.py`, które odkoduje twoją wiadomość

### 7. Śledź robota 🤖
Robot porusza się w płaszczyźnie zaczynając od pierwotnego punktu (0,0). Robot może poruszać się w GÓRĘ, W DÓŁ, ​​W LEWO i W PRAWO, wykonując określone kroki. Ślad ruchu robota pokazano następująco:
```
UP 5
DOWN 3
LEFT 3
RIGHT 2
```
Liczby po kierunku są krokami. Napisz program do odczytu wskazówek podanych jak wyżej i oblicz odległość od aktualnej do startowej pozycji. Jeśli odległość jest liczbą dziesiętną, wyświetl po prostu najbliższą liczbę całkowitą.

Przykład:
```
UP 5
DOWN 3
LEFT 3
RIGHT 2
```

Wynik: `3`

### 8. Sprawdź pogodę 🌤

Przypomnij sobie zadanie z wykorzystaniem biblioteki `requests` do odpytania zewnętrznego API.
Strona OpenWeatherMap udostępnia różnego rodzaju informacje o pogodzie. Skorzystaj z dokumentacji [Current Weather](https://openweathermap.org/current). Przyjrzyj się jak zbudowany jest adres URL. 

Pozwól użytkownikowi podać miasto oraz dwuliterowy kod kraju. Możesz ograniczyć miasta przez wybór kraju w prostym menu np.

- United Kingdom - uk
- Poland - pl
- Germany - de
- itd...

Pokaż użytkownikowi krótkie zdanie o pogodzie oraz temperaturę w st. Celsjusza.

*Uwaga: OpenWeather API może wymagać autoryzacji. Należy założyć darmowe konto i w miejsce appid podać swój klucz konta (`&APPID=your_key`)*

### 9. Love calculator 💖

Stwórz grę inspirowaną miłosną wróżbą z czasów szkolnych. Zasady gry przedstawia to [wideo](https://www.youtube.com/watch?v=oFsLVG7EAZ4).
1. Pobierz imiona zakochanych
2. Policz wystąpienia każdej z liter w obu imionach oraz słowie LOVE.
3. Redukuj liczbę elementów tablicy dodając pierwszą i ostatnią liczbę do siebie, tak długo, aż zostaną dwie cyfry.
4. Dwie ostatnie cyfry tworzą wartość procentową dopasowania pary wg. wróżby.
