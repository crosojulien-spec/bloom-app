# Existing examples and recorded results

Start with the illustrated live-app demo below. The older development reports and scripted examples are retained separately so their dates and limits remain clear.

## 1. The Last Spoonful: a captured live-app journey

**[Read the illustrated walkthrough](demos/the-last-spoonful/README.md)** · **[Open the 11-slide PDF](demos/the-last-spoonful/BlooM%20-%20The%20Last%20Spoonful%20-%20Presentation.pdf)**

A fictional 40th birthday for a guest, his wife and two Czech friends brings together memories of China and Prague. The run was captured at [bloommm.fr](https://bloommm.fr) on **6 October 2026**.

The same dossier was followed through discovery, a corrected recap, generated dishes, simulated chef decisions, menu selection, final confirmation and both generated professional packs. Suggestions include a hong shao rou dish, a plum dessert to share, plating ideas and small service gestures.

The screenshots and generated outputs come from the application. The dinner, chef approval and prices are simulated. The restaurant has not approved or delivered the meal. The separate restaurant-DNA image is an English reading view prepared from the saved profile, not a native profile-editor screen.

[Evidence notes](demos/the-last-spoonful/evidence.md) record the manual recap corrections, draft profile, pack-review state and failed operator-email attempt. This run supplements the earlier evidence; it does not validate every prompt or demonstrate commercial results.

## 2. Earlier development journeys

The existing [preview-validation report dated **21 September 2026**](evidence/preview-validation-2026-09-21.md) describes complete development journeys using two restaurant profiles.

### Le Tôt ou Tard

- Benkei conversation, corrections to the date and tastes, and real generation of five dishes per course.
- A single generation network call despite a double click.
- One guest selection per course, a guest note, a chef adaptation and a final proposal.
- A discreet candle wish kept as **to confirm with the restaurant**, without a promise.
- Simulated confirmation, without a payment route.
- Chef and Service packs edited, reloaded and approved; the Service pack retained its confirmation condition.
- Both pack email statuses remained `NOT_SENT`.

These are the steps explicitly recorded in the report. It does not provide all the dish titles, prices or complete pack text for this journey.

### Lá Bù Lá

- A French Benkei conversation captured three guests, a time, medium spice tolerance, an explicitly stated absence of allergies or dietary restrictions, and a memory of shared broth.
- Corrections to the date and tastes survived a reload: `2026-10-19`, hot broth and aubergine.
- A handwritten-note wish remained **to confirm with the restaurant**, without a service guarantee.
- A real generation produced five starters, five mains and five desserts, according to the report.
- The guest selected one dish per course; an adaptation and chef proposal were exercised.
- Final confirmation was simulated, and the invitation reached its used state.
- Chef and Service packs were edited, reloaded and approved; email status remained `NOT_SENT`.

This is a report of a development test. It is not evidence of a paying customer meal, approval of a service by the actual restaurant or a production deployment of the current prompts.

The original report is retained in the source export at `quality/reports/validation-preview-2026-09-21.md` and copied into this repository's evidence appendix. It does not include the full fifteen-dish output or a complete saved chef response.

## 3. Recorded AI output on an existing synthetic menu

A separate recorded test, **`packs-labula`**, has actual saved AI responses for Chef and Service packs. It used a synthetic menu and context already defined in `quality/evaluate-ai.ts`.

| Evidence field | Recorded value |
|---|---|
| Trace date | 21 September 2026, 12:40:10.939 UTC, from the filename |
| Trace | `quality/results/packs-labula-2026-09-21T12-40-10-939Z.json` |
| Pack prompt version | `2026-09-21-quality-1` |
| Recorded model | `gpt-4.1` |
| Review state | `REQUIRES_HUMAN_REVIEW` |
| Origin | A scripted test on synthetic inputs; not a customer dossier |

The fixture's story says that a family cake had a golden top and a tender centre, and that the two diners liked serving each other. It also records fennel as a dislike and a handwritten-note wish that is not authorised in the profile and needs confirmation.

The menu supplied to the generator was:

| Course | Existing test input |
|---|---|
| Starter | Aubergine croustillante; mild sauce, chilli separately, according to the fictional chef agreement in the fixture. |
| Main | Chao shou de porc en bouillon doux. |
| Dessert | Cheesecake basque au thé oolong. |

This menu was a test input. It was not produced by a saved chef interaction, and the fixture's confirmation timestamp was set artificially.

### Recorded Chef excerpt

Original French output, reproduced without rewriting:

> Texture à double contraste : accentuer le dessus doré et la tendreté intérieure (matérialise le souvenir du gâteau familial, cf. récit). Appui : « dessus doré cœur tendre ».

Another recorded suggestion was:

> Dressage à partager : présenter l’aubergine en morceaux à picorer ou à servir à l’autre, avec sauce en coupelle centrale (matérialise « se servir mutuellement » ; compatible avec la maison).

These excerpts show the intended connection between a concrete memory and a culinary or sharing option. They are historical AI suggestions requiring review, not proof that the restaurant accepted the proposed equipment or serving method.

### Recorded Service excerpt

Original French output:

> Attentions : Aucune attention spécifique autorisée ; la demande de petit mot reste à confirmer avant toute initiative.

> Points à confirmer : Autorisation d’un petit mot en salle.

This historical response also contained a `PACK CHEF` section inside the Service output. That is a recorded defect, not an example of the desired current format. The current prompt explicitly requires the two pack types to remain separate and distinguishes unknown permissions from explicit refusals; these historical outputs do not validate the revised prompt.

## 4. How these examples fit together

The Last Spoonful now provides a captured software journey through final confirmation and both generated packs. Its chef decisions remain simulated: an independently participating restaurant, a real meal and customer feedback are still missing from this evidence set.

The September preview journeys, the synthetic pack fixture and the October demo are **different cases**. They have not been combined into one customer story. The new demo uses its own recorded outputs.

**Provenance:** the exported test script and preview report, plus a read-only inspection of existing Replit test traces on 6 October 2026. The original trace directory was excluded from the uploaded source ZIP; the inspection transcript is preserved with the private preparation files.
