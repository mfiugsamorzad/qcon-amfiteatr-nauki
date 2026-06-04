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
