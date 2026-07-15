# IPI Repository Template

A minimal starting point for new repositories in the IPI organization.

Organization-wide contributing, conduct, security, support, governance, and
issue-template files are inherited from
[`ipicoin/.github`](https://github.com/ipicoin/.github). A repository should
override them only when its scope genuinely requires different instructions.

## Before making a repository public

- Replace this README with a plain-language purpose, maturity status, scope,
  non-goals, architecture, setup, test, security, and release description.
- Select an appropriate license and preserve every upstream notice. The
  organization default for new original software is Apache-2.0; copied or
  derived work must retain compatible upstream terms.
- Identify the default branch and responsible maintainers.
- Add reproducible tests and required pull-request checks before claiming a
  stable release.
- Enable private vulnerability reporting, secret scanning, push protection,
  dependency alerts, and automated dependency updates where supported.
- Protect the default branch: require pull requests, prevent force pushes and
  deletion, apply the rule to administrators, and require independent approval
  when the maintainer pool makes that feasible.
- Document third-party provenance, generated files, release signing, and any
  externally operated service or endpoint.
- Add useful labels and at least one bounded issue that an outside contributor
  can complete from public information.

## Honest maturity labels

Use conservative labels such as **concept**, **pre-alpha**, **experimental**,
**incubating**, **beta**, or **stable**. A public repository is not necessarily
open source, an experiment is not a release, a fast endpoint is not evidence of
independence, and an upstream fork is not original IPI code.

The organization [roadmap](https://github.com/ipicoin/.github/blob/main/ROADMAP.md)
defines evidence expected before stronger project-wide maturity claims.

## License

The template itself is licensed under [Apache License 2.0](LICENSE). Projects
created from it must review and record their own licensing decision.
