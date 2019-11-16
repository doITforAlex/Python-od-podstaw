---
layout: step
number: 5
title: Tablice
permalink: step5/
---

Nasze zmienne mogą przechowywać stringi i liczby, co jest super, ale co jeżeli jedna zmienna ma przechować kilka wartości?

W programowaniu często spotykamy się z sytuacją, kiedy nasze dane przechowujemy jako listę informacji - w javascript służy do tego specjalny typ danych, **tablica**.

Tablice to obiekty (o których powiemy więcej później), które zawierają jakieś wartości w określonej kolejności. A więc, tablica może przechowywać nie jedną, a kilka danych.

Typy mogące przechowywać różne dane nazywamy czasem **kolekcjami**.

Teraz stwórzmy prostą stronę, na której wyświetlimy listę imion, do której będziemy mogli dodawać kolejne pozycje.

Najpierw napiszmy stronę w HTMLu:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Warsztaty z JSa!</title>
  </head>
  <body>
    <input type="text" id="noweImie" placeholder="Podaj nowe imię" />
    <button id="przyciskDodajImie">Dodaj imię</button>
    <div id="liczbaImion"></div>
    <div id="listaImion"></div>
  </body>
  <script></script>
</html>
```

Dzięki temu mamy już okno, w którym możemy wpisać nowe imię, przycisk, który doda je do listy i dwa divy - jeden, w którym wyświetla się lista imion i drugi, pokazujący liczbę imion.

Teraz zajmijmy się naszym tagiem `<script>`...

## Tworzenie tablicy

Pustą tablicę tworzymy używając nawiasów kwadratowych.

Na początku swojego tagu `<script>` stwórz zmienną `imiona` i przypisz do niej początkową wartość - pustą tablicę.

```Javascript
let imiona = [] ;
```

Oczywiście, jeżeli chcesz, możesz stworzyć tablicę, która będzie już zawierała jakieś elementy - oddzielaj je wtedy od siebie przecinkami.

```Javascript
let imiona =["Karolina", "Asia"];
```

W naszym przykładzie zaczniemy jednak od pustej tablicy.

## Dodawanie elementów do tablicy

Chcemy, by po kliknięciu na przycisk `Dodaj imię`, nowe imię zostało dodane na końcu stworzonej przez nas tablicy.

W tym celu najpierw napiszmy funkcję, która będzie się wykonywała po kliknięciu na ten przycisk i przypiszmy ją do określonego zdarzenia.

```javascript
function dodajImie() {}

document.getElementById("przyciskDodajImie").onclick = dodajImie;
```

Teraz w funkcji `dodajImie` chcemy pobrać wpisaną przez użytkownika wartość i dodać ją na końcu naszej tablicy.

```javascript
let imie = document.getElementById("noweImie").value;
imiona.push(imie);
```

`push()` to funkcja, którą możemy wykonać na każdej tablicy - nazywamy ją wtedy właściwością. Istnieje jeszcze wiele innych właściwości, z których możemy korzystać, ale o nich powiemy sobie później.

Skoro dodaliśmy już nowe imię do tablicy, chcemy ją wyświetlić i policzyć, ile imion zawiera.

Żeby elementy naszej tablicy stały się jednym stringiem, użyjemy właściwości `join()`, która konkatenuje ze sobą wszystkie elementy tablicy w jeden ciąg znaków.

Z kolei do policzenia elementów tablicy, skorzystamy z właściwości `length`. Jak widzisz, w przeciwieństwie do dwóch poprzednich, ta właściwość nie jest funkcją, a po prostu właściwością liczbową.

Teraz, wewnątrz funkcji `dodajImie` dodaj następujący kod:

```javascript
document.getElementById("listaImion").innerText =
  "Imiona to:" + imiona.join(", ") + ".";
document.getElementById("liczbaImion").innerText =
  "Na liście mamy " + imiona.length + " imion.";
```

A teraz otwórz tę stronę i dodaj do listy kilka imion.

Super!

Jak możesz jednak zauważyć, z naszą stroną jest kilka małych problemów.

1. Do listy możesz dodać puste imię, co nie wygląda zbyt fajnie.
2. Jeżeli na liście masz tylko jedno imię, wyświetla się wiadomość "Na liście mamy 1 imion". Lepiej, żeby w takim przypadku wyświetlało się "Na liście mamy 1 imię".

Żeby to naprawić napiszemy kilka warunków. Spróbuj zrobić to samodzielnie, zanim pójdziemy dalej.

Podpowiedzi:

1. `if (imie !== ‘’)`
2. `if (imiona.length === 0)`

Możliwe rozwiązanie:

```javascript
<script>
  let imiona = [];

  function dodajImie(){
    let imie = document.getElementById('noweImie').value;
    if(imie !== ''){
      imiona.push(imie);
    }

    let komunikatZLiczbaImion = '';
    let komunikatZListaImion = '';

    if (imiona.length === 0){
      komunikatZLiczbaImion = "Na razie nie mamy jeszcze żadnych imion.";
    }
    if (imiona.length === 1){
      komunikatZLiczbaImion = "Na liście mamy 1 imię.";
      komunikatZListaImion = "Imię to: " + imiona[0] + ".";
    }
    if (imiona.length > 1){
      komunikatZLiczbaImion = "Na liście mamy " + imiona.length + " imion.";
      komunikatZListaImion = "Imiona to: " + imiona.join(', ') + ".";
    }
    document.getElementById('liczbaImion').innerText = komunikatZLiczbaImion;
    document.getElementById('listaImion').innerText = komunikatZListaImion;
  }

  document.getElementById("przyciskDodajImie").onclick = dodajImie;

</script>
```
