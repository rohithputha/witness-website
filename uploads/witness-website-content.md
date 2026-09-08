# Witness — Website Content

---

## Nav

- Witness (logo / wordmark)
- Memo
- Security
- Privacy
- Install on GitHub →

---

## Hero

**Headline:**
The diff shows what. Witness shows why.

**Subheadline:**
When AI writes your code, the session is where the decisions live. Witness reads it and posts the reasoning as inline PR comments before you merge.

**CTA:**
Install on GitHub →

---

## The Problem (below the fold)

**Label:** The gap

A teammate couldn't explain a function Claude had written two days earlier.

"I think it's caching something," he said.

The code worked. The diff was clean. But the reasoning was gone — the trade-offs considered, the alternatives rejected, the constraint that shaped the whole approach. It closed with the session.

That gap is what we built Witness for.

---

## Comparison / What You Get

| | Diff | Witness |
|---|---|---|
| What changed | Yes | Yes |
| Why this approach | No | Yes |
| What was rejected | No | Yes |
| Constraints respected | No | Yes |
| Context for the next change | No | Yes |

---

## How It Works

**Section label:** Three steps

**1. Install the GitHub App**
Connect Witness to your repo. No config required.

**2. Run Claude Code with the Skill**
Drop the Skill file into your project. Witness reads the session as it runs.

**3. Review the intent on your PR**
Structured decision summaries appear as inline comments before merge. Approve or flag each one.

---

## What Witness Posts

**Section label:** The comment

A Witness comment on your PR looks like this:

---

**Decision: Used Redis over in-memory store**

Agent considered in-memory caching but rejected it — session data needs to survive pod restarts. Redis adds a dependency but the team already runs it for the job queue.

Alternatives rejected: in-memory LRU, external session store (too slow at p99)

Constraint respected: no new infrastructure

👍 Approve · 🚩 Flag

---

## Architecture / Security

**Section label:** How it works under the hood

Witness processes session turns in memory and discards them. We store structured decision records only — never raw transcripts, never your source code.

Zero raw data retention by design.

[Read the security policy →](/security)

---

## CTA Section

**Headline:**
Start reviewing intent.

**Subheadline:**
Install takes 60 seconds. Works with any repo where you run Claude Code.

**CTA:**
Install on GitHub →

Questions: ro@membranelabs.org

---

## Footer

- Witness by Membrane Labs
- [Memo](/memo)
- [Security](/security)
- [Privacy](/privacy)
- ro@membranelabs.org

---
---

## Memo Page

*(Single-column, light mode, long-form essay. Reference register: mosaic.inc/blog/memo. No competitor mentions. No fundraising signals. Treat as a piece of writing.)*

**Title:** Code is the assembly

**Full text:**

We are shipping more code than ever and understanding less of it.

Not because the code is bad. The code works. Diffs are clean, tests pass, PRs merge. But ask someone to explain a function an AI agent wrote three days ago and you get something like: "I think it's caching something."

The diff shows what changed. It does not show why. The reasoning lived in the session — the trade-offs considered, the alternatives the agent explicitly rejected, the constraint that shaped the whole approach. When the session closed, that reasoning disappeared.

Addy Osmani has a name for what accumulates when this happens at scale: comprehension debt. The codebase grows. Ownership of individual decisions becomes diffuse. The next engineer to touch the code has no context for what it was trying to do, only what it does.

We built Witness because we think this is the central problem of AI-written code, and it is solvable.

The session is where the decisions live. Witness reads it. Before merge, it posts structured decision summaries as inline PR comments: what approach was chosen, what was rejected, what constraint was respected. A reviewer reads the intent, not just the output. They approve it or flag it. That judgment becomes part of the record.

Code is the assembly. The session is the source. We have been reviewing the wrong artifact.

The diff will tell you what changed. It will not tell you whether the agent understood the problem, considered the right alternatives, or made a call you would have made. By the time you find out it did not, the session is gone and the context is gone with it.

Witness keeps the record.

There is a version of AI-assisted development where teams ship faster and understand what they ship. Where a new engineer joining a project can read the decision history, not just the code. Where comprehension debt does not compound silently underneath velocity metrics.

That is what we are building toward.

Rohith
Membrane Labs

---
---

## Security Page

**Title:** Security

**Last updated:** September 2026

---

### Zero raw data retention

Witness processes session turns in memory. We do not store raw transcripts, session logs, or source code at any point. When a session ends, the raw data is discarded. What we retain is the structured decision record only: the distilled output Witness posts to your PR.

### What we store

- Structured decision records (the content of Witness comments)
- GitHub App installation metadata (repo name, installation ID)
- Approval and flag signals on individual decisions

We do not store raw Claude Code session transcripts. We do not store source code. We do not store file contents.

### Data in transit

All data between your environment and Witness servers is transmitted over TLS 1.2+.

### GitHub permissions

Witness requests the minimum GitHub App permissions required to post inline PR comments. We do not request read access to your code beyond what GitHub provides for PR diff context.

### Access controls

Decision records are scoped to your installation. Witness uses API key-based isolation per tenant. No data from one installation is accessible to another.

### Questions

ro@membranelabs.org

---
---

## Privacy Page

**Title:** Privacy Policy

**Last updated:** September 2026
**Effective:** September 2026

---

### Who we are

Witness is a product of Membrane Labs. Contact: ro@membranelabs.org

### What we collect

**Information you provide:**
- Email address (if you contact us)
- GitHub installation metadata (repo name, organization, installation ID)

**Information collected automatically:**
- Structured decision records derived from Claude Code sessions
- Approval and flag signals on Witness PR comments
- Basic usage logs (install events, comment events)

**What we do not collect:**
- Raw Claude Code session transcripts
- Source code
- File contents

### How we use it

We use collected information to:
- Operate and improve Witness
- Post decision summaries to your pull requests
- Respond to support requests

We do not sell data. We do not use your data to train models.

### Data retention

Structured decision records are retained for as long as your GitHub App installation is active. You can request deletion at any time by emailing ro@membranelabs.org. We will delete your records within 30 days of the request.

### Third parties

Witness uses GitHub as the surface for PR comments. Your use of GitHub is governed by GitHub's own privacy policy. We do not share your data with other third parties.

### Your rights

You may request access to, correction of, or deletion of your data at any time. Email ro@membranelabs.org.

### Changes

We will update this page when the policy changes. The effective date above reflects the most recent revision.

### Contact

ro@membranelabs.org
