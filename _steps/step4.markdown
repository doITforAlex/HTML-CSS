---
layout: step
number: 4
title: Formatowanie strony głównej
permalink: step4/
---

Aby przeglądarka wiedziała, jak wyświetlać treść, musimy wskazać jej która część jest czym np. nagłówkiem, akapitem, listą itp.

Patrząc na treść na naszej stronie głównej, widzimy, że mamy nagłówek, dwa akapity każdy składający się z jednego zdania, a następnie wypunktowaną listę dwóch elementów.

```
Tiny Cakes!
-----------

Welcome to my recipes web site all about Tiny Cakes!

Here are the recipes that we have:

 * Traditional cupcakes
 * Muffins
```
Musimy teraz dodać odpowiednie znaczniki HTML by to oddać. Taki zabieg nazywamy znakowaniem/oznaczaniem tekstu (marking up).

Sama koncepcja oznaczania tekstu istniała w przemyśle wydawniczego, gdzie edytor zapisywał na manuskrypcie w jaki sposób tekst powinien zostać sformatowany do wydruku. Wraz z rozwojem technologii możliwe stało się skomputeryzowanie procesu wydruku a przepisywanie ponownie tekstu stało się zbędne.  https://pl.wikipedia.org/wiki/J%C4%99zyk_znacznik%C3%B3w#Historia

Zamieńmy teraz treść naszego `<body>` dokumentu `index.html` na poniższy tekst:

```html
  <h1>Tiny Cakes!</h1>

  <p>
  Welcome to <em>my</em> recipes web site all
  about <strong>Tiny Cakes!</strong>
  </p>

  <p>
  Here are the recipes that we have:
  </p>

  <ul>
    <li>Traditional Cupcakes</li>
    <li>Muffins</li>
  </ul>
```

Zapisz plik i odśwież przeglądarkę. Wygląda to teraz znacznie lepiej, prawda?

![The marked-up home page](../assets/browser-formatted-homepage.png){:title="The marked-up home page" class="img-responsive imgbox"}

Przeanalizujemy teraz poszczególne znaczniki HTML, które zostały użyte w powyższym tekście.

`<h1>`
: To znacznik nagłówka, a dokładniej odnosi się do
 **nagłówka najwyższego poziomu**. Jak się domyślacie istnieją `<h2>`, `<h3>` itd. aż do `<h6>`.  Używamy ich do zaznaczenia nagłówków i podtytułów. Wyższy numer oznacza niższy poziom,wtedy również rozmiar czcionki nagłówka zmniejsza się.

`<p>`
: **paragraf** oznacza blok tekstu.  
<!-- Note that HTML doesn't display line breaks. -->

`<strong>`
: znacznik **strong/ważne** oznacza, że tekst zawiera jakąś ważną informację. Przeglądarki zwykle wyświetlają go pogrubioną czcionką.  

`<em>`
: czyli **emphasis/emfaza** , tag używany dla podkreślenia tekstu, wyświetlany jako kursywa.

`<ul>`
: oznacza  **unordered list/nienumerowaną listę** i korzystamy z niego gdy chcemy stworzyć listę wypunktowaną.

Dla porównania **ordered list/numerowaną listę** stworzysz tagiem `<ol>`.

`<li>`
: **list item/element listy** to znacznik używany przy wymienianiu kolejnych elementów list, zarówno numerowanej jak i wypunktowanej.

Czy jest to tak trudne jak się wydaje? Oczywiście istnieje więcej znaczników niż te, które wymieniliśmy przed chwilą ale obowiązują je te same zasady: 
<!-- And that is mostly as hard as HTML gets.  There are a lot more tags than just these few but the same basic concept applies: -->

1. Używamy znaczników HTML aby sprecyzować w jaki sposób przeglądarka powinna wyświetlać poszczególne elementy zawartości strony .
2. Używamy znaczników otwierających i zamykających by wskazać miejsce działania kodu.

## Zagnieżdżanie elementów. Znaczniki liniowe a blokowe.

Istnieją dwa główne typy znaczników **inline/liniowe** oraz **block/blokowe**.

Znaczniki blokowe zawsze zaczynają nową linię i zajmą jej całą przestrzeń. Dla odmiany, znaczniki liniowe nie zaczną się od nowej linii i zajmą tylko tyle miejsca ile będzie im potrzebne (w praktyce jest to trochę bardziej skomplikowane, ale na tę chwilę niech wystarczy nam takie rozróżnienie).

Wszystkie znaczniki, których użyliśmy do tej pory poza `<em>` i `<strong>` są znacznikami blokowymi.

Zauważ, że znaczniki `<em>` i `<strong>` umieściliśmy w  paragrafie `<p>`?  Taki zabieg nazywamy **nesting/zagnieżdżaniem** elementów.

W zasadzie *możesz* zagnieździć każdy znacznik. Chociaż wynik takiego zabiegu może wyglądać satysfakcjonująco to nie zawsze ma on sens. 

Przypatrzmy się poniższemu przykładowi:

```html
<p>
Welcome to <em>my</em> recipes web site all
about <strong>Tiny Cakes!</strong>
<h2>Recipes:</h2>
Here are the recipes that we have:
</p>
```
Ten kawałek kodu może spowodować problemy. Przeglądarki nie są zawsze konsekwentne w interpretacji takiego kodowego misz-maszu. Kiedy zaczniesz używać później CSS, zobaczysz że taki kod nie jest przyjazny CSS. 

Kolejna sprawa. Niektóre znaczniki *muszą* zostać zagnieżdżone w środku innych, ponieważ nie będą działać poprawnie bez nich. Takim przykładem jest tag `<li>`, który musi znaleźć się w środku `<ol>` lub `<ul>`. Nie możemy przecież stworzyć element listy bez listy.


## Hiperlinki

Kolejną istotnym znacznikiem HTML, który musimy przedstawić zanim przejdziemy do kolejnego kroku
jest `<a>`, **anchor/kotwica** inaczej znacznik hiperlinku.

Hiperlinki tworzymy tagiem `<a>`. Są to odnośniki do innych stron www.

Zamieńmy teraz listę naszych przepisów w listę z hyperlinkami do stron z przepisami.
Zamień całą sekcję `<ul>` na poniższy kodem:

```html
<ul>
  <li><a href="traditional-cupcakes.html">Traditional Cupcakes</a></li>
  <li><a href="muffins.html">Muffins</a></li>
</ul>
```
Odśwież stronę. Teraz lista powinna zawierać hyperlinki, które zwykle wyświetlane są jako niebieski, podkreślony tekst.

![Dodawanie linków do listy](../assets/browser-formatted-home-links.png){:title="Adding links to the list" class="img-responsive imgbox"}

Jeśli klikniesz jeden z odnośników, przeglądarka przejdzie do strony odnośnika. Zobaczysz niesformatowaną treść. Nie dodaliśmy w końcu tam jeszcze żadnych znaczników. Kliknij przycisk Wstecz w przeglądarce, aby wrócić do oryginalnej strony.

Widzisz w tagu część `href =" muffins.html`? Nazywamy ją atrybutem. W szczególności jest to atrybut **odwołania hipertekstowego**. Cytaty zawierają adres URL, do którego prowadzi łącze. Tutaj po prostu umieszczamy tylko nazwę pliku strony bez protokołu i nazwy hosta, ponieważ wszystkie nasze pliki znajdują się w tym samym katalogu.

Gdybyśmy chcieli dać odnośnik do innej strony niż nasza, to wtedy musimy podać kompletny już adres:

```html
<a href="http://nodegirls.com.au/brisbane.html">Node Girls: Brisbane</a>
```
Niektóre tagi wymagają atrybutów aby wywołać określone funkcje.

Ok, przejdźmy teraz do formatowania naszych stron z przepisami.