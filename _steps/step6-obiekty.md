---
layout: step
number: 6
title: Obiekty
permalink: step6/
---

Za pomocą tablic potrafimy już tworzyć listy wartości.

Ale co jeżeli nasza lista ma być bardziej skomplikowana i nie możemy jej zapisać po prostu jako ciągu pojedynczych wartości? Jeżeli nasza aplikacja ma zawierać odpowiednio nazwane informacje o naszych użytkownikach? Albo o naszych kotach?

Wtedy przydadzą nam się **obiekty**.

Obiekty to zmienne, które zawierają kilka wartości. Ich zadaniem jest łączenie razem kilku wartości, które odnoszą się do jednej rzeczy. Takie wartości obiektu nazywamy jego właściwościami.

Stwórzmy kolejną stronę, ale tym razem zamiast listy imion będziemy pracować na liście obiektów, które będziemy wyświetlać na różne sposoby.

I tak, przykładowo, nasz użytkownik może mieć imię, adres, swój unikalny numer użytkownika. Albo kot może mieć imię, wagę czy kolor.

Obiekty można tworzyć na kilka różnych sposób, ale najłatwiejszym jest korzystanie z **literału obiektu**.

Oto nasz obiekt `kot`:

```javascript
let kot = {
  imie: "Garfield",
  waga: 8.2,
  kolor: "pomarańczowy",
  lubi: "lasagne",
  nienawidzi: "poniedziałków"
};
```

Nasz obiekt, przypisany do zmiennej `kot`, ma pięć właściwości: 4 stringi i jedną liczbę.
Żeby odwoływać się do właściwości obiektu, podaj jego nazwę i określoną właściwość, oddzielając je od siebie kropką, np. `kot.imie`, `kot.lubi`.

Właściwości obiektu możesz używać w taki sam sposób, jak pozostałych zmiennych:

```javascript
kot.waga = kot.waga - 0.2;

console.log(kot.imie + " naprawdę nienawidzi " + kot.nienawidzi);
```

Jeżeli spróbujesz odwołać się do właściwości, która nie istnieje, jej wartością będzie `undefined`.

Jeżeli z kolei spróbujesz przypisać wartość do takiej nieistniejącej właściwości, zostanie ona stworzona.

Javascript i przeglądarki w dużym stopniu korzystają właśnie z obiektów. Każdy element na stronie i każde zdarzenie jest obiektem. Ale o tym dowiemy się za chwilę.
