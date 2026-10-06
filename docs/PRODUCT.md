# Product and vision

BlooM helps a restaurant turn what a guest shares about a meaningful meal into useful material for the chef and dining room. The guest's intention travels through the process: conversation, recap, culinary proposals, chef decisions, confirmed menu and operational briefs.

## The idea

A guest can describe a memory, an occasion, a taste, a texture or a way of sharing a meal. BlooM structures those details so the restaurant can interpret them through its own craft.

The ambition is to make more of the restaurant's expertise available through personalisation. AI helps connect the guest's context with professional possibilities; the chef and team determine the experience they can actually deliver. This is a product direction, not a measured claim of additional revenue, time savings or market creation.

## Who does what?

| Participant | Contribution |
|---|---|
| Guest | Shares wishes and constraints, corrects the recap, ranks culinary directions and confirms a menu proposal. |
| Benkei | Conducts the discovery conversation and extracts practical information and concrete story details. |
| Chef | Evaluates feasibility, adapts dishes, sets prices and composes proposals. |
| Dining room | Uses a separate draft pack to consider service, rhythm, sharing and interaction options. |
| BlooM operator | Manages invitations and requests, and reviews, edits, approves or retries professional packs through the dashboard. |

These are functional roles. The current authentication model does not yet provide a separate, fully isolated account for every restaurant role.

## Restaurant DNA

The kitchen profile describes style, signature ingredients, reference dishes, areas to avoid, creativity and notes for the AI. Signature ingredients are guidance rather than a closed catalogue of everything the chef may use.

The service profile distinguishes documented capabilities, explicitly allowed attentions, explicit prohibitions, equipment and additional notes. A missing permission remains unknown. A public menu reference is not proof of today's stock, equipment or permission to provide a special service.

Guest constraints and the confirmed menu take priority. Creative suggestions must identify a meaningful connection to the guest and a documented basis in the restaurant; anything additional remains subject to professional confirmation.

## From inspiration to execution

The software holds several distinct outputs:

- An editable guest recap and structured dossier.
- Five culinary directions per course, including titles, notes, explanations and key elements.
- Chef menu proposals with adaptations and prices.
- A final menu recorded after the guest's selection.
- Separate Chef and Service draft packs, with review status and editing tools.

The existing packs are text. A built-in PDF, DOCX or presentation export has not been established in the current snapshot.

## Principles expressed in the current prompts

- Keep facts, wishes, optional ideas and unknowns distinct.
- Follow the guest's conversational pace without manufacturing a personal story.
- Respect manual corrections and require explicit recap validation.
- Preserve the agreed menu and its adaptations when preparing briefs.
- Offer meaningful, conditional suggestions rather than guaranteed services.
- Give the dining room useful context without exposing intimate story details.
- Keep professional review essential, including ingredient and allergy checks.

These are design rules visible in the code. Their presence in a prompt does not prove that every generated response complies.

## Scope and evidence

These documents cover BlooM's restaurant application. They do not describe a deployed hotel product or a catering workflow.

No sales, customer-satisfaction or operational ROI figures are asserted here. Existing development journeys and historical AI outputs are described in [Examples](EXAMPLES.md); the current verification limits are listed in [Status](STATUS.md).

**Source basis:** current `client/src/lib/publicContent.ts`, `shared/schema.ts`, `server/services/benkei-prompt.ts`, `server/services/prompt-builder.ts` and `server/services/professional-pack-prompt.ts`; source commit `3cff2298063d73d4d23e918b4fba2f656ead43f4`.
