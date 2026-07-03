# Współpraca (Contributing)

Dziękujemy za wkład w projekt **IPI — Independent Protocol Infrastructure**. Ten dokument opisuje
obowiązujący proces pracy. Jest on częścią standardu **B.O.S. (Basic Operating Standard)** i
obowiązuje we wszystkich repozytoriach powstałych na bazie tego szablonu.

## Zanim zaczniesz

- Przeczytaj [README.md](README.md) (sekcje **B.O.S.** i **GRIH**).
- Sprawdź otwarte issues — być może zadanie jest już zgłoszone lub w toku.
- Do większych zmian najpierw załóż/wybierz issue i opisz zamiar, żeby uzgodnić kierunek.

## Procedura B.O.S. — fork → branch → PR

1. **Fork** repozytorium (lub, jeśli masz uprawnienia, pracuj na gałęzi tematycznej).
2. Utwórz **gałąź** od aktualnej gałęzi docelowej:
   ```bash
   git checkout -b feat/krotki-opis
   ```
   Nie commituj bezpośrednio na `main`.
3. Wprowadź zmiany, dbając o zielone testy lokalnie (`task test` — patrz `tests/Taskfile.yml`).
4. **Commituj** zgodnie z Conventional Commits (niżej).
5. Wypchnij gałąź i otwórz **Pull Request** z wypełnionym
   [szablonem PR](.github/pull_request_template.md).
6. Poczekaj na **zielone CI** i **review** — dopiero wtedy PR może zostać scalony.

## Konwencja commitów — Conventional Commits

Format:

```
type(scope): krótki opis w trybie rozkazującym

[opcjonalne ciało]

[opcjonalna stopka, np. Closes #123]
```

Dozwolone `type`:

| type       | zastosowanie                                            |
|------------|---------------------------------------------------------|
| `feat`     | nowa funkcjonalność                                     |
| `fix`      | poprawka błędu                                          |
| `docs`     | dokumentacja                                            |
| `style`    | formatowanie, bez zmiany logiki                         |
| `refactor` | refaktoryzacja bez zmiany zachowania                    |
| `perf`     | poprawa wydajności                                      |
| `test`     | testy                                                   |
| `build`    | system budowania, zależności                            |
| `ci`       | konfiguracja CI                                         |
| `chore`    | prace porządkowe                                        |

Zmiany łamiące kompatybilność: dopisek `!` po scope (`feat(api)!: …`) lub stopka
`BREAKING CHANGE:`.

Przykłady:

```
feat(wallet): dodaj obsługę podpisów offline
fix(rpc): popraw timeout przy zapytaniu do gateway
docs(readme): uzupełnij sekcję GRIH
```

## Wersjonowanie — GRIH

Wydania podlegają cyklowi **GRIH** (Growth → Revision → Integration → Hardening), spiętemu z
gałęziami `developement` / `revision` / `testing` / `releasing`. Format etykiety:
`MAJOR.MINOR.PATCH-<faza>` (np. `1.4.0-i`). Szczegóły w [README.md](README.md#grih--system-wersjonowania).
Nie przeskakuj faz; promocja odbywa się kolejno, regres jest dozwolony przy wykryciu wady.

## Wymóg CI

Każdy PR **musi** przechodzić pipeline CI. PR z czerwonym CI nie jest scalany. Jeśli CI wykryje
problem, popraw go w tej samej gałęzi (kolejne commity dołączą się do PR automatycznie).

## Review

- Wymagana co najmniej jedna akceptacja utrzymującego.
- Adresuj komentarze w formie kolejnych commitów lub dyskusji — nie rób force-push kasującego
  historię review, chyba że uzgodniono inaczej.

## Licencja wkładu

Wysyłając PR zgadzasz się na udostępnienie swojego wkładu na warunkach
[Apache License 2.0](LICENSE), spójnie z licencją repozytorium.
