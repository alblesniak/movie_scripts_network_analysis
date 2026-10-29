# movie_scripts_network_analysis

Notatniki do zajęć z humanistyki cyfrowej: analiza sieciowa i dialogowa scenariuszy filmowych. W każdym kroku czytasz, uzupełniasz albo piszesz prompt, przekazujesz go modelowi AI, wklejasz otrzymany kod do pustej komórki i porównujesz wynik z opisem w notatniku.

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/alblesniak/movie_scripts_network_analysis?quickstart=1)

## Szybki start w GitHub Codespaces

1. Zaloguj się na GitHub. Jeśli masz już fork tego repozytorium, otwórz go i kliknij **Sync fork**, żeby pobrać najnowsze notatniki.
2. Kliknij przycisk **Open in GitHub Codespaces** powyżej. Jeśli masz już codespace, przycisk zaproponuje powrót do niego. Pierwsze uruchomienie trwa kilka minut, bo instalują się biblioteki.
3. Otworzy się notatnik o sieci postaci. Pozostałe notatniki są w folderze `notebooks/` w panelu po lewej.
4. W prawym górnym rogu notatnika kliknij **Select Kernel** → **Python Environments** → pozycja oznaczona „Recommended”.
5. Komórki uruchamiasz trójkątem przy komórce albo klawiszami Shift+Enter, tak jak w Colab.

Wolisz wygląd klasycznego Jupytera? Na stronie [github.com/codespaces](https://github.com/codespaces) kliknij **…** przy swoim codespace i wybierz **Open in JupyterLab**.

## Zapisywanie pracy

- Pliki tworzone przez notatniki (CSV, GraphML, JSON) zapisują się w folderze `notebooks/`, obok notatników. Kolejne notatniki znajdują je automatycznie, nie trzeba ich pobierać ani wgrywać.
- Plik pobierzesz na komputer prawym przyciskiem w panelu po lewej → **Download**. Plik z komputera wgrasz, przeciągając go do tego panelu.
- Na koniec zajęć zapisz pracę: ikona **Source Control** po lewej → krótki opis zmian → **Commit** → **Sync Changes**. Jeśli pracujesz na repozytorium kursu, a nie na swoim forku, GitHub sam utworzy fork i zapisze w nim zmiany.
- Codespace zatrzymuje się po 30 minutach bezczynności. Na kolejnych zajęciach wróć do tego samego codespace (przycisk powyżej albo [github.com/codespaces](https://github.com/codespaces)), zamiast zakładać nowy.

## Klucz API (notatniki o emocjach)

Notatniki z modułu 3 potrzebują klucza do API modelu językowego. Najwygodniej zapisać go raz jako sekret Codespaces: zdjęcie profilowe → **Settings** → **Codespaces** → **New secret**. Nazwa `OPENROUTER_API_KEY` (wariant 02b) albo `OPENAI_API_KEY` (warianty 02 i 02a), wartość to Twój klucz, a w **Repository access** wybierz swoje repozytorium. Bez sekretu notatnik poprosi o klucz w okienku, które w VS Code pojawia się na górze ekranu.

## Zajęcia nic nie kosztują

- Codespaces ma darmowy miesięczny limit: 120 godzin rdzeniowych, czyli około 60 godzin pracy na domyślnej maszynie dwurdzeniowej (z GitHub Education 180).
- **Nie dodawaj karty ani PayPala do konta GitHub.** Bez metody płatności GitHub niczego nie nalicza: po wyczerpaniu limitu codespace po prostu przestaje się uruchamiać do początku następnego miesiąca.
- Nie uruchamiaj okresów próbnych (np. Copilot Pro). Wymagają karty i potem same przechodzą w płatne.
- Zużycie sprawdzisz na [github.com/settings/billing](https://github.com/settings/billing) → **Usage**.
- W OpenRouter korzystaj z darmowych modeli i nie kupuj kredytów. Zużycie klucza pokazuje komórka ZUŻYCIE w notatniku 02b.

## Notatniki

We wszystkich modułach analizuj ten sam film: synteza (moduł 4) łączy sieć z modułu 1 z dialogami i emocjami z modułów 2 i 3.

| Plik | Moduł | Co powstaje |
|---|---|---|
| `analiza_sieciowa_scenariusza.ipynb` | 1. Sieć współwystąpień postaci | `krawedzie.csv`, `graf_postaci.graphml` |
| `analiza_dialogow_01_glos_plec.ipynb` | 2. Głos i płeć | `dialogi.csv`, `postacie.csv` |
| `analiza_dialogow_02_emocje.ipynb` | 3. Emocje (OpenAI) | `emocje.csv`, `emocje_postaci.csv` |
| `analiza_dialogow_02a_emocje.ipynb` | 3. Emocje z rozkładem w czasie (OpenAI) | jak wyżej |
| `analiza_dialogow_02b_emocje.ipynb` | 3. Emocje z rozkładem w czasie (OpenRouter, darmowe modele) | jak wyżej |
| `analiza_dialogow_03_synteza.ipynb` | 4. Synteza i prezentacja | `bundle.json`, `graf_postaci_wzbogacony.graphml`, archiwum ZIP |
| `analiza_sieciowa_scenariusza_done.ipynb` | Rozwiązanie referencyjne modułu 1 | — |

Graf z modułu 1 możesz otworzyć w [Gephi Lite](https://lite.gephi.org), które działa w przeglądarce bez instalacji. Samouczek jest w pliku `presentations/tutorial.html`.

## Dla prowadzącego

Konfiguracja Codespaces jest w `.devcontainer/`. Korzysta z domyślnego obrazu Codespaces, więc nie zużywa darmowego limitu dysku studentów. Codespace utworzony z tego repozytorium rozlicza się z limitu osoby, która go uruchomiła, a nie właściciela repozytorium. Nie włączaj prebuildów Codespaces, bo ich koszt nalicza się właścicielowi repozytorium.
