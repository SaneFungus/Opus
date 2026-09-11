# Rejestracja komend Opus Alchymicum jako skilli Claude Code

`CLAUDE.md` opisuje `/separatio`, `/coagulatio`, `/coniunctio`, `/mapa`,
`/status`, `/reset` jako reguły tekstowe — ale Claude Code samo w sobie ich
nie rozpoznaje. Wiadomość zaczynająca się od `/` jest przechwytywana przez
Claude Code i dopasowywana do zarejestrowanej komendy/skilla, zanim
cokolwiek trafi do modelu. Bez rejestracji w tym katalogu wpisanie
`/separatio ...` kończy się błędem `Unknown command: /separatio`, a model
nigdy nie widzi treści `CLAUDE.md` w kontekście tej wiadomości.

Każdy plik `SKILL.md` w tym katalogu to cienki wyzwalacz: przekazuje surowy
tekst argumentów (`$ARGUMENTS`) i każe modelowi wczytać właściwy plik z
`../../modules/` i `../../modulators/` zgodnie z regułą progresywnego
ładowania z `../../CLAUDE.md`. Logika modułów zostaje wyłącznie w
`modules/` i `modulators/` — nie jest tu duplikowana.

**Uwaga:** nowe skille są wykrywane przy starcie sesji Claude Code. Po
dodaniu lub zmianie plików w tym katalogu trzeba zacząć nową sesję w
`Opus/`, żeby zaczęły działać w bieżącej rozmowie.
