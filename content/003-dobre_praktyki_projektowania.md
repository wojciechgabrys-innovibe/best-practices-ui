# Dobre praktyki projektowania

### Format

Przekazując pliki lub dostęp do projektów w chmurze upewnijmy się, że developer (który w przyszłości ma na nich pracować) będzie w stanie je otworzyć.

Wykorzystujemy rozwiązania typu <em>cloud-based</em>, takie jak [Figma](https://figma.com), [Adobe XD](https://www.adobe.com/products/xd.html), [Sketch Cloud](https://www.sketch.com/), czy [Zeplin](https://zeplin.io/) lub [Invision](https://www.invisionapp.com/) (zamiast Photoshopa, którego uruchomienie np. na Ubuntu jest w najlepszym wypadku bardzo problematyczne).

Jeśli skorzystanie z w/w aplikacji nie jest możliwe, skontaktuj się z osobą, która  przekonwertujmy projekty do formatu, który odbierający będzie mógł otworzyć na swoich urządzeniach.

Z Photoshopa korzystamy tylko i wyłącznie, kiedy klient tego wymaga, w innym wypadku zawsze wybieramy narzędzie, które jest stworzone z myślą o UI/UX.

### Zanim odpalisz Figmę, Sketcha, czy Photoshopa

**Skup się na celach biznesowych i rozwiązywaniu problemów.** W początkowych etapach trwania projektu wyekstrahowanie informacji od klienta i przygotowanie architektury informacji są o wiele ważniejsze od docelowych kolorów i perfekcyjnie zaprojektowanych komponentów.

**Zacznij od lo-fi.** Projektowanie na papierze (np. Post-its), tablicy suchościeralnej, czy w narzędziach do budowy wireframe’ów pozwala na szybsze iteracje. Zmiany na tym etapie (w porównaniu z dalszymi, gdy większość kluczowych funkcjonalności będzie już zaprogramowana) są relatywnie tanie. Pamiętaj, aby wytłumaczyć klientowi, że to co widzi nie jest odzwierciedleniem ostatecznej jakości, a ma na celu oszczędzenie jego czasu i pieniędzy.

## Organizacja projektu

**Ekrany/artboardy powinny być uporządkowane.** Decyzję o tym czy powinny być ułożone tematycznie (np. wszystkie ekrany związane z profilem użytkownika ustawione blisko siebie), czy logicznie (sekwencja ekranów odpowiadająca za flow płatności) czasami zależy od specyfiki projektu i pozostawiamy ją projektantowi.

Decyzję o tym czy ekrany responsywne (mobile, tablet, desktop) powinny być ułożone obok siebie, czy być pogrupowane rozmiarami na osobnych stronach pozostawiamy projektantowi i zespołowi – czasami ta sama osoba wdraża je wszystkie, a innym razem powstają odrębne aplikacje (np. web i React Native), które wdrażają różne osoby (i wygodniej jest im się obracać tylko w ramach swoich zadań). Najważniejsza jest tu wygoda zespołu i konsekwencja.

Dobrym zabiegiem jest dodanie dużych nagłówków (ok. `200pt`) opisujących grupy ekranów – dzięki temu robiąc zoom out (aby zobaczyć wszystkie widoki) łatwiej odnajdujemy się w projekcie.

**Pamiętajmy, aby ukończone ekrany dokładnie nazywać.** Pomaga to w ich wyszukiwaniu i przeglądaniu. O ile w przypadku kilkunastu ekranów nawigowanie nawet po nieopisanych ekranach jest to łatwe, o tyle w przypadku projektów posiadających po kilkaset widoków konsekwencja w nazewnictwie zaprocentuje i ułatwi pracę wszystkim osobom zaangażowanym w proces tworzenia produktu.

**Projektuj nowe widoki w miejscu z dala od już gotowych.** W przypadku narzędzi pozwalających na kolaborację, staraj się wydzielić obszar zawierający już ukończone widoki (np. używając Pages w przypadku Figmy i Sketcha). Pozwoli to uniknąć nieporozumień które z ekranów są już gotowe, a nad którymi jeszcze trwają prace.

**Uporządkuj skończone ekrany.** Dobrą praktyką jest uporządkowanie warstw (nazwy opisujące ich zawartość, ułożenie ich w kolejności występowania na artboardzie) i grup (nazwy opisujce ich zawartość, usunięcie niepotrzebnych zagnieżdżeń) przed oddaniem ekranu do cięcia.

Pluginy ułatwiające ten proces:

* Figma: [Clean Document](https://www.figma.com/community/plugin/767379019764649932/Clean-Document)
* Sketch: [Cleanup Useless Groups](https://sketchelements.com/plugins/cleanup-useless-groups-sketch-plugin/)

**Interaktywne elementy interfejsu i przejścia pomiędzy ekranami.** Jeśli program graficzny w którym przygotowujemy materiały nam na to pozwala (np. Figma, Sketch), warto poświęcić czas na zamarkowanie interakcji poszczególnych elementów interfejsu (np. kliknięcie w przycisk powoduje przejście do kolejnego ekranu lub pojawienie się pop up'u). Dzięki temu będziemy w stanie:

* Samodzielnie odkryć brakujące ścieżki użytkowników
* Dostarczyć klientowi *prototyp* aplikacji, co pozwoli mi na zweryfikowanie poprawności pierwotnych założeń i ewentualną szybką zmianę kursu zanim projekt trafi do wdrażania
* Dostarczyć programistom dodatkowy poziom informacji (w postaci interaktywnej dokumentacji), co zdecydowanie ułatwi im wybór.

Nie wszystkie interakcje można bez problemu wykonać i przedstawić w programie graficznym. Warto wtedy (w formie np. komentarza) podać link do interaktywnego rozwiązania, które jest online z przykładem, który w prosty sposób zobrazuje daną funkcjonalność.

## Style, komponenty, grupy, frame’y i autolayout

**Gdzie i kiedy warto je wdrożyć.** Im bardziej Twój projekt się rozrasta, tym trudniej nad nim zapanować. W średnich i większych projektach kluczem do utrzymania porządku jest dyscyplina i korzystanie z dobrodziejstw nowoczesnych narzędzi (takich jak style, komponenty, grupy, warianty, frame’y i autolayout). W mniejszych (gdzie np. musisz dorobić tylko 2-3 ekrany do rozwijanej już aplikacji) nie warto tracić czasu na szczegółowe definiowanie komponentów – lepiej jest zdefiniować powtarzalne sekcje jako komponenty (np. header czy footer). W przypadku konieczności zmiany na tych elementach musimy to robić tylko w jednym miejscu (zazwyczaj pierwszy frame). Decyzję pozostawiamy Tobie.

**Nie staraj się jednak wdrażać ich wszystkich na siłę już od pierwszych godzin projektowania.** Takie podejście Cię spowolni i ograniczy możliwości iterowania. Zacznij porządkować (artboardy, grupy i warstwy) dopiero wtedy, gdy poczujesz, że projekt zmierza w dobrym kierunku, a z zaprojektowanych da się wyodrębnić małe powtarzalne elementy (np. przyciski, czy pola formularzy).

**Inwestycja w style i komponenty oszczędzi Ci czas.** O ile ich tworzenie bywa nudne i mozolne, to ostatecznie pozwoli Ci na utrzymanie spójności (te same elementy na przestrzeni całego projektu będą wyglądały tak samo), ułatwi wprowadzanie globalnych zmian (w przypadku gdy np. klient zażyczy sobie zmianę koloru wszystkich przycisków) i umożliwi szybkie tworzenie kolejnych ekranów (niczym budowanie z klocków LEGO).

**Nie zostań niewolnikiem komponentów i wariantów.** Fajnie jest mieć pojedynczy komponent z którego można zrobić input, pole tekstowe (z wieloma linijkami tekstu), czy dropdown, ale im więcej cech będziemy chcieli do niego dodać (etykiety, teksty pomocy, komunikaty błędu, stan hover, disabled, etc.), tym trudniej będzie nam je wszystkie pogodzić i uniknąć błędów podczas ich wykorzystywania. W tego typu przypadkach należy rozważyć wady i zalety różnych rozwiązań – czasami łatwiej, szybciej i wygodniej jest przygotować dwie osobne wersje komponentu zamiast walczyć z jego wariantami.

**Nie ograniczaj się do tworzenia wyłącznie prostych komponentów.** Z czasem zauważysz coraz więcej elementów układających się w większe, powtarzające się moduły (np. grupy przycisków akcji pod formularzami, dropdowny, etc.), które będzie można wyekstrahować i okiełznać używając autolayoutu. Posiadanie dużych klocków (takich jak np. cały navbar, wraz z logo, linkami, avatarem i przyciskiem do wylogowania) pozwoli Ci nie tylko na szybsze tworzenie nowych ekranów, ale także na ich modyfikację z jednego miejsca (np. gdy klient zażyczy sobie nowego linku w menu) – dobrym punktem odniesienia jest metodologia Atomic Design. Tworząc większe komponenty (np. całe pole formularza, wraz z etykietą i dopiskiem z informacją pod polem) warto definiować je tak, aby składały się już z istniejących (mniejszych) komponentów, miały odpowiednio zdefiniowane odstępy i korzystały z auto layout (aby układ dopasowywał się automatycznie wraz ze zmianą któregokolwiek z child-components).

**Dodatkowe materiały:**
* [https://www.figma.com/best-practices/groups-versus-frames/](https://www.figma.com/best-practices/groups-versus-frames/)

## Grid

Mówiąc o gridzie mamy zwykle na myśli strukturę kilkunastu kolumn (a czasem też rzędów) o zdefiniowanych szerokościach i odstępach między nimi (w przeciwieństwie do ciągnącej się w nieskończoność siatki o jednolitych oczkach), w obszarze których będziemy starali się układać elementy interfejsu użytkownika.

**Staraj się korzystać z wymiarów (liczba kolumn, szerokość kolumn, szerokość odstępów pomiędzy kolumnami) zdefiniowanych we frameworkach** (np. Boostrap, Material Design, czy Tailwind CSS), z których będą korzystali developerzy tego projektu – powinniście to ustalić na spotkaniu otwierającym projekt. Nawet jeśli developer nie zamierza korzystać z całego Bootstrapa, może on z łatwością wyciągnąć z niego sam grid i na nim oprzeć układ strony (pisząc resztę styli samodzielnie).

**Zaprojektuj swój grid.** Jeśli powszechnie dostępne rozwiązania nie spełniają Twoich potrzeb/oczekiwań (np. gdy musisz umieścić na stronie banner o egzotycznych wymiarach, lub odtwarzacz wideo o konkretnym współczynniku proporcji), skonstruuj własny układ. Zalecamy oparcie go na układzie 12 kolumn (najpopularniejszy układ, ponieważ łatwo dzieli się na 1, 2, 3, 4, 6 i 12 równych kolumn), lub ewentualnie 16 kolumn (dzieli się na 1, 2, 4, 8, 16 równych kolumn). W sieci znajdziesz wiele tzw. Grid calculators, które w wizualny sposób ułatwią Ci znalezienie odpowiednich wymiarów kolumn i odstępów (tak, aby zmieścić się w najpopularniejszych szerokościach widoków responsywnych).

**Trzymaj się gridu.** Układanie elementów interfejsu wewnątrz kolumn ułatwi developerom pracę i pozwoli im na dokładniejsze oddanie Twojej wizji w docelowym produkcie.

**Nie bój się sporadycznego łamania zasad.** Ciągłe trzymanie się grida może spowodować, że projekty będą “przewidywalne” i “nudne”. Aby tchnąć w nie więcej życia i dynamiki można czasami wyjść poza grid (np. grafiką, albo cytatem blokowym). Pamiętaj przy tym, aby tego typu zabiegi były przemyślane (by developer był w stanie je zreprodukować np. korzystając z pozycjonowania absolutnego i wartości procentowych) i robione ze smakiem.

**Na stronie może być więcej niż jeden grid.** Pamiętaj, że nie ogranicza Cię wyłącznie główny grid. Każdy kontener (np. boczna kolumna, czy główna szpalta) może mieć swój wewnętrzny grid (np. jeśli główna kolumna składa się z 7/12 kolumn, nic nie stoi na przeszkodzie, aby te 7 kolumn podzielić znów na 12). Zwróć tylko uwagę, czy takie proporcje dobrze ze sobą współgrają wizualnie.

**Grid horyzontalny.** Poza zdefiniowaniem 12 kolumn (zwykle o stałej szerokości), warto jest dodatkowo włączyć powtarzające się w nieskończoność kolumny w trybie horyzontalnym (zalecamy paski po `8px` z odstępami `8px`, ewentualnie `4px`/`4px`, choć bardziej zaciemnia to obszar projektowania). Taki zabieg pozwala na łatwiejsze zapanowanie nad odstępami pomiędzy elementami i nadaje całości wertykalny rytm.

Po zdefiniowaniu bazowego rozmiaru fontu jako `16px` (`1em`), developer może łatwo korzystać z okrągłych wartości relatywnych jednostek do definiowania odstępów (`8px=0,5em`, `32px=2em`, etc.).

Nowoczesne frameworki opierają swoje systemy odstępów właśnie na systemach `4px` (w Tailwind CSS `m-1` odpowiada margin: `4px`) lub `8px` (oczko siatki w Material Design), a korzystanie z ich wielokrotności ułatwi pracę developerom przy wdrażaniu tak przygotowanych projektów.

Dla ułatwienia sobie pracy, warto przestawić tryb dużego nudge (`SHIFT` + strzałki) z `10px` na `8px` – w Sketchu (Preferences → Canvas), a w Figmie (Preferences → Nudge amount).

Dodatkowe materiały:

* [https://bradfrost.github.io/this-is-responsive/patterns.html](https://bradfrost.github.io/this-is-responsive/patterns.html)
* [http://gridcalculator.dk/](http://gridcalculator.dk/)
* [https://uxdesign.cc/responsive-grids-and-how-to-actually-use-them-970de4c16e01](https://uxdesign.cc/responsive-grids-and-how-to-actually-use-them-970de4c16e01)
* [https://designsystemsrepo.com/design-systems/](https://designsystemsrepo.com/design-systems/)

## Typografia i teksty

**Body text = 16px.** Przy obecnych rozmiarach i rozdzielczościach ekranów przyjęło się aby ustawiać podstawowy rozmiar tekstu (tzw. body text, od rozmiaru fontu ustawionego dla elementu `<body>`) i nie schodzić poniżej tej wartości

Ustawienie mniejszego rozmiaru może spowodować problemy:
* niepotrzebny zoom-in na urządzeniach mobilnych (np. iPhone) po tapnięciu tekstu w takim rozmiarze,
* błędy w Google Search Console (mówiące o mało czytelnym tekście), co w dłuższej perspektywie może negatywnie wpłynąć na Page Rank strony.

**Ogranicz liczbę fontów (i ich wag) na stronie.** Korzystanie z wielu różnych krojów na jednej stronie obniża czytelność treści (wprowadzając chaos) i powoduje wydłużenie jej ładowania.

**Unikaj skrajnych wariantów wagowych.** Pomijając miejsca takie jak key visuale, splash screeny, czy inne sporadyczne miejsca (w których chcesz osiągnąć zamierzony efekt wizualny oparty np. na wielkich literach o cienkich liniach), staraj się nie używać skrajnych wariantów wagowych fontów (takich jak thin, extrabold, czy ultra).

**Zmieniając wagę fontu przeskakuj o 2 kroki.** Aby uniknąć nieporozumień (czy to normal/medium, lub semibold/bold) pomijaj wagi i używaj par, które nie są sąsiadami, np. Extralight(200)/Normal(400), Medium(500)/Bold(700), lub Normal(400)/Bold(700).

**Nie zmieniaj wagi dla stanu hover.** W przypadku gdy stan normalny i hover będą miały różne wagi, wersja podświetlona kursorem stanie się dłuższa (efekt nasila się wraz z długością linku), co może spowodować “pływanie” sąsiednich elementów a nawet rozbicie układu strony.

**Szpalta tekstu powinna mieć pomiędzy 60 a 80 znaków.** Dłuższe linijki powodują trudności w śledzeniu tekstu wzrokiem (odnajdywanie początku kolejnej linii tekstu), natomiast krótsze zaburzają naturalną płynność rytmu czytania. Łatwym sposobem określenia optymalnej szerokości kolumny lanego tekstu jest trzykrotne wypisanie wszystkich małych liter angielskiego alfabetu (78 znaków).

**Wyznaczanie górnej i dolnej krawędzi linii tekstu.** Najwyższą z powszechnie stosowanych liter jest Å (U+00C5), natomiast najniższą jest y (pomijając znaki specjalne składane przy pomocy ligatur systemu Unicode).

**Rytm wertykalny.** W celu poprawy czytelności tekstu i uczynienia jego składu bardziej estetycznym warto zadbać o proporcjonalny rytm wertykalny. Pomaga przy tym włączenie poziomych kolumn (opisanych w sekcji Grid horyzontalny) i ustalenie wysokości linii wszystkich tekstów jako wielokrotności tego gridu. Teoria i przykłady:

* [https://zellwk.com/blog/why-vertical-rhythms/](https://zellwk.com/blog/why-vertical-rhythms/)
* [https://betterwebtype.com/articles/2018/10/15/rhythm-in-web-typography/](https://betterwebtype.com/articles/2018/10/15/rhythm-in-web-typography/)

**Hierarchia nagłówków.** Podobnie jak w przypadku doboru par wagowych, rozmiary poszczególnych poziomów pełnią bardzo ważną rolę w wizualnym uporządkowaniu informacji. Dobrze dobrane rozmiary i wagi poszczególnych poziomów spowodują, że użytkownik nie będzie miał wątpliwości na jakim poziomie treści się znajduje.

Wiele frameworków (np. Bootstrap, czy Tailwind CSS) posiada przemyślane i sprawdzone w bojach hierarchie nagłówków (i innych elementów typograficznych), które warto wykorzystać (chociażby jako punkt wyjścia w przypadku zmiany fontu na niestandardowy).

Jeśli jest to uzasadnione, nie bój się modyfikować istniejącej hierarchii lub tworzyć własnej. Przydatnymi narzędziami będą następujące kalkulatory:

* [https://www.gridlover.net/try](https://www.gridlover.net/try)
* [https://type-scale.com/](https://type-scale.com/)

**Unikaj Lorem ipsum.** Staraj się pracować na docelowych tekstach (a tam gdzie nie jest to możliwe, używaj zamienników – przykładem może być np. artykuł skopiowany z innej strony). Dzięki temu szybciej wyłapiesz ewentualne problemy i brakujące elementy (np. listy wypunktowane, czy cytaty blokowe).

**Tłumaczenie tłumaczeniu nie równe.** Projektując stronę, która ma pozwalać na przełączanie się pomiędzy różnymi wersjami językowymi, pamiętaj, że te same słowa w różnych językach mogą mieć różną długość (np. “FAQ” po francusku to “Questions Fréquemment Posées”, a “Cart” po niemiecku to “Einkaufswagen”, co może skutkować “rozjechaniem się” layoutu). Artykuł https://www.w3.org/International/articles/article-text-size.en zawiera przykładowe “mnożniki” długości słów różnych języków.

**Różne wersje językowe to nie tylko tłumaczenia.** Wraz z obsługą tłumaczeń warto zadbać również o odpowiednie formaty zapisu walut, liczb, dat, adresów i pól formularzy (np. w przypadku płatności).

**RTL to nie tylko odwrócenie kierunku tekstu.** Osoby korzystające z języków takich jak Arabski, czy Hebrajski oczekują, że cała strona będzie “odbita lustrzanie”.

**Dodatkowe materiały:**

* [https://charactercounttool.com/](https://charactercounttool.com/)
* [https://www.fontpair.co/](https://www.fontpair.co/)

## Dostępność

**Wyróżnij interaktywne elementy.** Wszystkie interaktywne elementy powinny być przejrzyście oznaczone (np. poprzez podkreślenie tekstu, dodanie cienia, użycie koloru akcentującego)

**Zaprojektuj stan hover.** Wszystkie interaktywne elementy powinny być dawać feedback po najechaniu na nie kursorem (np. poprzez wyświetlenie/ukrycie podkreślenia, zmianę koloru lub intensywności cienia).

**Odpowiedni poziom kontrastu.** Zgodnie z wytycznymi standardu `WCAG 2.1`, kontrast pomiędzy body text a tłem powinien wynosić conajmniej `4,5:1`, a dla nagłówków/większych tekstów `3:1`.

**Etykiety pól formularzy powinny być cały czas widoczne.** Nie ma przeciwwskazań przeciwko ich rozsądnemu animowaniu (jak ma to miejsce w przypadku Material Design). Nie powinno się ich natomiast usuwać/ukrywać, a w ich miejsce używać tekstu w placeholderach (ponieważ znika gdy tylko zaczniemy cokolwiek wpisywać w danym polu). Zadaniem placeholderów jest jedynie podpowiadanie użytkownikowi jakiego typu danych (i w jakim formacie) od niego oczekujemy.

**Dodatkowe materiały:**

* [https://webaim.org/resources/contrastchecker/](https://webaim.org/resources/contrastchecker/)

## Style guide

Omawiając to zagadnienie mamy na myśli dedykowany page lub artboard, gdzie znajdują się podobne do siebie komponenty (np. zestaw kolorów, hierarchia nagłówków, kontrolki formularzy, etc.). Pozwala to na łatwe wychwycenie ich wspólnych właściwości (np. podobieństwo fontów, obramowań i paddingów wewnątrz pól tekstowych, list) i utrzymanie spójności w projekcie. Osoba wdrażająca nasze projekty będzie wiedziała jak ma wyglądać zwykły input w różnych stanach (pusty, z treścią, z placeholderem, podświetlony kursorem, aktywny, zablokowany) i w różnych wariantach (zwykły input, input do wprowadzania kwoty w danej walucie, dropdown, etc.)

Dodatkowym atutem styleguide’u jest możliwość korzystania z niego jak z pudełka z klockami Lego – nowe ekrany tworzy się szybciej i pewniej (mając świadomość zachowania spójności z resztą projektu). W ekstremalnych przypadkach (np. nasza nieobecność) programista zaopatrzony w dobrze przygotowany style guide będzie sam w stanie zbudować brakujący moduł lub widok z posiadanych komponentów.
