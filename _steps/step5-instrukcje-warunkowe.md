---
layout: step
number: 5
title: Instrukcje warunkowe
permalink: step5/
---

Nie zawsze chcemy, żeby nasz kod za każdym razem wykonywał te same czynności - czasem powinien robić inne rzeczy, na przykład reagując na to, co na stronie wpisał użytkownik.

Mówimy wtedy, że nasz kod ma **odgałęzienia**.

Ale jak możemy kontrolować, co robi nasz program? Za pomocą **instrukcji warunkowych**.

Najpopularniejszą instrukcją jest wyrażenie `if`.

Spójrz na przykład poniżej - sprawdzamy, czy użytkownik podał swoje imię i jeżeli tego nie zrobił, ustawiamy odpowiednią treść wiadomości z błędem.

```Javascript
if(imie == ''){
  wiadomoscOBledzie = 'Musisz podać swoje imię!';
}
```

`if` składa się z dwóch części:

- warunku w nawiasach okrągłych (możesz sobie wyobrazić, że to pytanie, które zadajemy naszemu kodowi, na przykład _"Czy imię użytkownika to pusty string?"_),
- kodu w nawiasach klamerkowych, zawierającego instrukcje, które mają się wykonać, jeżeli nasz warunek jest prawdziwy (czyli jeżeli odpowiedzią na nasze pytanie jest _"Tak"_).

Ewentualnie na końcu możesz dodać też `else`, który określa, jaki kod się wykona, jeżeli nasz warunek nie zostanie spełniony.

Warunki przyjmują wartość wyrażeń logicznych, czyli tzw. **booleanów**.
Boolean to takie wyrażenie, którego wartość zostaje oszacowana jako `true` (prawdziwa) lub `false` (fałszywa) dzięki użyciu **operatorów warunkowych**.

Operator warunkowy, którego użyliśmy w powyższym przykładzie to **operator równości**, czyli **A jest równe B**. Jeżeli wartości po jego obu stronach są uznawane za takie same, warunek uznawany jest za prawdziwy (przyjmuje wartość `true`). Jeżeli wartości po obu stronach są różne, warunek nie jest uznawany za prawdziwy i przyjmuje wartość `false`.

## Używanie operatorów porównania

Zmodyfikujmy nasz poprzedni przykład - dodamy miejsce, w którym możemy podać swoje imię, za pomocą którego strona następnie się do nas zwróci.

Najpierw dodajmy miejsce, w którym podamy swoje imię:

```html
<input type="text" id="inputZImieniem" placeholder="Podaj swoje imię" />
```

A teraz zmodyfikujmy nasz kod, dzięki czemu nasze funkcje `przyjdz` i `odejdz` zobaczą, jakie imię wpisaliśmy i użyją go w wiadomości.

```JavaScript
function przyjdz(){
  let imie = document.getElementById('inputZImieniem').value;
  wiadomosc = 'Witaj '+imie+'!';
}

function odejdz(){
  let imie = document.getElementById('inputZImieniem').value;
  wiadomosc = 'Szerokiej drogi '+imie+'!';
}
```

Odśwież stronę, podaj swoje imię i kliknij na przycisk `Przyjdź` lub `Odejdź`.

Ale co jeśli nie podasz żadnego imienia? W wiadomości zostanie puste miejsce, czego chcemy uniknąć.

Dodajmy do naszego kodu instrukcję warunkową, która zapobiegnie takiej sytuacji.

```Javascript
function przyjdz(){
  let imie = document.getElementById('inputZImieniem').value;
  if(imie == ''){
    wiadomosc = "Witaj tajemniczy nieznajomy!  Jak masz na imię?";
  }
  else {
    wiadomosc = 'Witaj '+imie+'!';
  }
}

function odejdz(){
  let imie = document.getElementById('inputZImieniem').value;
  if(imie == ''){
    wiadomosc = 'Szerokiej drogi tajemniczy nieznajomy!';
  }
  else {
    wiadomosc = 'Szerokiej drogi '+imie+'!';
  }
}
```

Jak widzisz, używamy tutaj instrukcji `else`. Jeżeli `imie` jest pustym stringiem, nasza wiadomość nie będzie go używała.
Ale jeżeli nasze `imie` nie będzie pustym stringiem, wykonany zostanie kod znajdujący się w bloku `else`, który ustawi wiadomość, dodając do niej podane przez użytkownika imię (za pomocą znanej ci już konkatenacji - znaku `+`).

Teraz nasze funkcje `przyjdz` i `odejdz` mogą się wykonać na dwa różne sposoby.

Tak na marginesie, możesz zauważyć, że w obu funkcjach wykonywane są prawie takie same instrukcje, które różnią się jedynie małymi różnicami. Oczywiście, możemy zmodyfikować nasz kod w taki sposób, że nie będzie zawierał takich powtórzeń - ale tym zajmiemy się w jednej z kolejnych lekcji, poświęconej funkcjom.

## Operatory warunkowe

Na razie używaliśmy operatora równości, `==`, za pomocą którego sprawdzaliśmy, czy _A jest równe B_. Podobnych operatorów jest jednak znacznie więcej.

| Operator | Nazwa/Opis                                                  | Używany na        |
| -------- | ----------------------------------------------------------- | ----------------- |
| `==`     | Równość. Obie strony mają te same wartości.                 | Liczby i stringi. |
| `===`    | Równość ścisła. Wartość i typ obu stron musi być taka sama. | Liczby i stringi. |
| `!=`     | Brak równości. Strony mają różne wartości.                  | Liczby i stringi. |
| `!==`    | Brak równości ścisłej. Różne wartości ALBO różne typy.      | Liczby i stringi. |
| `<`      | Mniejszy niż.                                               | Liczby.           |
| `>`      | Większy niż.                                                | Liczby.           |
| `<=`     | Mniejszy lub równy.                                         | Liczby.           |
| `>=`     | Większy lub równy.                                          | Liczby.           |

Większość z nich mówi sama za siebie - z wyjątkiem ścisłej równości i jej braku. Wyjaśnijmy sobie krótko, o co z nimi chodzi.

Jeżeli porównywane wartości będą różnych typów, zwykłe porównania (`==` i `!=`) najpierw przekonwertują je do tego samego typu, a dopiero potem dokonają porównania. Przykładowo, `12 == '12'`potraktowane zostanie jak `'12' == '12'`.

Porównania ścisłe nie pozwalają na konwersję typów.

Z tego też powodu zwykle zaleca się korzystanie właśnie z porównań ścisłych.

## Operatory logiczne

Umiemy już radzić sobie z porównaniem dwóch rzeczy. Ale co jeżeli mamy dokonać oceny bardziej skomplikowanych warunków? Wtedy z pomocą przychodzą nam **operatory logiczne**.

Spotykać się będziesz głównie z trzema z nich: `&&`, `||` i `!`

### Operator `&&` (**koniunkcja**, `i`)

`&&` to operator koniunkcji - używamy go, kiedy każdy z poszczególnych warunków wyrażenia musi być prawdziwy.

```javascript
if (wiek >= 18 && zgodaUzytkownika) {
}
```

Używając operatora `&&` możesz łączyć ze sobą tyle warunków, ile tylko zapragniesz. One następnie będą sprawdzane od lewej do prawej i jeżeli tylko jeden z nich będzie fałszywy (będzie miał wartość `false`), całe wyrażenie będzie fałszywe. W przeciwnym razie całe wyrażenie będzie pradziwe (będzie miało wartość `true`).

### Operator `||` (**alternatywa**, `albo`)

`||` to operator alternatywy - używamy go, kiedy tylko jeden z poszczególnych warunków wyrażenia musi być prawdziwy.

```javascript
if (wiek >= 18 || zgodaRodzica) {
}
```

Tak samo jak w przypadku operatora `&&`, używając operatora `||` możesz łączyć ze sobą tyle warunków, ile chcesz. One również sprawdzane są od lewej do prawej - różnica polega na tym, że w przypadku alternatywy, jeżeli którykolwiek z warunków wyrażenia będzie prawdziwy, prawdziwe będzie też całe wyrażenie.

### Operator `!` (**negacja**, `nie`)

W przeciwieństwie do operatorów `&&` i `||`, negacja logiczna umieszczana jest przed wyrażeniem, żeby odwrócić jego wartość logiczną (z `true` na `false` albo z `false` na `true`).

```Javascript
if(!zgodaUzytkownika){

}
```

Ten operator przydaje się w sytuacjach, kiedy coś nie zostało zrobione albo coś poszło nie tak.

### Łączenie operatorów logicznych

Możesz połączyć ze sobą kilka operatorów logicznych w jednym wyrażeniu, ale w wyniku tego może się ono stać nieczytelne. Żeby upewnić się, że kod zachowa się tak, jak tego oczekujesz, łącz poszczególne wyrażenia w nawiasy.

I tak, przykładowo, załóżmy, że chcemy stworzyć formularz, w którym:

- użytkownik ma podać swój wiek (zmienna `age` - liczba),
- użytkownik musi wyrazić zgodę na warunki korzystania z serwisu (zmienna `zgodaUzytkownika` - boolean),
- jeżeli użytkownik ma mniej niż osiemnaście lat, zgodę na warunki korzystania z serwisu musi wyrazić też jego rodzic (zmienna `zgodaRodzica` - boolean).

Poniższe wyrażenie `if` nie działa jednak do końca tak, jak byśmy chcieli.

```Javascript
if (wiek >= 18 || zgodaRodzica && zgodaUzytkownika) {

}
```

Jeżeli spełniony jest warunek `wiek >= 18`, całe wyrażenie uznawane jest za prawdziwe po napotkaniu w nim operatora `||`. Nie o to nam chodziło, prawda?

W takiej sytuacji musimy użyć nawiasów, które pokazują, między którymi wyrażeniami mają zachodzić określone zależności.

```javascript
if ((wiek >= 18 || zgodaRodzica) && zgodaUzytkownika) {
}
```

Jeżeli chcesz odwrócić wartość logiczną wyrażenia znajdującego się w którymś nawiasie, umieść przed nim operator `!` (negację).
