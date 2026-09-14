# How to style the bibliography

The rules below explain how to properly format your bibliography in a bachelor thesis. Use a standard BibTeX style, preferably a variant that prints DOIs as links.
The examples below show the resulting output.

## 1. Authors

- Full first names, all authors, never "et al." inside the entry:
  `author = {Lommen, Nils and Meyer, {\'E}l{\'e}anore and Giesl, J{\"u}rgen}`
- Accents in LaTeX form: `Giesl, J{\"u}rgen`, `Meyer, {\'E}l{\'e}anore`, `Thiemann, Ren{\'e}`.
- Name particles lowercase and braced, so they stay with the surname: `{von Essen}, Christian`.
- Hyphenated surnames braced: `{Schneider-Kamp}, Peter`.

## 2. Titles

- Title Case for every main word, protected with braces:
  `{{Proving}} {{Almost-Sure}} {{Innermost}} {{Termination}} of {{Probabilistic}} {{Term}} {{Rewriting}} {{Using}} {{Dependency}} {{Pairs}}`
- Tool names in sans-serif via a macro `\newcommand{\tool}[1]{$\mathsf{#1}$}` defined in the preamble, so that every tool name looks the same in the text and in the bibliography: `{{\tool{KoAT}}}: {{Automatic Complexity}} and {{Termination Analysis}} of {{Integer Programs}}`, `{{\tool{AProVE}}}`. The double braces protect the macro from BibTeX's case changes.
- Mathematical symbols in titles as math: `Non-$E$-Overlapping`.

## 3. Venues

**Conferences.** One fixed pattern, always the same for the same series: `Proc.\ ACRONYM~'YY`, then series with volume, pages, year. 
No "Proceedings of the 30th International Conference on ...", no ordinal, no city, no publisher.

```
@inproceedings{kassinggiesl2023iast,
  author    = {Kassing, Jan-Christoph and Giesl, J{\"u}rgen},
  title     = {{{Proving}} {{Almost-Sure}} {{Innermost}} {{Termination}} of {{Probabilistic}} {{Term}} {{Rewriting}} {{Using}} {{Dependency}} {{Pairs}}},
  booktitle = {Proc.\ CADE~'23},
  series    = {LNCS 14132},
  pages     = {344--364},
  year      = 2023,
  doi       = {10.1007/978-3-031-38499-8_20}
}

@inproceedings{ahrens2025WeightedRewritingSemiring,
  author    = {Ahrens, Emma and Kassing, Jan-Christoph and Giesl, J{\"u}rgen and Katoen, Joost-Pieter},
  title     = {{{Weighted}} {{Rewriting}}: {{Semiring}} {{Semantics}} for {{Abstract}} {{Reduction}} {{Systems}}},
  booktitle = {Proc.\ FSCD~'25},
  series    = {LIPIcs 337},
  pages     = {6:1--6:21},
  year      = 2025,
  doi       = {10.4230/LIPIcs.FSCD.2025.6}
}
```

Further venue examples: `Proc.\ IJCAR~'24` (LNCS 14739), `Proc.\ TACAS~'26` (LNCS 16506), `Proc.\ CAV~'26` (LNCS 16684), `Proc.\ FroCoS~'05` (LNCS 3717), `Proc.\ RTA~'10` (LIPIcs 6). 
LNAI volumes are written as LNCS. Joint events keep the joint acronym (`Proc.\ RTA-TLCA~'14`). 
Workshops without a series get only pages and year (`Proc.\ WST~'23`, `Proc.\ IWC~'12`).

**Journals.** ISO abbreviation, volume, pages, year. 
Issue number only when the pages do not identify the paper (LMCS, article-numbered journals).

```
@article{fuhs2011provingterminationdependency,
  author  = {Fuhs, Carsten and Giesl, J{\"u}rgen and Parting, Michael and {Schneider-Kamp}, Peter and Swiderski, Stephan},
  title   = {{{Proving}} {{Termination}} by {{Dependency}} {{Pairs}} and {{Inductive}} {{Theorem}} {{Proving}}},
  journal = {J.\ Autom.\ Reason.},
  volume  = 47,
  pages   = {133--160},
  year    = 2011,
  doi     = {10.1007/s10817-010-9215-9}
}

@article{arts2000termination,
  author  = {Arts, Thomas and Giesl, J{\"u}rgen},
  title   = {{{Termination}} of {{Term}} {{Rewriting}} {{Using}} {{Dependency}} {{Pairs}}},
  journal = {Theor.\ Comput.\ Sci.},
  volume  = 236,
  pages   = {133--178},
  year    = 2000,
  doi     = {10.1016/S0304-3975(99)00207-8}
}

@article{kassing2025LMCS,
  author  = {Kassing, Jan-Christoph and Giesl, J{\"u}rgen},
  title   = {{{From}} {{Innermost}} to {{Full}} {{Probabilistic}} {{Term}} {{Rewriting}}: {{Almost-Sure}} {{Termination}}, {{Complexity}}, and {{Modularity}}},
  journal = {Log.\ Methods Comput.\ Sci.},
  volume  = 21,
  number  = 4,
  year    = 2025,
  doi     = {10.46298/lmcs-21(4:28)2025}
}
```

Other journal abbreviations: `J.\ ACM`, `Inf.\ Comput.`, `J.\ Symb.\ Comput.`, `Inf.\ Process.\ Lett.`, `ACM Trans.\ Comput.\ Log.`, `J.\ Log.\ Algebr.\ Methods Program.`

**Book chapters.** `@incollection` with `booktitle`, `editor`, `publisher`, series, pages:

```
@incollection{brockschmidt2010TerminationGraphsJava,
  author    = {Brockschmidt, Marc and Otto, Carsten and {von Essen}, Christian and Giesl, J{\"u}rgen},
  title     = {{{Termination}} {{Graphs}} for {{\tool{Java}}} {{Bytecode}}},
  booktitle = {Verification, {{Induction}}, {{Termination Analysis}}},
  editor    = {Siegler, Simon and Wasser, Nathan},
  publisher = {Springer},
  series    = {LNCS 6463},
  pages     = {17--37},
  year      = 2010,
  doi       = {10.1007/978-3-642-17172-7_2}
}
```

**Theses.** `@phdthesis` / `@mastersthesis` with the university in `school`:

```
@phdthesis{thiemann_diss:2007,
  author = {Thiemann, Ren{\'e}},
  title  = {{{The}} {{DP}} {{Framework}} for {{Proving}} {{Termination}} of {{Term}} {{Rewriting}}},
  school = {RWTH Aachen University},
  year   = 2007
}

@mastersthesis{kassing:thesis:2022,
  author = {Kassing, Jan-Christoph},
  title  = {{{Using}} {{Dependency}} {{Pairs}} for {{Proving}} {{Almost-Sure}} {{Termination}} of {{Probabilistic}} {{Term}} {{Rewriting}}},
  school = {RWTH Aachen University},
  year   = 2022
}
```

A bachelor's thesis is entered as `@mastersthesis` with `type = {Bachelor's thesis}`.

**Technical reports.** `@techreport` with `number = {Technical Report …}` and `institution = {…}`.

**Online material.** `@misc` with the URL and access date in `note`:

```
@misc{aprove-website,
  key  = {{\relax APrW}},
  note = {Website of \tool{AProVE}: \url{https://aprove.informatik.rwth-aachen.de/}. Accessed: 2026-07-19}
}
```

## 4. DOI

Every entry that has a DOI gets `doi = {10.…}`. 
The style renders it as a link. 
Workshop papers without a DOI get the proceedings URL in `note`. 
Never put a URL into the `doi` field.

## 5. Non-English sources

Add `note = {In Japanese}` (or the respective language) for papers in non-English journals.

## 6. Results

With these fields the style produces, uniformly:

> Jan-Christoph Kassing and Jürgen Giesl. Proving Almost-Sure Innermost Termination of Probabilistic Term Rewriting Using Dependency Pairs. In *Proc. CADE '23*, LNCS 14132, pages 344–364, 2023. doi:10.1007/978-3-031-38499-8_20.

> Carsten Fuhs, Jürgen Giesl, Michael Parting, Peter Schneider-Kamp, and Stephan Swiderski. Proving Termination by Dependency Pairs and Inductive Theorem Proving. *J. Autom. Reason.*, 47:133–160, 2011. doi:10.1007/s10817-010-9215-9.

> Nils Lommen, Éléanore Meyer, and Jürgen Giesl. Control-Flow Refinement for Complexity Analysis of Probabilistic Programs in KoAT (Short Paper). In *Proc. IJCAR '24*, LNCS 14739, pages 233–243, 2024. doi:10.1007/978-3-031-63498-7_14.

## 7. Ordering

The bibliography is sorted alphabetically by author, not by order of citation: first by the surname of the first author, then by the following authors, then by year, then by title. 
Entries without authors (websites, tools) sort under their `key` field, which also determines their label (see the `@misc` example above).
Particles are ignored for sorting, so `{von Essen}, Christian` is filed under E. For the examples above this gives the order

> Arts, Giesl (2000) — Brockschmidt, Otto, von Essen, Giesl (2010) — Fuhs, Giesl, Parting, Schneider-Kamp, Swiderski (2011) — Kassing, Giesl (2023) — Kassing, Giesl (2025) — Lommen, Meyer, Giesl (2024) — Thiemann (2007).

Keep the `.bib` file itself in the same order (e.g. with `bibtool -s`, sort key first author and year), so that inconsistencies between entries of the same author are easy to spot.