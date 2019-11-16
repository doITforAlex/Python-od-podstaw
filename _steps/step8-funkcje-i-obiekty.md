---
layout: step
number: 8
title: Funkcje i obiekty
permalink: step8/
---

W naszym kodzie używaliśmy kilkukrotnie `document.getElementById`, ale nie wyjaśniliśmy sobie jeszcze, co to tak właściwie znaczy.

Otóż `getElementById` to właściwość obiektu `document` i jednocześnie funkcja, która zwraca pewną wartość.

Ale hola hola, czy właściwość obiektu może być funkcją?

## Fukncje jako wartości

Funkcje są także typami danych. Główna różnica między nimi a innymi danymi jest taka, że funkcje można wywoływać, czego nie można zrobić chociażby z liczbami czy stringami.

Spójrz na kod poniżej:

```javascript
function szczekanie() {
  return "hau-hau-hau";
}
let burekSzczeka = szczekanie;
console.log(burekSzczeka());
```

`szczekanie` jest funkcją, a `burekSzczeka` to zmienna.

Kiedy przypisujemy funkcję `szczekanie` do zmiennej `burekSzczeka`, `burekSzczeka` w dalszym ciągu jest zmienną, ale teraz jako zmienna zawiera deklarację funkcji. A więc również jest funkcją, która może zostać wywołana. Szaleństwo!

Zwróć uwagę, że podczas przypisywania `szczekanie` do zmiennej `burekSzczeka`, nie wywołujemy funkcji `szczekanie`. Gdybyśmy to zrobili, do funkcji `burekSzczeka` zostałoby przypisane to, co zwraca funkcja `szczekanie` (czyli "hau-hau-hau"), a nie ta funkcja sama w sobie. Jak widzisz, to duża różnica.

Właśnie w taki sposób przypisujemy funkcje do zdarzeń. `getElementById` zwraca nam obiekt, który odzwierciedla odpowiedni element HTML ze strony. Funkcje zdarzeń, takie jak `onclick` i `onchange` to właściwości tego obiektu, dzięki którym możesz przypisać do nich cokolwiek zechcesz. Domyślnie mają one wartość null. Kiedy dochodzi do jakiegoś zdarzenia, przeglądarka sprawdza, czy odpowiednia właściwość ma wartość null, i jeżeli nie, próbuje wykonać zawarty w niej kod. Jeżeli przypiszemy do tej właściwości coś innego niż funkcja, dostaniemy błąd w konsoli.

## Wyrażenia funkcyjne

Funkcje możemy tworzyć także za pomocą **wyrażeń funkcyjnych**.

```javascript
let burekSzczeka = function() {
  return "hau-hau-hau";
};
```

Jak widzisz, możesz od razu zadeklarować funkcję przypisując ją do zmiennej.

Oczywiście, możesz dać tej funkcji jakąś nazwę (tak jak w przykładzie wyżej nazwaliśmy ją `szczekanie`), ale to nie miałoby za dużo sensu - nie będziemy mogli się odwoływać do tej funkcji po jej nazwie, a po nazwie zmiennej. Takie funkcje, które nie mają swoich nazw, nazywamy **funkcjami anonimowymi**.

Dzięki wyrażeniom fukcyjnym możemy zrobić coś takiego:

```javascript
document.getElementById("przycisk").onclick = function(){
  document.getElementById("komunikat").innerText = "Naciśnięto przycisk!"!
};
```

To dosyć wygodna metoda na upraszczanie naszego kodu, gdy potrzebna jest nam jakaś funkcja.

## Funkcje jako właściwości obiektów

Oczywiście, jeżeli możemy przypisywać funkcje do zmiennych, to możemy je przypisywać też jako właściwości obiektów.

Tym właśnie jest `getElementById`, właściwością obiektu `document` .

Spójrz na przykład poniżej: mamy obiekt, którego właściwościami są trzy funkcje, przypisane na trzy różne sposoby - jako deklaracja funkcji, wyrażenie funkcyjne przypisane do zmiennej i wyrażenie funkcyjne przypisane bezpośrednio do właściwości.

```javascript
let odglosyZwierzat = {
  kot: miau,
  pies: hau,
  kaczka: function() {
    console.log("kwa kwa!");
  }
};

function miau() {
  console.log("miau miau!");
}
let hau = function() {
  console.log("hau hau!");
};

odglosyZwierzat.kot();
odglosyZwierzat.pies();
odglosyZwierzat.kaczka();
```

(Możesz zauważyć, że ten przykładowy kod nie zadziała - wynika to z tego, że zmienna `hau` jest używana zanim zostanie do niej przypisana funkcja. Kod zadziała, jeżeli przeniesiesz zmienną `hau` na sam początek kodu. Jeżeli chcesz dowiedzieć się czegoś więcej na ten temat i dlaczego ten problem nie dotyczy funkcji `miau`, poczytaj o hoistingu tutaj <https://developer.mozilla.org/pl/docs/Glossary/Hoisting> ).

## Łączenie funkcji i właściwości

No dobrze, spójrzmy jeszcze na kod, którego niedawno używaliśmy:

```javascript
document.getElementById(‘przycisk’).onclick = jakasFunkcja;
```

W tej jednej linijce bardzo wiele się dzieje.

`document.getElementById(‘przycisk’)` zwraca nam obiekt `Element`, tak więc możemy od razu coś z nim zrobić. Jak pewnie pamiętasz, kiedy wywołamy funkcję, która coś zwraca, dostaniemy w rezultacie to, co nasza funkcja zwróciła.

Łączenie ze sobą kilku wywołań funkcji i odwołań do właściwości obiektu to property chaining lub function chaining (czyli po polsku po prostu łączenie właściwości lub łączenie funkcji). Z czasem nabierzesz wyczucia, kiedy warto z tego korzystać, a kiedy nasz "łańcuszek" lepiej rozbić na kilka mniejszych części.

I odnosząc to do naszego kodu powyżej - moglibyśmy go równie dobrze zapisać jako:

```javascript
let przycisk = document.getElementById(‘przycisk’);
przycisk.onclick = jakasFunkcja;
```

Efekt będzie dokładnie taki sam.
