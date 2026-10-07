# Technical overview

BlooM is a TypeScript web application with a React frontend and an Express backend. The current source remains an export of the existing Replit application; this documentation does not claim that it has already been made portable or redeployed.

The published application is at [bloommm.fr](https://bloommm.fr). This repository contains its public introduction and [captured demo](demos/the-last-spoonful/README.md); it has no runnable application code. Developers with access can use the [private source and setup guide](https://github.com/crosojulien-spec/bloom-app-source/blob/main/docs/DEVELOPER_GUIDE.md).

## Components

| Component | Current implementation | Responsibility |
|---|---|---|
| Frontend | React 18, Vite, Tailwind, shadcn/Radix components | Public pages, guest flow, chef workspace and admin dashboard. |
| Client state | Zustand and browser storage | Discovery dossier, intermediate choices and journey restoration. |
| Backend | Node.js, Express, TypeScript | Invitation checks, discovery streaming, menu workflow, administration and pack generation. |
| Validation | Zod and shared TypeScript schemas | Input validation, output structures and shared data contracts. |
| Database | PostgreSQL through Drizzle and the Neon serverless driver | Restaurant profiles, requests, proposals, selections, menus and packs. |
| AI | OpenAI SDK with configurable gateway and role-specific models | Discovery, analysis, culinary generation and professional packs. |
| Invitations | Airtable | Standard invitation storage and status. |
| Email | Resend when configured | Invitation delivery and operator pack messages. |
| Contact integration | Optional Make webhook plus database storage | Website contact submissions. |

These are dependencies identified in the source. Their credentials and real runtime configuration are not included in the public repository.

## Organisation of the private source

| Location | What a developer will find |
|---|---|
| `client/src/components` | Guest discovery, selections, chef proposals and final-validation components. |
| `client/src/pages` | Public, invitation and admin pages. |
| `client/src/store` | Journey state and persistence. |
| `shared/schema.ts` | Database schema, restaurant profiles and application data types. |
| `shared/benkei-dossier.ts` | Structured discovery facts, extraction and correction handling. |
| `server/routes.ts` | API workflow and administration routes. |
| `server/storage.ts` | Database operations, final-confirmation handling and pack leases. |
| `server/ai.ts` | AI calls, model-role configuration, structured generation and pack modes. |
| `server/services` | Prompts, restaurant constraints, profiles and email handling. |
| `quality` | Tests, scripted AI scenarios, profile drafts and historical reports. |

## AI flow

Benkei streams a conversational response and structured markers. The frontend extracts those markers into an editable dossier. Manual corrections and explicit recap validation are then carried into the menu request.

Culinary generation assembles the guest constraints, corrected context and restaurant kitchen profile. The output schema expects five starters, five mains and five desserts. Additional filtering and top-up logic are present; these checks do not replace professional ingredient review.

After final guest confirmation, Chef and Service pack generation receives the final menu, corrected dossier and both restaurant profiles. The current prompt priorities preserve constraints and adaptations, distinguish permissions from unknowns, and keep suggestions optional.

The model names in the code are configurable defaults. They do not establish which model is used by the live deployment or what a new provider account can access.

## Main stored entities

Restaurant profiles; guest requests and dossier context; dish proposals; guest ranked selections; chef feasibility decisions; menu proposals and their dishes; final menus; professional packs with source snapshots, edits, approvals, generation status and email status.

The schema also retains older menu and service-brief structures. Their presence is not proof that they drive the current professional-pack workflow.

## Running the source

The source includes an installation note, dependency lockfile and `.env.example`. A developer needs to install dependencies, provide a compatible database and configure AI and invitation services. The app does not automatically load a local `.env` file. The exported Airtable base identifier is deliberately a placeholder.

Available commands include development startup, TypeScript checks, quality tests and a production build. Database schema push and profile import can write to a target database and require a deliberately chosen environment.

There are no versioned migrations, general seed or CI configuration in the export. Pack simulation does not simulate the entire app or remove all external dependencies. The complete setup notes and source are kept in the private preparation.

## Contribution areas

The current implementation identifies useful work around portable configuration, access control, reliable background jobs, preservation of chef adaptations, profile completeness and evaluation of the latest prompts. These are contribution areas derived from existing gaps, not announced commitments to ship new features.

**Source basis:** `package.json`, `vite.config.ts`, `shared/schema.ts`, `server/db.ts`, `server/ai.ts`, `server/routes.ts`, `server/storage.ts`, service modules and `EXPORT_README.md`.
