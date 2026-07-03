# GrantForge

A full-lifecycle grant writing engine for any organization: nonprofits,
schools, universities, local governments, and companies pursuing
educational, government, private, and corporate funding.

GrantForge produces research-driven, submission-ready applications that
read like a seasoned grant writer wrote them. Every draft passes through a
built-in house style that removes AI writing patterns, and every
application is scored by a mock reviewer before it goes out.

## First run

Connect a folder where GrantForge should live (your grants folder), then
say **"set up GrantForge"**. A guided interview captures your organization's
dossier: identity and registrations (EIN, UEI, SAM), mission and programs,
capacity and leadership, financials, past awards, and impact metrics. Upload
past applications and reports to speed this up — GrantForge extracts answers
and builds a reusable answer library from them. It also learns your writing
voice from samples you provide.

Everything is stored in a `.grantforge/` folder that persists across
sessions and improves with every application you complete.

## The workflow

Run the whole lifecycle with `/grantforge`, or invoke stages directly:

| Stage | Say | What happens |
|-------|-----|--------------|
| Discover | "find grants for us" | Searches Grants.gov, state portals, foundations, and corporate givers; returns a ranked, verified shortlist |
| Intake | "respond to this RFP" | Parses the announcement into a requirements matrix; eligibility check; go/no-go recommendation |
| Research | "research this grant" | Builds a cited evidence base (need data, intervention evidence) and funder intelligence (990s, giving history, priorities) |
| Draft | "draft the application" | Writes each section against the funder's verbatim prompts, within limits, in your voice |
| Budget | "build the budget" | Excel budget workbook plus a matching budget narrative, with verification math |
| Review | "are we ready to submit?" | Compliance audit, mock-scorer grading against the rubric, and a requirements-to-response compliance matrix |
| Track | "what's in our pipeline?" | Deadlines, statuses, win rate; harvests winning language back into your answer library |

## Outputs

Word documents formatted to the funder's rules, portal-ready plain-text
sections with character counts, Excel budget workbooks, and a compliance
matrix proving every requirement was addressed.

## Components

- 9 skills: grant-setup, grant-discover, grant-intake, grant-research,
  grant-draft, grant-budget, grant-review, grant-tracker, house-style
- 1 command: `/grantforge` (lifecycle orchestrator)

No external accounts or API keys required; research uses web search.
