# About this demo

[Back to the walkthrough](README.md) · [Project status](../../STATUS.md)

## What was captured

The Last Spoonful was recorded in Microsoft Edge at [bloommm.fr](https://bloommm.fr) on **6 October 2026**. One fictional guest dossier was followed from discovery through a corrected recap, dish generation, chef-role decisions, menu selection, simulated confirmation and generated Chef and Service packs.

The English presentation was shortened to 11 slides on **7 October 2026**. Its explanatory copy was edited for readability. The selected screenshots are unchanged; the PDF trims their side margins for layout. Remaining French labels belong to the captured interface. This PDF was prepared separately and is not an in-app export.

The [screenshot manifest](screenshots/provenance.json) records the source and SHA-256 hash of each of the nine included images. Eight are live product captures. The ninth is the restaurant-DNA reading view described below.

## What was simulated

The scenario is a 40th birthday for four adults on 17 October: the host, his wife and two Czech friends. Their story and meal are fictional. The chef role was exercised as part of the demo, without participation or approval from the actual restaurant.

Availability, preparation choices and prices were entered as test assumptions. The €35 shown is a demo price, not a restaurant quote or a verified conversion of the guest's 900 CZK budget. Final confirmation used the app's simulation control. No real payment, booking or meal is established by this run.

## Restaurant DNA

The Lá Bù Lá profile was retrieved from the live application after the run, on the same day. Its kitchen references include pork, Chinese home cooking and oolong Basque cheesecake. The service profile is labelled `2026-09-21-public-draft`; its capability, attention and equipment lists contain no entries.

The DNA image is an **English reading view prepared for this demo**, not a production profile-editor screen or an immutable snapshot from the exact moment of generation. The original profile uses public references, including the restaurant's [website](https://www.labula.cz/) and [menu](https://www.labula.cz/menu). It is not a restaurant-approved inventory.

Pork belly, plums, braising time, serving vessels and special gestures still need checking. Empty service fields mean undocumented. They establish neither permission nor refusal. The profile instructs the AI not to suggest special attentions without permission; the packs nevertheless contain conditional service ideas. This is a reason for human review, not proof of perfect adherence to the profile.

## Observed limits

The recap needed manual corrections. Both professional packs were generated and inspected, but were not marked approved by BlooM. The operator-email attempt failed because `BLOOM_OPERATOR_EMAIL` was not configured; no operator email was sent.

The live build has not been independently matched to the exported source commit. This is evidence of one software journey. It does not establish restaurant feasibility, reliable behaviour across every scenario, guest satisfaction or commercial results.

## Supporting records

The full transcripts, dish outputs, chef decisions, selected menu, generated pack text and profile exports are retained in the private [source demo archive](https://github.com/crosojulien-spec/bloom-app-source/tree/main/docs/demos/the-last-spoonful) for authorised reviewers. That archive includes the earlier, longer walkthrough. This public folder contains the revised presentation and its selected captures.
