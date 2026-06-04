# aMFIteatr Nauki | Side Event Q-Con

Oficjalne repozytorium strony internetowej wydarzenia **aMFIteatr Nauki**. Wydarzenie zaplanowane jest na 10 września 2026 r. na Wydziale MFI UG. Strona jest statycznym landing page'em wykorzystującym HTML i CSS, z animacjami AOS oraz interaktywną agendą w postaci siatki (CSS Grid).

---

## 📅 Instrukcja dodawania wydarzeń do agendy (Kalendarz CSS)

1. Znajdź sekcję `<div class="calendar-grid">` w `index.html`[cite: 1].
2. Użyj poniższego szablonu:

    ```html
    <div class="cal-event [KLASA-KOLORU]" style="grid-column: [NR-STREFY]; grid-row: [START] / [KONIEC];">
        <h4>Nazwa Wydarzenia</h4>
        <p>Prelegent/Info</p>
    </div>
    ```

3. **KLASY KOLORÓW**:
   * `event-blue` (Niebieski - secondary)
   * `event-lime` (Limonkowy - primary)
   * `event-dark` (Ciemny - bg-darker)
   * `event-common` (Szary - dla przerw)
   * `event-outline` (Ramka - strefy otwarte)

4. **NUMERY KOLUMN (STREFY)**:
   * 2 = STEM Arena
   * 3 = Cyber Space
   * 4 = Future Leaders
   * 5 = Global Stage
   * 6 = Tech Poligon
   * 7 = Sprintathon
   * 8 = Science Fair

5. **OBLICZANIE RZĘDÓW (Każde 15 minut = 1 rząd)**:
   * 09:00 = 1
   * 09:30 = 3
   * 10:00 = 5
   * 10:30 = 7
   * 11:00 = 9
   * 11:30 = 11
   * 12:00 = 13
   * 12:30 = 15
   * 13:00 = 17
   * 13:30 = 19
   * 14:00 = 21
   * 14:30 = 23
   * 15:00 = 25

**PRZYKŁAD:**
Wydarzenie w Cyber Space (kolumna 3) od 11:00 do 12:00:
Start 11:00 (rząd 9), Koniec 12:00 (rząd 13).
Styl: `style="grid-column: 3; grid-row: 9 / 13;"` 

---

## 📄 Instrukcja tworzenia podstron wydarzeń

### Krok 1: Stwórz nowy plik
Skopiuj gotowy plik `example.html` i zmień jego nazwę na taką, która opisuje prelekcję (np. `wyklad-dragan.html`, `warsztaty-python.html`).
> **WAŻNE:** Używaj małych liter, unikaj polskich znaków i stosuj myślniki zamiast spacji.

### Krok 2: Podepnij plik w agendzie (w pliku `index.html`)
Otwórz `index.html`, znajdź odpowiedni kafelek w harmonogramie i zamień znacznik `<div>` na link `<a>`, podając nazwę nowo utworzonego pliku.

**Zamiast**:
```html
<div class="cal-event event-blue" style="...">
    ...
</div>
```

**ZRÓB**:
```html
<a href="wyklad-dragan.html" class="cal-event event-blue" style="...">
    ...
</a>
```

### Krok 3: Edytuj treść (w nowym pliku, np. `wyklad-dragan.html`)
Otwórz nowo sklonowany plik HTML i podmień informacje w odpowiednich sekcjach:

#### A. Tagi (Sekcja: `<div class="event-tags">`)
* `<span class="tag tag-zone">Nazwa Strefy</span>`
* `<span class="tag tag-level">Poziom: np. Początkujący</span>`

#### B. Tytuł i zajawka (Sekcja: `<div class="details-header">`)
* `<h1 class="details-title">Główny Tytuł Wykładu</h1>`
* `<p class="details-subtitle">Krótkie streszczenie (1-2 zdania).</p>`

#### C. Czas, miejsce i prelegent (Sekcja: `<div class="event-meta-grid">`)
Podmień teksty znajdujące się wewnątrz tagów `<p>...</p>`:
* ⏰ **Godzina**: np. `<p>11:45 - 13:15</p>`
* 📍 **Lokalizacja**: np. `<p>Sala 101</p>`
* 🎤 **Prelegent**: np. `<p>Imię i Nazwisko</p>`

#### D. Główny opis (Sekcja: `<div class="details-content">`)
Tutaj wklejasz pełen tekst od prelegenta. Przydatne formatowanie:
* `<h3>Tytuł akapitu</h3>` (nagłówek)
* `<p>Zwykły tekst</p>` (akapity)
* `<ul class="details-list">` (rozpoczęcie listy punktowanej)
* `<li>Twój punkt</li>` (pojedynczy element listy)
* `</ul>` (zakończenie listy)

---

## 🚀 Szybki proces

1. Kopiujesz `example.html` -> nazywasz plik `startup.html`.
2. W `index.html` podmieniasz `<div>` na: `<a href="startup.html" class="cal-event...">`.
3. Otwierasz `startup.html`, wpisujesz dane prelekcji, zapisujesz i gotowe!
