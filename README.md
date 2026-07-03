# standard_repo_template

Standardowy szablon repozytorium (**repository template**) organizacji **IPI — Independent
Protocol Infrastructure**. Służy jako baza (starter) narzucana na wszystkie własne repozytoria
organizacji, aby każdy nowy projekt startował z tym samym kompletem procedur, plików bazowych
i konwencji — zamiast powstawać ad-hoc i rozjeżdżać się ze standardami org.

Ekosystem IPI opiera się o **Cosmos SDK / CosmWasm**, dlatego domyślne konwencje, `.gitignore`
i procedury CI są dobrane pod stack Go / Rust (CosmWasm) / Node / Python.

> Status: **draft do review**. Definicje B.O.S. i GRIH poniżej są propozycją standardu org
> zgłoszoną w ramach [Fala 0] i podlegają akceptacji utrzymujących.

## Jak użyć jako startera

1. Na GitHubie kliknij **Use this template → Create a new repository** (albo wykonaj fork).
2. Uzupełnij `README.md` opisem konkretnego projektu (zostawiając sekcje B.O.S. / GRIH lub
   linkując do nich).
3. Zaktualizuj pole `Copyright` w `LICENSE` jeśli projekt ma innego właściciela praw niż IPI.
4. Skonfiguruj pipeline CI (patrz B.O.S. — wymóg przechodzenia CI przed merge).
5. Zacznij pracę zgodnie z procedurą B.O.S. (fork → branch → PR → CI → review → merge).

## Struktura katalogów

```
.
├── .github/
│   ├── AGENTS.md               # wskazówki dla agentów/automatyzacji operujących na repo
│   ├── ISSUE_TEMPLATE/         # szablony zgłoszeń (bug / feature)
│   └── pull_request_template.md
├── .vscode/                    # współdzielone ustawienia edytora
├── docs/
│   └── index.md                # punkt wejścia do dokumentacji wzorca
├── examples/                   # przykłady użycia
├── resources/
│   └── .omnis.toml             # konfiguracja zasobów org
├── src/                        # kod źródłowy projektu
├── tests/
│   └── Taskfile.yml            # zadania testowe (go-task)
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE                     # Apache-2.0
└── README.md
```

## B.O.S. — Basic Operating Standard

**B.O.S.** to obowiązkowy, minimalny standard pracy w repozytoriach IPI. Każda zmiana trafia do
gałęzi `main` wyłącznie tą drogą:

1. **Fork / branch** — pracę prowadzimy na gałęzi tematycznej, nigdy bezpośrednio na `main`.
   Nazwy gałęzi: `feat/…`, `fix/…`, `docs/…`, `chore/…`, `refactor/…`.
2. **Conventional Commits** — każdy commit zgodny z konwencją (`type(scope): opis`), patrz
   [CONTRIBUTING.md](CONTRIBUTING.md).
3. **Pull Request** — zmiana wchodzi wyłącznie przez PR z wypełnionym
   [szablonem PR](.github/pull_request_template.md).
4. **CI musi przejść** — PR nie może zostać scalony, dopóki pipeline CI nie jest zielony.
5. **Review** — wymagana co najmniej jedna akceptacja utrzymującego.
6. **Merge** — po spełnieniu powyższych zmiana jest scalana do gałęzi docelowej zgodnej z GRIH.

Model gałęzi org: `main` (stabilna) · `developement` · `testing` · `revision` · `releasing`.

## GRIH — system wersjonowania

**GRIH** to cykl życia wydania stosowany w org, spięty z modelem gałęzi. Cztery fazy:

| Faza | Znaczenie   | Gałąź robocza  | Co się dzieje                                    |
|------|-------------|----------------|--------------------------------------------------|
| **G** | Growth      | `developement` | Rozwój funkcji, nowe zmiany                       |
| **R** | Revision    | `revision`     | Przegląd, refaktor, stabilizacja API             |
| **I** | Integration | `testing`      | Integracja, pełne testy, CI end-to-end           |
| **H** | Hardening   | `releasing`    | Utwardzanie, wydanie kandydata, promocja do `main` |

Etykieta wersji jest kompatybilna z SemVer z sufiksem fazy GRIH:

```
MAJOR.MINOR.PATCH-<faza>[.n]
np.  1.4.0-g.2   (druga iteracja Growth wydania 1.4.0)
     1.4.0-h     (Hardening — kandydat do wydania)
     1.4.0       (wydanie stabilne na main)
```

Zasada promocji: `G → R → I → H → release`. Zmiana nie przeskakuje faz; regres (cofnięcie do
wcześniejszej fazy) jest dozwolony przy wykryciu wady.

## Licencja

[Apache License 2.0](LICENSE) — Copyright 2026 IPI — Independent Protocol Infrastructure.

## Kontrybucja

Zobacz [CONTRIBUTING.md](CONTRIBUTING.md). Część roadmapy:
[ipicoin/universal-independency-declaration#1](https://github.com/ipicoin/universal-independency-declaration/issues/1).
