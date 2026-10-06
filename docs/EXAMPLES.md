# Existing examples and recorded results

This document shows what is available in the existing evidence. It does not invent dishes, conversations or customer outcomes to complete the product story.

## 1. A documented development journey

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

## 2. Recorded AI output on an existing synthetic menu

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

## 3. What is still missing from the evidence set

The inspected records do not provide one continuous saved case linking all of these: Benkei conversation, the complete fifteen proposals, a real chef adaptation, final guest confirmation and both resulting packs.

The preview journey and the pack fixture above are **different cases**. They have not been joined to suggest a complete end-to-end capture. No replacement conversation, menu, adaptation or brief has been generated for this documentation.

**Provenance:** the exported test script and preview report, plus a read-only inspection of existing Replit test traces on 6 October 2026. The original trace directory was excluded from the uploaded source ZIP; the inspection transcript is preserved with the private preparation files.
