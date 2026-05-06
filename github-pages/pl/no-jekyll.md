## Bez Jekyll

[en](../no-jekyll.md)

Wyłączenie Jekylla w GitHub Pages oznacza, że **GitHub Pages przestaje automatycznie konwertować Markdown do HTML**.

### Co się dzieje po wyłączeniu Jekylla?

Jeśli dodasz plik `.nojekyll` do repo:

* GitHub Pages **nie uruchamia Jekylla**
* **Markdown (`.md`) nie jest już automatycznie renderowany do HTML**
* pliki są serwowane „tak jak leżą” w repo

Czyli:

* `index.html` → działa normalnie
* `notes.md` → będzie pobierany jako plik tekstowy albo wyświetlany surowo (zależnie od przeglądarki), ale **nie jako strona**

---

## Czy musisz wtedy pisać w HTML?

**Nie musisz, ale masz 3 opcje:**

### 1. ✔️ Markdown + własny build (najczęstsze rozwiązanie)

Piszesz nadal w `.md`, ale:

* używasz **GitHub Actions**
* np. generatora:

  * Hugo
  * MkDocs
  * Astro
  * Eleventy
  * Docusaurus

One:

* zamieniają Markdown → HTML
* wrzucają gotową stronę do `gh-pages` lub `/docs`

👉 To daje pełną kontrolę i brak Jekylla.

---

### 2. ✔️ Markdown + Jekyll (domyślne GitHub Pages)

Jeśli NIE dodasz `.nojekyll`, GitHub:

* sam renderuje Markdown → HTML
* używa Jekylla

To najprostsze, ale mniej elastyczne.

---

### 3. ✔️ Statyczny HTML (bez żadnej konwersji)

Możesz:

* pisać ręcznie HTML
* albo generować go lokalnie

Plus:

* pełna kontrola

Minus:

* mniej wygodne niż Markdown

---

## Najważniejsze podsumowanie

| Opcja                               | Markdown działa | Konwersja automatyczna | Wygoda        |
| ----------------------------------- | --------------- | ---------------------- | ------------- |
| Jekyll (default)                    | ✔️              | ✔️                     | wysoka        |
| `.nojekyll` + brak builda           | ❌               | ❌                      | niska         |
| `.nojekyll` + CI (Hugo/MkDocs itd.) | ✔️              | ✔️ (w CI)              | bardzo wysoka |
| czysty HTML                         | ❌               | ❌                      | średnia       |

---

## Wniosek

Jeśli chcesz:

> „pełną kontrolę nad notatkami”

to najlepszy setup to:
👉 **Markdown + GitHub Actions + generator (np. MkDocs albo Hugo)**
a nie ręczne HTML.

---

Jeśli chcesz, mogę zaproponować Ci konkretną konfigurację (np. „minimalny setup do notatek jak Obsidian + GitHub Pages”).
