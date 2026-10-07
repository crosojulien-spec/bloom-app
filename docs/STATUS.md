# Current status and verification

**Documentation date:** 7 October 2026.

**Exported source:** `main`, commit `3cff2298063d73d4d23e918b4fba2f656ead43f4`, dated 25 September 2026.  
**Current prompt markers in that source:** Benkei `2026-09-25-quality-1`; professional packs `2026-09-25-quality-3`.

## What has been checked for this documentation

- The public homepage at [bloommm.fr](https://bloommm.fr) returned HTTP 200 on 7 October 2026. This availability check did not rerun the application journey.
- [The Last Spoonful](demos/the-last-spoonful/README.md) records a live-app journey captured on 6 October 2026, from discovery through simulated confirmation and generated Chef and Service packs. Its [evidence notes](demos/the-last-spoonful/evidence.md) distinguish application outputs from the fictional dinner and simulated decisions.

- The uploaded ZIP opens correctly and contains 173 files.
- All 169 source-file hashes listed in its export manifest match the exported files. This verifies internal export integrity, not independent equality with the live deployment.
- The frontend, backend, shared schema, prompts, tests and historical documents have been inspected for documentation.
- No real `.env` file is included. A first secret-pattern scan did not identify a provider key; this is not an exhaustive guarantee about source history, which is not included.
- Replit reports a successfully published deployment at [bloommm.fr](https://bloommm.fr). The identity of its deployed build with the exported commit has not been independently established.

During repository recovery on 6 October 2026, the private source passed a fresh dependency installation, application and quality TypeScript checks, all 43 isolated quality tests, and the client/server build on Windows with Node.js 24.18.0. The 169 exported source hashes still match the original manifest. Those source checks did not include a live journey, external email delivery, database migration or real AI evaluation. The separately captured live demo above adds evidence of one application journey; it does not establish equality between the live build and the source export.

## Built in the source

| Area | Evidence and qualification |
|---|---|
| Invitations | Restaurant-linked invitation creation and access. Real email depends on configured delivery services. |
| Benkei | Streaming discovery with structured extraction, restaurant context and guest corrections. |
| Recap | Editable fields, manual-override priority, explicit approval and unknown constraint states. |
| Menu generation | Five proposals per course, structured output and restriction filtering/top-up. |
| Guest preferences | Selection and ranking persisted through the workflow. |
| Chef workspace | Feasibility, adaptation, pricing and menu proposals. |
| Final choice | Guest confirmation and stored final-menu data with duplicate handling. |
| Professional packs | Separate Chef and Service text, editing, approval and retry controls. |
| Administration | Invitation, request and internal pack views. |
| Payment | Simulation only. |

## Historical development evidence

The preview report dated **21 September 2026** records two development journeys using the Le Tôt ou Tard and Lá Bù Lá profiles. It reports **29/29 quality tests**, application and quality TypeScript checks, a build and browser journeys, including real AI generation in development. QA email delivery and payment were not executed.

Those results predate the prompt versions in the current export. They must not be presented as a new pass of the current build, a production certification or evidence of meals served by partner restaurants.

Saved AI traces dated 21 September include actual responses on scripted, synthetic inputs. They are marked for human review. The retained examples and their limits are described in [Examples](EXAMPLES.md).

## Gaps visible in the current implementation

- **Portable setup:** external service configuration, database preparation and environment loading still require work.
- **Access control:** a separate restaurant-scoped chef identity is not established; protection is uneven across older routes.
- **Chef adaptations:** final-menu construction takes the original proposal title; an adapted display title can be lost. Adaptation notes are still carried forward.
- **Pack review and delivery:** approval tools exist, but automatic operator email is not conditioned on approval.
- **Background reliability:** generation runs asynchronously in the web process rather than a durable job queue.
- **Older code paths:** legacy service-brief and menu structures coexist with the current packs and need clear separation.
- **Profiles:** public references and draft profiles do not establish current stock, equipment or service permissions.
- **Demo follow-up:** the captured recap needed manual corrections, the generated packs were not marked approved, and the operator email failed because no operator address was configured. No operator email was sent.
- **Evidence:** a captured software journey is now available, but restaurant execution, customer outcomes and a fresh evaluation of all current prompts remain unverified.

## Next work to decide

For collaboration, the immediate priorities are a reproducible setup, clear source-access arrangements and a documented environment for testing. For an operational rollout, priorities include restaurant-specific access control, complete profile validation, reliable background processing and new evaluations of current prompts and professional handoffs.

These are proposed priorities derived from the source and reports. They are not a release schedule or a claim that the fixes have been implemented.

## Reading the evidence honestly

Code presence shows that a mechanism is implemented. A saved output shows what one run produced. A dated report describes the checks performed at that time. Publication status shows that a deployment exists. None of those alone demonstrates restaurant execution, guest satisfaction, time saved or a commercial result.

**Sources:** `EXPORT_MANIFEST.json`, `EXPORT_REDACTIONS.json`, `EXPORT_README.md`, current source modules, `quality/reports/validation-preview-2026-09-21.md`, the 6 October read-only inspection of existing AI traces, and [the live-demo evidence notes](demos/the-last-spoonful/evidence.md).

