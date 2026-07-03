# Dokumentacja — standard_repo_template

Punkt wejścia do dokumentacji wzorca repozytorium organizacji **IPI — Independent Protocol
Infrastructure**. Ten szablon jest bazą (starter) dla wszystkich własnych repo org.

## Spis treści

- [README](../README.md) — przegląd, jak użyć jako startera, struktura katalogów.
- [CONTRIBUTING](../CONTRIBUTING.md) — proces pracy, Conventional Commits, review, CI.
- [LICENSE](../LICENSE) — Apache License 2.0.
- [Szablony zgłoszeń](../.github/ISSUE_TEMPLATE/) — bug report, feature request.
- [Szablon PR](../.github/pull_request_template.md).
- [AGENTS.md](../.github/AGENTS.md) — wskazówki dla agentów/automatyzacji.

## Standardy org

### B.O.S. — Basic Operating Standard

Obowiązkowy minimalny standard pracy: **fork → branch → PR → CI → review → merge**. Żadna zmiana
nie trafia do `main` inną drogą. Szczegóły: [README → B.O.S.](../README.md#bos--basic-operating-standard).

### GRIH — system wersjonowania

Cykl życia wydania **G**rowth → **R**evision → **I**ntegration → **H**ardening, spięty z modelem
gałęzi org (`developement` / `revision` / `testing` / `releasing`). Etykieta wersji:
`MAJOR.MINOR.PATCH-<faza>`. Szczegóły: [README → GRIH](../README.md#grih--system-wersjonowania).

## Kontekst / roadmapa

Ten wzorzec realizuje **[Fala 0]** roadmapy IPI — fundament odblokowujący kolejne fale.
Część: [ipicoin/universal-independency-declaration#1](https://github.com/ipicoin/universal-independency-declaration/issues/1).
