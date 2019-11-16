---
layout: step
number: 0
title: Czym jest sieć web?
permalink: step0/
---

## Co będziemy dzisiaj robić?

Celem dzisiejszych warsztatów jest nauczenie się jak tworzyć strony www.

W tym celu użyjemy dwóch języków komputerowych:

- HTML (HyperText Markup Language po polsku hipertekstowy język znaczników), oraz
- CSS (Cascading Style Sheets czyli kaskadowe arkusze stylów)

Strony internetowe mogą zawierać wiele innych elementów, które nie będą elementami języka HTML lub CSS np. obrazy, dźwięk audio czy też skrypty kodu takiego jak JavaScript. Póki co, do stworzenia prostej strony wystarczy Ci tylko HTML i CSS.

Zanim jednak przejdziemy do nauki wcześniej wspomnianych języków poświęćmy chwilę na upewnienie się czy rozumiemy dane pojęcia.

## Web (WWW, W3, World Wide Web)

Porozmawiajmy na początku o sieci Web oraz samym Internecie.

My wszyscy korzystamy z sieci Web:
wpisaliśmy adres w oknie przeglądarki (Firefox, Internet Explorer) by otworzyć daną stronę i kliknęliśmy w link, który przekierował nas do relewantnej podstrony.

Ale czy wiesz jak to wszystko wygląda od kuchni? Co dokładnie się dzieje kiedy klikasz w link bądź otwierasz daną stronę w przeglądarce?

Mimo, że nasze działania wydają się być banalne to tak naprawdę w naszym komputerze dzieje się sporo!

Ale dobra wiadomość jest taka, że nie musisz dokładnie wszystkiego wiedzieć :)

Potrzebujesz jedynie wiedzieć jak mniej-więcej działa sieć WWW by zacząć tworzyć swoje własne strony.

Resztę rzeczy można poznawać stopniowo np. gdy w procesie nauki pojawi się jakiś błąd bądź masz pomysł i nie wiesz jak go zrealizować.

Nie trzeba od razu uczyć się wszystkiego. Poznawanie nowych pojęć stopniowo, kiedy są one potrzebne, jest częścią pracy developera.

## Jak działa sieć?

W bardzo dużym uproszczeniu, sieć działa w ten sposób:

1. Pytasz swoją przeglądarkę o daną stronę www.
2. Twoja przeglądarka wysyła żądanie dotyczące tej strony wwww do odpowiedniego komputera w Internecie.
3. Dany komputer odsyła stronę internetową z powrotem do Twojego komputera.
4. Twoja przeglądarka odbiera stronę internetową i wyświetla ją dla Ciebie.

Omówimy to teraz bardziej szczegółowo.

### 1. Zadajesz zapytanie odnośnie danej strony.

Zwykle wpisujesz adres strony internetowej w przeglądarce lub klikasz w link (zawierający jakiś adres), aby wysłać żądanie o daną stronę internetową.

Adres strony internetowej nazywamy **URL**, co jest rozwinięciem skrótu Uniform Address Locator. Po polsku tłumaczymy to jako Jednolity Lokalizator Zasobów.

Każdy adres URL składa się z trzech części:

1. Z **protokołu** czyli sposóbu wysłania strony internetowej. W przypadku stron internetowych jest to zwykle **http** lub **https**.
2. Z **hosta (nazwy serwera)** czyli nazwy komputera, który zawiera żądaną stronę.
3. Z **ścieżki do zasobu** czyli lokalizacji strony na komputerze, na którym jest zapisana.

### 2. Twoja przeglądarka wysyła zapytanie o daną stronę do innego komputera

Części składowe adresu URL zapewniają Twojej przeglądarce wszystkie potrzebne informacje aby ta wysłała żądanie o zapytana stronę do odpowiedniego komputera. Komputery, które zawierają informację o danych stronach i dostarczają informację o nich na żądanie nazywamy serwerami sieci Web. (dopisek -) Taki komputer-serwer jest podłączony na stałe do sieci.

Przeanalizujmy adres URL strony Node Girls Brisbane `http://nodegirls.com.au/brisbane.html`:

W tym przypadku naszym protokołem jest `http`, `nodegirls.com.au` odpowiada nazwie serwera, natomiast końcówka `/brisbane.html` zawiera informacje o ścieżce do zasobu. Innymi słowy, serwer sieci Web o nazwie `nodegirls.com.au` przesłał do nas plik `brisbane.html` za pomocą protokołu `http`.

Protokół to umowny zbiór zasad. W tym przypadku oznacza zbiór zasad opisujących sposób wysyłania żądań na temat stron web i odpowiedzi na te żądania. To ** http ** je określa, a ** https ** rozszerza ten protokół o obsługę zabezpieczeń.

Spójrz teraz na pasek adresu swojej przeglądarki.
Czy potrafisz teraz powiedzieć, jakie są poszczególne części adresu URL strony, którą aktualnie właśnie czytasz?

### 3. Inny komputer odsyła stronę www.

Jeśli serwer sieci Web posiada plik strony www o którą zapytała Twoja przeglądarka, to dany plik zostanie wysłany do okna Twojej przeglądarki.

W innym wypadku, zostaniesz przekierowana na stronę z informacją o błędzie. 

### 4. Twoja przeglądarka otrzyma informacje o stronie web i wyświetli ją dla Ciebie.

Większość stron napisana jest w dwóch językach komputerowych o których wspomnieliśmy na początku.

Twoja przeglądarka odczytuje język HTML i CSS na stronie. Stosuje się do ich zasad i wyświetla stronę, którą widzisz.

## Nic skomplikowanego, prawda?

Przykład, który omówiliśmy był dosyć prosty - serwer posiada plik z daną stroną web i wysyła go do Ciebie za każdym razem, gdy o niego poprosisz.

Tak naprawdę serwer sieciowy nie zawsze ma gotowe pliku dla każdego żądanego adresu URL.

Czasami serwery internetowe używają specjalnego oprogramowania do sprawdzania przychodzących żądań przeglądarki i tworzenia stron internetowych dla każdego konkretnego żądania na bieżąco. Jednak dzisiaj nie zamierzamy się zajmować takimi przypadkami. Zaczniemy od zbudowania kilku prostych stron.

<!-- To może brzmieć skomplikowanie i fantazyjnie ale w rzeczywistości sposób działania jest najczęściej podobny do [mail-merge](https://en.wikipedia.org/wiki/Mail_merge) ;) -->

## Uprośćmy to jeszcze bardziej!

Na dzisiejszych warsztatach zrobimy coś odmiennego.

Stawianie własnego serwera może być trochę zbyt skomplikowane. Na szczęście przeglądarki umożliwiają otwieranie plików, które znajdują się lokalnie, na dysku Twojego komputera. Kiedy wykonujemy taką operację korzystamy z protokołu **file**. Zauważysz to w adresie URL, gdy zaczniemy warsztat!

Protokół będzie jedyną rzeczą, którą zamierzamy zmienić.
Podstawowy HTML i CSS będą dokładnie takie same.

Gotowi? Zaczynamy!
