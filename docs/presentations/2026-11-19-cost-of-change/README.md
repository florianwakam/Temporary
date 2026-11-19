# Presentation: the cost of change

Date: 2026-11-19 · Length: 20 minutes · Audience: tech teams · Language: French.

What it costs to change software we already built, why that cost grows, how to measure it, and why AI accelerates a system with a low cost of change and amplifies the debt of the others. Hook: GTA VI, released today, 13 years after GTA V. Live deck (private until shared): <https://claude.ai/artifact/UsZaeXpTAJL1FcCby3NYU6>.

Every figure carries its source on the slide; slides 21 and 22 list the references. Below, each slide comes with its message in text, for readers who do not see the image.

## Accessibility

- Text contrast is at least 4.5:1, or 3:1 for large text; colours are told apart by lightness, and every coloured mark has a word next to it.
- No text is smaller than 24 px on a 1920 × 1080 slide.
- Each chart is an `<svg>` with an `aria-label` describing it in French; labels are real text over the drawing.

## Slides

| #   | Slide                                   | Minutes |
| --- | --------------------------------------- | ------- |
| 1   | Cover: a dictionary definition          | 0.75    |
| 2   | GTA VI, 2013–2026 timeline              | 1       |
| 3   | Three lessons from GTA VI               | 1       |
| 4   | The tip of the iceberg                  | 1       |
| 5   | Boehm vs Beck: two cost curves          | 1.25    |
| 6   | Fowler: internal quality pays back      | 1       |
| 7   | 42 % of the week on maintenance         | 0.75    |
| 8   | Debt is concentrated                    | 0.75    |
| 9   | Three forces: coupling, Conway, Lehman  | 1       |
| 10  | DORA: speed and stability go together   | 1       |
| 11  | Five signs the cost is soaring          | 1       |
| 12  | And AI?                                 | 0.5     |
| 13  | The promise, then the measures          | 1       |
| 14  | METR: felt −20 %, measured +19 %        | 1       |
| 15  | AI amplifies the system it finds        | 1       |
| 16  | For an agent, change costs tokens       | 1       |
| 17  | What helps a human helps an agent       | 1       |
| 18  | Switching cost, AI edition              | 1       |
| 19  | What we can do on Monday                | 1       |
| 20  | Closing                                 | 0.75    |
| 21  | References: scientific studies          | —       |
| 22  | References: books, articles and reports | —       |

1. Cover

   ![Dark cover, glowing amber title "coût du changement", dictionary style: "loc. nom. m. · de l'anglais switching cost", then three numbered definitions.](01-cover.png)

   1. Ce qu'on perd en quittant ce qu'on a construit. 2. Ce qu'on paie pour modifier ce qu'on a construit. 3. Ce qui décide si l'IA vous accélère… ou vous enlise.

2. GTA VI, 2013–2026 timeline

   ![Five-step timeline: 2013 GTA V, September 2022 leak, December 2023 trailer, May 2025 and November 2025 delays.](02-gta.png)

   GTA V sort en 2013 ; le leak de 2022 est moqué ; le trailer bat le record de vues en 24 h ; deux reports amènent la sortie au 19 novembre 2026. Même avec des moyens hors normes, on n'échappe pas au coût du changement.

3. Three lessons from GTA VI

   ![Three cards: the mocked leak, what we lose when we leave, changing at scale.](03-gta-lecons.png)

   De l'extérieur on ne voit que l'écran ; plus un existant rapporte, plus le quitter coûte cher ; plus un système est grand, plus un changement tardif coûte cher.

4. The tip of the iceberg

   ![An amber "Écrire le code" pill above a dashed waterline, eight hidden activities below it: understand, analyse impact, coordinate, test, review, deploy, fix regressions, wait.](04-iceberg.png)

   Écrire le code n'est que la partie visible : l'essentiel du coût est sous l'eau.

5. Boehm vs Beck: two cost curves

   ![Schematic chart by phase: Boehm's curve stays low then climbs to ×100 in production; Beck's curve stays almost flat.](05-courbes.png)

   Corriger après livraison coûte souvent 100× plus cher qu'en phase d'exigences (≈ 5× sur les petits systèmes) ; tests, refactoring et petites itérations aplatissent la courbe.

6. Fowler: internal quality pays back

   ![Cumulative features over time: "no design" starts faster then flattens, "good design" overtakes it at a dashed threshold; +124 % and 15× on the right.](06-fowler.png)

   Selon l'hypothèse de Fowler, le croisement arrive en semaines ; Tornhill et Borg mesurent +124 % de temps et 15× plus de défauts dans le code de faible qualité.

7. 42 % of the week on maintenance

   ![Light slide, a huge "42 %" with three facts: 17.3 h of 41.1 h, about 85 billion dollars a year for bad code, 23 % lost to technical debt.](07-stripe.png)

   Stripe : 17,3 h sur 41,1 h en maintenance (42 %, calcul) ; Besker et al. mesurent 23 % du temps perdu à cause de la dette technique.

8. Debt is concentrated

   ![Two bars: 20–30 % of the code, 70–80 % of the slowdown.](08-pareto.png)

   Observation de terrain QMates, pas une étude : on peut cibler au lieu de tout réécrire.

9. Three forces: coupling, Conway, Lehman

   ![Three cards with icons: coupling, dependencies between teams, accumulated complexity.](09-causes.png)

   Le couplage propage chaque changement, le système copie l'organisation, la complexité monte sans effort actif.

10. DORA: speed and stability go together

    ![Four cards: 182× more deployments, 127× shorter lead time, 2,293× faster recovery, 8× fewer failed changes.](10-dora.png)

    Les équipes élite ont la vitesse et la stabilité ; le lead time, c'est le coût du changement mesuré en jours.

11. Five signs the cost is soaring

    ![Light slide, five numbered signs separated by thin rules.](11-signaux.png)

    Trois sur cinq ? Le coût du changement pilote déjà votre roadmap.

12. And AI?

    ![Amber statement slide: "Et l'IA dans tout ça ?"](12-ia.png)

    L'IA écrit du code de plus en plus vite ; or écrire, c'était la pointe de l'iceberg.

13. The promise, then the measures

    ![Three cards: 55.8 % faster with Copilot, −7.2 % delivery stability, ×2 code churn.](13-mesures.png)

    Sur du code neuf l'IA brille ; sur un système existant, elle hérite de son coût du changement.

14. METR: felt −20 %, measured +19 %

    ![Two huge figures side by side: blue "−20 %" felt, amber glowing "+19 %" measured, revealed on click.](14-metr.png)

    Des développeurs expérimentés se croyaient 20 % plus rapides avec l'IA ; ils étaient 19 % plus lents : près de 40 points d'écart.

15. AI amplifies the system it finds

    ![Two cards: modular and tested system, AI speeds delivery; coupled and untested system, AI speeds debt.](15-amplificateur.png)

    Chaque ligne générée est une ligne à maintenir.

16. For an agent, change costs tokens

    ![A huge "−83 %" with before/after rows: tokens read 159,564 to 27,360, largest file 17,155 to 3,695 lines, tokens written unchanged.](16-tokens.png)

    L'agent n'écrit pas moins, il lit moins : une seule expérience, à confirmer.

17. What helps a human helps an agent

    ![Light slide, a two-column table: for a human, for an AI agent.](17-parallele.png)

    Réduire le coût du changement, c'est préparer le terrain pour l'IA.

18. Switching cost, AI edition

    ![A glowing quote "Ce qu'on perd en quittant ce qu'on a construit" and three steps: open formats, agnostic harness, interchangeable models.](18-lockin.png)

    Ne recréez pas la dette chez votre fournisseur d'IA.

19. What we can do on Monday

    ![Five numbered actions and a dashed box with the DORA 2024 elite benchmark.](19-lundi.png)

    Mesurer, cartographier, cibler, découpler, rendre le système lisible pour l'IA ; repère élite : lead time < 1 jour, ≈ 5 % d'échecs, restauration < 1 h.

20. Closing

    ![A QMates quote and a glowing amber punchline.](20-fin.png)

    GTA VI arrive 13 ans après GTA V. L'IA va vite. Votre système doit pouvoir suivre.

21. References: scientific studies

    ![Two columns of references.](21-references.png)

22. References: books, articles and reports

    ![Two columns of references grouped by type.](22-references-2.png)

## Sources

| Claim                                                                   | Source                                                                                                                                                      |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition and 20–30 % / 70–80 % field observation                      | [QMates, « Coût du changement en développement logiciel »](https://qmates.tech/fr/savoir/cout-du-changement-logiciel), 2026-03-18                           |
| GTA VI delays to 2026-05-26 then 2026-11-19; Take-Two −8 % at the close | Rockstar Games and Take-Two announcements (May and Nov. 2025); Reuters, 2025-11-07                                                                          |
| First trailer: 90.4 M views in 24 h                                     | [Guinness World Records](https://www.guinnessworldrecords.com/world-records/758375-most-viewed-youtube-video-in-24-hours-non-music)                         |
| ~90 leaked videos, Sept. 2022                                           | Press coverage (Game World Observer); Rockstar confirmed the intrusion, not the number                                                                      |
| Defect fixed after delivery ≈ 100× (≈ 5× on small systems)              | Boehm, B. W. (1981). _Software Engineering Economics_; Boehm, B. & Basili, V. (2001). Software Defect Reduction Top 10 List. _IEEE Computer_, 34(1)         |
| Flattening the curve                                                    | Beck, K. (1999). _Extreme Programming Explained_                                                                                                            |
| Design stamina, "weeks not months"; internal quality cost is negative   | [Fowler (2007)](https://martinfowler.com/bliki/DesignStaminaHypothesis.html); [Fowler (2019)](https://martinfowler.com/articles/is-quality-worth-cost.html) |
| +124 % time to resolve issues, 15× defects, 39 codebases                | Tornhill, A. & Borg, M. (2022). Code Red: The Business Impact of Code Quality. [arXiv:2203.04374](https://arxiv.org/abs/2203.04374)                         |
| 17.3 h of 41.1 h on maintenance; ≈ 85 Md$ a year for bad code           | [Stripe (2018), _The Developer Coefficient_](https://stripe.com/files/reports/the-developer-coefficient.pdf)                                                |
| 23 % of developer time lost to technical debt                           | Besker, T., Martini, A. & Bosch, J. (2019). _Journal of Systems and Software_, 156, 41–61                                                                   |
| Coupling, Conway, Lehman                                                | Parnas (1972), _CACM_ 15(12); Conway (1968), _Datamation_ 14(4); Lehman (1980), _Proc. IEEE_ 68(9)                                                          |
| 182× / 127× / 2,293× / 8×; elite benchmark; AI adoption −1.5 % / −7.2 % | [DORA / Google Cloud (2024), _Accelerate State of DevOps Report_](https://dora.dev/research/2024/dora-report/)                                              |
| Copilot 55.8 % faster                                                   | Peng, S. et al. (2023). [arXiv:2302.06590](https://arxiv.org/abs/2302.06590)                                                                                |
| METR: +19 % measured, −20 % felt, 16 developers, 246 tasks              | Becker, J., Rush, N., Barnes, E. & Rein, D. (2025). [arXiv:2507.09089](https://arxiv.org/abs/2507.09089)                                                    |
| Code churn projected to double vs 2021                                  | [GitClear (2024), _Coding on Copilot_](https://www.gitclear.com/coding_on_copilot_data_shows_ais_downward_pressure_on_code_quality)                         |
| Agents tend to introduce technical debt                                 | [Doernenburg (2026)](https://martinfowler.com/articles/exploring-gen-ai/ccmenu-quality.html)                                                                |
| −83 % tokens read per change after refactoring                          | [Edwards-Alexander (2026)](https://martinfowler.com/articles/exploring-gen-ai/refactoring-economic-benefit.html)                                            |

arXiv papers are preprints, not peer-reviewed. Every figure was re-checked against its primary source on 2026-11-19.

## Timing

The speaker notes add up to about 19 minutes for 20 content slides, which leaves about a minute for questions in a 20-minute slot. For a 15-minute slot, skip slides 8, 11 and 18.

## Questions to expect

| Question                                | Answer                                                                                                   |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Isn't Boehm's 100× contested?           | Yes: Boehm and Basili (2001) give about 5× on small, non-critical systems; the order of magnitude stays. |
| Does METR prove AI slows everyone down? | No: 16 experienced developers on their own mature repositories, early-2025 tools; it shows the felt gap. |
| Is the −83 % tokens result solid?       | One experiment by one author on one codebase; the mechanism (less code to read) is the point.            |
| Did GTA VI take 13 years to develop?    | No: 13 years separate GTA V and GTA VI; the development time was never published.                        |

## Rendering

`slides.html` holds every slide (fonts from Google Fonts); each slide renders to a PNG with headless Chrome, one slide per HTML file:

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --hide-scrollbars --window-size=1920,1080 --virtual-time-budget=6000 --screenshot=01-cover.png file://$PWD/01-cover.html
```
