# Konsola Transmutacji — panel do strojenia Opus Alchymicum

`panel.html` to samodzielny, wizualny panel (Claude Artifact) do ustawiania
parametrów modułów `/separatio`, `/coagulatio`, `/coniunctio` przed
rozpoczęciem rozmowy w Claude Code.

## Co robi

Wybierasz moduł, fazę alchemiczną, parametry specyficzne dla modułu i
opcjonalnie ścieżkę sefirotyczną — panel na bieżąco składa gotowy tekst
komendy (np. `/separatio Pieniądz; ognie: ONT, PRG; faza: Nigredo; głębia:
8/10`). Przycisk „Kopiuj” kopiuje ten tekst do schowka. Wklejasz go jako
pierwszą wiadomość w Claude Code.

## Czego NIE robi

- Nie zapisuje żadnej konfiguracji ani presetów.
- Nie łączy się z Claude Code ani z żadnym innym systemem — to czysto
  statyczna strona HTML/CSS/JS, cała logika działa lokalnie w przeglądarce.
- Nie jest ładowany przez `Opus/CLAUDE.md` — reguła progresywnego ładowania
  kernela nic o nim nie wie i nie musi wiedzieć. To osobne narzędzie
  pomocnicze, poza systemem promptów.

## Zakres

Obejmuje tylko trzy aktywne moduły z `../CLAUDE.md` (separatio, coagulatio,
coniunctio) wraz z modulatorami faz (`../modulators/phases_matrix.md`) i
sefirot (`../modulators/sefirot.md`). Rodzina modułów `Consilium` (poza
`Opus/`) jest poza zakresem tego panelu.

## Jak opublikować / uruchomić

- **Jako Claude Artifact:** poproś Claude Code o opublikowanie
  `interface/panel.html` narzędziem Artifact — dostaniesz link działający w
  przeglądarce, bez instalacji.
- **Lokalnie:** otwórz `panel.html` bezpośrednio w przeglądarce (podwójne
  kliknięcie) — działa identycznie, offline, poza czcionkami z Google Fonts.

## Architektura (pod przyszły pulpit fizyczny)

Logika w `panel.html` jest rozdzielona na:
- `state` — jeden obiekt reprezentujący wszystkie ustawienia,
- `renderCommand(state)` — czystą funkcję budującą tekst komendy,
- warstwę zdarzeń DOM, która tylko aktualizuje `state` i woła `update()`.

Docelowy fizyczny pulpit (pokrętła/przełączniki, np. Arduino/ESP32 +
WebSerial) mógłby zasilać ten sam `state` z innego źródła, bez zmiany
logiki generowania komend.
