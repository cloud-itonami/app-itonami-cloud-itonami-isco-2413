# cloud-itonami-isco-2413
Occupation reference: ISCO-08 (International Labour Organization, 2012), code 2413. This app is not produced, reviewed or endorsed by the ILO.
職業の参照: ISCO-08（国際労働機関 ILO、2012 年）のコード 2413。日本語の名称は当方の訳です。この app は ILO が作成・確認・推奨したものではありません。

Open Business Blueprint for **ISCO-08 2413**: Financial Analysts — an ISCO
**Wave 0 (cognitive substrate)** occupation per ADR-2607121000:
pure-cognitive work, the LLM-first wave, **no robotics gate** —
eligible for actor implementation now.

**Maturity: `:implemented`** — FinancialAnalystsAdvisor ⊣
FinancialAnalystsGovernor as a langgraph StateGraph
(`intake → advise → govern → decide → commit/hold`, human-approval
interrupt), modeled on cloud-itonami-isco-4311's bookkeeping actor.
13 tests / 27 assertions green.

The analyst HARD invariants — set validity and disclosure
completeness, not editorial judgement:

1. **Rating validity** — the proposed rating must be a member of the
   security's registered valid-ratings scale (no invented rating
   category).
2. **Conflict disclosure** — the proposed disclosed-conflicts set must
   be a superset of the security's registered known-conflicts set — an
   undisclosed conflict is detected by set difference.

Also HARD: unregistered/foreign security, unregistered organization,
non-`:propose` effect. Escalations (always human sign-off):
`:publish-rating` (external publication), low confidence (< 0.6).

Scope honesty: ANALYSIS only — regulated investment advice and any trade execution are out of scope for this blueprint (a different licensing regime and a different ISCO code).

AGPL-3.0-or-later, forkable by any qualified operator. Part of the
[cloud-itonami](https://itonami.cloud) open business fleet.
