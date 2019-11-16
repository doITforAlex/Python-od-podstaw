---
layout: step
number: 10
title: Skrypty zewnetrzne
permalink: step10/
---

Do tej pory cały nasz kod pisaliśmy w tagu `script` znajdującym się w naszym HTMLu.
Takie rozwiązanie sprawdza się w przypadku prostych stron, ale nie nadaje się do pisania bardziej skomplikowanego kodu. I co w przypadku, jeżeli zechcemy użyć jednego kodu na kilku stronach?

Tag `<script>` może być używany nie tylko do pisania kodu bezpośrednio wewnątrz niego, ale także do odwoływania się do kodu zapisanego w innym pliku, podobnie jak odwołania do pliku css.

Jak to zrobić?

1. Umieść swój kod w osobnym pliku. Zwykle ma on rozszerzenie `.js` i powinien być odpowiednio nazwany.
2. W tagu `<script>` użyj atrybutu src, który określi ścieżkę do twojego pliku z kodem.

Zmodyfikujmy w ten sposób nasz pierwszy przykład z lekcji 1:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Warsztaty z JSa!</title>
  </head>
  <body>
    <button id="przycisk">Kliknij na mnie</button>
    <pre id="okno"></pre>
  </body>
  <script src="script.js"></script>
</html>
```

A teraz cały kod wrzuć do pliku `script.js`:

```javascript
function zrobCos() {
  document.getElementById("okno").innerText = "Naciśnięto przycisk!";
}
document.getElementById("przycisk").onClick = zrobCos;
```

Atrybut `src` tagu `<script>` działa bardzo podobnie do atrybutu `src` tagu `<img>`.

Spróbuj teraz przerobić w ten sposób pozostałe przykłady, na których pracowaliśmy.
