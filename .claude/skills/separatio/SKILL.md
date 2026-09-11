---
name: separatio
description: Analityczna destylacja Opus Alchymicum — oddziela esencję zagadnienia od przypadłości. Wywołaj jako /separatio <zagadnienie>; ognie: ONT,EPI,AKS,PRG; faza: Nigredo|Albedo|Citrinitas|Rubedo; głębia: n/10[; sefiroty: ...]
argument-hint: <zagadnienie>; ognie: ONT,EPI,AKS,PRG; faza: Nigredo|Albedo|Citrinitas|Rubedo; głębia: n/10[; sefiroty: ...]
disable-model-invocation: true
---

Uruchom moduł SEPARATIO systemu Opus Alchymicum.

Argumenty podane przez użytkownika: $ARGUMENTS

Zanim odpowiesz:
1. Wczytaj `modules/separatio.md` i `modulators/phases_matrix.md` (ścieżki względem katalogu `Opus/`), zgodnie z regułą progresywnego ładowania z `CLAUDE.md`.
2. Jeśli w argumentach jawnie wskazano ścieżkę sefirotyczną lub pojedynczą sefirę (segment `sefiroty: ...`), wczytaj też `modulators/sefirot.md`. W przeciwnym razie pomiń ten wymiar całkowicie — nie ładuj go domyślnie.
3. Z argumentów wyodrębnij: Zagadnienie, wybrane Ognie Analityczne (1-4 z ONT/EPI/AKS/PRG), Fazę (Nigredo/Albedo/Citrinitas/Rubedo) i Głębię analizy (1-10, domyślnie 6 jeśli nie podano). Jeśli brakuje Zagadnienia, Fazy lub choć jednego Ognia, dopytaj o brakujące wartości w jednej turze — zgodnie z regułą „Brak parametrów” z `CLAUDE.md` — zamiast zgadywać.
4. Zastosuj tożsamość i zasady jakości z `CLAUDE.md` (Opus Alchymicum), styl poznawczy wskazanej Fazy z `modulators/phases_matrix.md`, oraz pełną sekwencję operacyjną (5 kroków, DoD) z `modules/separatio.md`.
