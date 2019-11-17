---
layout: step
number: 10
title: div i span
permalink: step10/
---

Wrócimy teraz na moment do HTML i przyjrzymy się bliżej dwóm znacznikom, które są naprawdę przydatne przy pisaniu CSS. Są to `<div>` i `<span>`.

`<div>` to element blokowy ogólnego przeznaczenia. Div można użyć jako kontener dla podobnych treści. Grupowanie podobnej treści ułatwi późniejsze stylizowanie za pomocą CSS danych elementów. Oczywiście możemy ustawić ramkę, odstępy, marginesy i kolory dla `<div>`.

`<span>` możemy nazwać liniową wersją `<div>`.

Teraz dowiesz się jak ich używać:

## Używanie `<div>`

Jeśli spojrzysz na nasze strony z przepisami, to zauważysz, że tekst jest w pewnym odstępie od białego obszaru, czyli naszego `<body>`. Chcemy dokonać zmian, aby `<h2>`, nasze podtytuły zaczynały się zaraz od `<body>`. Na chwilę obecną przeszkadza w tym wartość `padding`, czyli odległość zawartości od krawędzi body, tzw. margines wewnętrzny.

Zaktualizujmy więc nasz CSS i ustawimy lewe i prawe `padding` w `<body>` na 0.


<!--- Moglibyśmy po prostu usunąć padding, ale my zmienimy wartość prawą i lewą na zero. W końcu użytkownik może korzystać z  przeglądarki, która nie ma przewiduje zerowej wartości `padding` dla body.  --->

```css
body {
  margin: 20px auto;
  max-width: 800px;
  background-color: rgb(255, 255, 255);
  padding: 20px 0px;
  font-family: sans-serif;
}
```
Zapisz i odśwież. Na pewno zauważysz, że nasze nagłówki przesunęły się do początku lewej krawędzi body, tak jak chcieliśmy. 

![Headings span entire body](../assets/css-no-side-padding.png){:title="Headings span entire body" class="img-responsive imgbox"}

Ale pojawił się nowy problem. Cała reszta zawartości też jest skierowana do lewej bez żadnego odstępu. Chcieliśmy wprowadzić zmiany tylko dla nagłówka...

Tutaj może nam pomóc umiejętne wykorzystanie `<div>`.

Umieśćmy wszystko, co będzie miało odstęp od lewej do `<div>` z klasą `container`. Zacznijmy od pliku muffins.html i umieścimy w `<div>` odnośnik do strony głównej, tytuł i opis przepisu.

```html
<body>
  <div class="container">
    <a href="index.html">Home</a>

    <h1>Muffins</h1>

    <p>This recipe makes 12 plain muffins.</p>

    <p>Refer to directions at the bottom for how to modify the recipe for different types of muffins.</p>
  </div>
```

Dodajmy teraz styl `div.container` do naszego CSS:

```css
div.container {
  padding: 0px 20px;
}
```

Odśwież. Pierwsza część tekstu naszego pliku muffins.html powinna być osunięta od krawędzi.

Teraz dodamy `<div>` o klasie `container` osobno dla sekcji ingredients, method i variations.

Dla przykładu, tak to powinno wyglądać dla sekcji ingredients:

```html
<h2 class="recipepart ingredients">Ingredients:</h2>
<div class="container">
    <ul>
     <li>2 cups white flour</li>
     <li>1 tablespoon baking powder</li>
     <li>1/2 teaspoon salt</li>
     <li>2 tablespoons sugar</li>
     <li>1 egg, slightly beaten</li>
     <li>1 cup milk</li>
     <li>1/4 cup melted butter</li>
   </ul>
</div>
```

Zaktualizuj każdą z sekcji (zarówno na stronie cupcakes, jak i muffins) tak aby nasza zawartość była oddalona od krawędzi a podtytuły zaczynały się od krawędzi.

![Headings span, div content doesn't](../assets/css-extra-internal-padding.png){:title="Headings span, div content doesn't" class="img-responsive imgbox"}

Powinno wyglądać tak jak zaplanowaliśmy. Wróćmy do strony głównej... Nie mamy odstępów. Nie wygląda najlepiej.

![Homepage without padding](../assets/css-broken-homepage.png){:title="Homepage without padding" class="img-responsive imgbox"}

Ale wiemy jak to łatwo naprawić. Dodaj `<div>` z klasą `container` wokół wszystkich treści, dla których chcemy ustawić odstęp:

```html
<body>
  <div class="container">
    <img src="tinycakes.png" title="Tiny Cakes!" alt="The Tiny Cakes logo, a stylized cartoon cupcake." height="128px" width="128px" />
    <h1 id="sitetitle">Tiny Cakes!</h1>
    <p>
      Welcome to <em>my</em> recipes web site all about <strong>Tiny Cakes!</strong>
    </p>
    <p>
    Here are the recipes that we have:
    </p>
    <ul>
      <li><a href="traditional-cupcakes.html">Traditional Cupcakes</a></li>
      <li><a href="muffins.html">Muffins</a></li>
    </ul>
  </div>
</body>
```

![Homepage with a div](../assets/css-fixed-homepage.png){:title="Homepage with a div" class="img-responsive imgbox"}

Znacznie lepiej.

`<div>` to taki zbiornik, który pozwala Ci umieszczenie w nim elementów dla których chcemy ustalić konkretny styl. Jest bardzo przydatny.

## Używanie `<span>`

`<span>` jest trochę podobny do `<div>`, ponieważ jest to również element ogólnego przeznaczenia, ale liniowy a nie blokowy jak `<div>`. Możesz użyć `<span>` do określenia stylu dla konkretnego fragmentu tekstu.

Wykorzystamy znacznik <span> do stworzenia specjalnego formatowania temperatur w przepisach.

Dodaj poniższy CSS:

```css
span.temp {
  font-weight: bold;
  border: 2px solid red;
  background-color: pink;
  border-radius: 15px;
  padding: 5px 8px 4px 8px;
}
```

Teraz dodaj `<span>` o klasie `temp` wszędzie, gdzie w tekście pojawia się temperatura.

W ten sposób:

```html
<li>Preheat oven to <span class="temp">200°C</span> or <span class="temp">180°C</span> fan-forced.</li>
```

![Fancy temperatures](../assets/css-fancy-temperatures.png){:title="Fancy temperatures" class="img-responsive imgbox"}

Możesz dodać określony styl dla konkretnego tekstu. Wystraczy, że wrzucisz między znaczniki `<span>` i `</span>`, nadasz klasę i napiszesz styl dla danej klasy w CSS.
