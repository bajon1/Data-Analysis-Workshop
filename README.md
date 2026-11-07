# Warsztaty analizy danych

[![Otwórz w Colabie](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/main/notebooks/workshop.ipynb)

Kliknij **Open In Colab**, przeczytaj wstęp i uruchom pierwszą komórkę z kodem. Pobierze ona wszystkie pliki repozytorium do Twojego środowiska Colaba, w tym moduły pomocnicze. Każda osoba pracuje niezależnie; nie trzeba ręcznie kopiować plików, aby zacząć.

Warsztaty analizy danych dla osób związanych z psychologią, przygotowane na [Brainhack Kraków 2026](https://brainhackkrakow.org). Zakładamy znajomość podstaw rozumowania statystycznego. Wcześniejsze doświadczenie w programowaniu nie jest wymagane.

Kurs wykorzystuje Google Colab i publiczną [ankietę OSMI dotyczącą zdrowia psychicznego w branży technologicznej](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey). Notebook pobiera plik `survey.csv` z Kaggle podczas zajęć; repozytorium nie zawiera zbioru danych. Autorzy opisują zbiór jako ankietę z 2014 roku i udostępniają go na licencji CC BY-SA 4.0.

Ćwiczenia dotyczą sześciu pytań o miejsce pracy: `remote_work`, `self_employed`, `benefits`, `care_options`, `wellness_program` i `seek_help`. Płeć, dane demograficzne, historia rodzinna, historia leczenia i komentarze tekstowe nie wchodzą do tabeli ćwiczeniowej. Pełny słownik opisuje wszystkie kolumny źródłowe.

Kurs zaczyna się od **części 0: przygotowanie**. **Część 1** pokazuje, jak czytać krótkie polecenia, wybierać kolumny po nazwach lub pozycjach i filtrować wiersze. **Część 2** dotyczy braków danych i sprawdzania liczebności odpowiedzi. **Część 3** obejmuje wykresy słupkowe, procenty, porównywanie grup i krótką galerię wykresów do modyfikowania. **Część 4** pokazuje maskowanie wymyślonego tekstu za pomocą regex oraz rozpoznawania osób i miejsc z kontekstu. **Część 5** porównuje znaczenie słów, a następnie wymyślonych komentarzy z jednym pozytywnym i jednym negatywnym przykładem, bez ręcznego wypisywania słów kluczowych.

W kursie jest **8 ćwiczeń**, ponumerowanych od 1 do 8. Każde ma opis, podpowiedź, przykład i komórkę z poleceniem. Zadania po części 1 i na końcu części 2 łączą poznane operacje. Pełny słownik kolumn można rozwinąć w razie potrzeby. Wersja warsztatowa pozostawia zadania do wykonania; osobny notatnik zawiera odpowiedzi i pomaga wrócić do pracy po pominięciu fragmentu zajęć.

## Wymagania

- laptop;
- stabilne połączenie z internetem;
- konto Google;
- współczesna przeglądarka internetowa.

Nie trzeba instalować Pythona na własnym komputerze.

## Materiały

- [Notatnik warsztatowy — zadania do wykonania](notebooks/workshop.ipynb)
- [Notatnik z odpowiedziami — kompletne rozwiązania](notebooks/workshop_solutions.ipynb) · [otwórz odpowiedzi w Colabie](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/main/notebooks/workshop_solutions.ipynb)

Obie wersje utrzymujemy równolegle: każda zmiana programu, opisów lub ćwiczeń trafia także do notatnika z odpowiedziami.

Materiały można też udostępniać przez wspólny [folder materiałów warsztatowych](https://drive.google.com/drive/folders/1ijaY-LXx4DGp8ZrUz9KOmUY6Drk4mSBJ?usp=sharing).

## Uruchomienie w Google Colab

1. Kliknij **Open In Colab** u góry tego README.
2. W razie potrzeby zaloguj się na własne konto Google.
3. Przeczytaj wstęp i uruchom pierwszą komórkę z kodem, aby pobrać repozytorium. Następnie wykonuj komórki po kolei przyciskiem obok nich lub skrótem `Shift+Enter`.

Komórka przygotowawcza pobiera pliki potrzebne do warsztatów. Dzięki temu możemy korzystać także z kodu pomocniczego, np. pliku `nbutils.py`, przez zapis `import nbutils`. Pobierana jest wersja z gałęzi `main` na GitHubie. Ponowne uruchomienie komórki zachowuje pliki istniejące już w danej sesji.

Aby zachować własne zmiany po zakończeniu sesji, możesz wybrać **Plik → Zapisz kopię na Dysku** (**File → Save a copy in Drive** w angielskim interfejsie). Otwarcie notebooka z GitHuba nie zapisuje automatycznie kopii na Twoim Dysku.

Osobna komórka w części 0 instaluje `kagglehub`, pobiera `survey.csv` z Kaggle i odczytuje go do tabeli pandas. Bezpośrednio pod nią znajduje się słownik kolumn źródłowych. Kolejna komórka z kodem wybiera wyłącznie sześć kolumn ćwiczeniowych, zanim wyświetli jakiekolwiek wiersze. Ponowne uruchomienie lub odłączenie środowiska usuwa pliki tymczasowe, dlatego po połączeniu uruchom ponownie przygotowanie modułów i pobieranie danych.

Przykład rozpoznawania osób i miejsc w części 4 pobiera angielski model spaCy. Jeśli pobieranie lub instalacja są niedostępne, osoba prowadząca może omówić pokazane zdanie i schemat zamiany bez wykonywania tej demonstracji.

Część 5 instaluje `sentence-transformers` i pobiera model obsługujący wiele języków. Pierwsze uruchomienie może potrwać dłużej. Większe podobieństwo do przykładu nie jest procentem pewności ani gwarancją poprawnej oceny komentarza. Pokaz korzysta wyłącznie z wymyślonych wypowiedzi; liczba ćwiczeń pozostaje równa 8.

## Sprawdzenie przed zajęciami

Przed wydarzeniem uruchom nowe środowisko Colaba i sprawdź, czy:

1. pobieranie z Kaggle kończy się bez żądania danych logowania lub niespodziewanej dodatkowej zgody;
2. plik `survey.csv` się wczytuje i zawiera sześć kolumn ćwiczeniowych;
3. części 0–3 działają: wybieranie danych, obsługa braków, liczebności, procenty i wykresy grupowe;
4. model spaCy z części 4 daje się zainstalować i rozpoznaje osobę oraz miasto w wymyślonym zdaniu;
5. dwie kolejne komórki części 5 pokazują podobieństwo słów i porównanie wymyślonych komentarzy z dwoma wzorcami;
6. notatnik z odpowiedziami działa od początku, a wersja warsztatowa zawiera przykłady i miejsca na własne rozwiązania.

## Ochrona danych i granice interpretacji

Dane z Kaggle służą wyłącznie jako publiczny materiał warsztatowy. Uczestnicy zgłaszali się do ankiety samodzielnie: wykresy opisują ich odpowiedzi i nie ustalają częstości występowania zaburzeń w populacji, diagnoz ani skutków przyczynowych. Opisana w słowniku źródłowym kolumna `treatment` oznacza deklarowane szukanie leczenia, a nie diagnozę; nie wykorzystujemy jej w ćwiczeniach.

Praca z rzeczywistymi danymi badawczymi wymaga osobnej decyzji dotyczącej zgód, zasad instytucji, zatwierdzonej infrastruktury, uprawnień dostępu, czasu przechowywania i ryzyka ujawnienia. Ani pseudonimizacja, ani automatyczne wykrywanie danych identyfikujących nie sprawiają automatycznie, że zbiór można bezpiecznie przesłać do zewnętrznego LLM. Przykłady tekstowe są wymyślone i nigdy nie wykorzystują komentarzy respondentów.
