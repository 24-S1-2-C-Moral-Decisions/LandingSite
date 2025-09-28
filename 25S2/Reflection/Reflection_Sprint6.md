# Sprint 6 — Reflection & Improvement Report (Concise)

**Timeframe:** Week 7–8 (2025-09-15 to 2025-09-28)
 **Team:** Moral Decisions
 **Sprint Goal (based on what we actually delivered):**

1. **Compile and write technical documentation** (architecture, tech stack, start/deploy steps);
2. **Confirm the storage location and access method for the Survey database** (as a prerequisite for later integration);
3. **Record a display video** showing how to run the project locally and access the pages. (Aligned with the two client meetings’ asks: documentation + demo video, and clarity on DB location.)

------

## 1) Feedback Sources (Feedback Collected)

- **Client Meeting — 2025-09-15:** Complete docs for two sites, confirm Survey DB location, and record a “how to run the site” demo video.
- **Client Meeting — 2025-09-22:** Re-emphasised the display video and logic/architecture explanation; first “make the Survey↔DB relationship clear.” For this sprint we **focused on the three minimal deliverables: DB location clarity + run demo + docs**.
- **Carry-over from Sprint 5 (format reference):** Continue the “demo-path-first, unified docs and start-up” approach; reuse the same reflection structure.

------

## 2) What We Actually Completed This Sprint

1. **Technical Documentation Consolidation**
   - Documented **frontend/backend architecture**, **tech stack**, **environment variables**, and **start/stop steps**; produced an executable “Quick Start” in README/Wiki. (Matches 9/15 requests.)
2. **Survey Database Location Confirmation**
   - Audited current environments and confirmed the Survey DB **hosting location and access path** (including connection method and responsible owner), laying the groundwork for later read/write integration. (Matches 9/22’s “first figure out where it is.”)
3. **Display Video Recording**
   - Recorded a short **“how to run locally and access the site”** video, covering dependency installation, start commands, URLs, and basic health checks (as requested in both meetings).

------

## 3) Issues & Root Causes

- **Scattered information:** Historical DBs and unclear ownership led to inconsistent team understanding of “where the DB actually lives.” We solved the transparency problem first by documenting the **DB location**.
- **Inconsistent startup paths:** Local environments differed across members and we **lacked a copyable start script/guide**. We therefore prioritised the **run demo video + Quick Start** to lower the entry barrier.

------

## 4) Outcomes & Evidence

- **Documentation:** Integrated architecture/tech stack, run instructions, env variables, and FAQs into a single README that supports handover.
- **DB Location Report:** Clear notes on the Survey DB’s **hosting, connection, and responsible owner**, enabling subsequent read/write verification and integration.
- **Demo Video:** A “**how to run the website**” video covering install, start, and verification steps—meeting the client’s immediate need to see it running.

------

## 5) What Worked / What Didn’t

**Worked**

- Aligning on the **critical blocking info (DB location)** first reduced downstream communication costs.
- **Short video + one-page Quick Start** significantly improved “runnability” for new members and stakeholders.

**Didn’t**

- This sprint only delivered **location clarity + run demo + docs**; we **did not** complete functional verification of “Survey → DB write/read” (scheduled for next sprint).

------

## 6) Commitments for the rest of time

> Keep “docs-as-code” and extend **Minimum Runnable** to **Minimum Verifiable (submit → persist → query)**.

1. **Close the minimal data loop:** Implement Survey submit → API → DB write with a simple query verification; document scripts/API samples.
2. **Add contract checks:** Based on the field definitions in README, add a **FE/BE field consistency checklist** (or a minimal CI contract test) to prevent “unclear fields” issues.
3. **Enhance videos:** In addition to the “run demo,” add a **submit → persist → query** video as direct evidence for the client.

------

## 7) Risks & Mitigations

- **Environment differences hinder reproducibility** → Keep `.env.example` and “Quick Start” up-to-date; add a “Common Errors & Fixes” section.
- **DB permission/availability uncertainty** → Keep Nectar as a fallback for hosting/connection; document owners and request procedures.