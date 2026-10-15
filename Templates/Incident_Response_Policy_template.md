# Incident Response Policy (Template)

Security incidents happen even to well-run, well-intentioned projects. A short,
clear incident response policy turns a stressful, ad-hoc scramble into a
practiced, predictable process — and signals to users and downstream consumers that the
project takes security seriously.

This does not need to live in its own file. For most projects it fits
naturally as a section in `SECURITY.md`, or as a page in existing
documentation (e.g. `docs/incident-response.md`). A few paragraphs is enough
for a small project; larger projects will want more detail and named roles.

## Why adopt this

- Incidents are a matter of "when," not "if." Having a plan in place reduces
  response time and limits damage.
- A documented process helps contributors and users know what to expect when they
   report concerns.
- It demonstrates security maturity to downstream users, auditors, and
  regulators at minimal cost to maintain.
- A documented process turns "I'll figure it out if it happens" into real actions in a real sequence which can reveal the gaps in the plan before they are needed.


## Template

```markdown
## Incident Response Policy

### Scope
This policy covers security incidents affecting this project, including its
source code, infrastructure, release pipeline, maintainer accounts, and
contributor trust.

Security takes place in two places - before and after something goes wrong.  Other processes and policy should be in place to be preventative and cover things like reviewing merge requests before they are accepted, and vetting new contributions and contributors to a project before they are trusted.  This "Incident Response Policy", or IRP, is reactive and covers what happens if something has already gone wrong.


### What constitutes an incident

An incident can be many things.  In this context we are talking about hostile events that threaten the security of the product.
- Unauthorized code changes (e.g. a malicious commit or compromised
  maintainer account)
- Leaked secrets, credentials, or signing keys
- A vulnerability being actively exploited in the wild
- Compromised build or release infrastructure
- A compromised endpoint belonging to someone with repository or release
  access

An incident might also mean "a system outage that prevents a bug-fix from being shipped".  For the sake of the simple example of a small open source project, this will not be covered.


### Reporting a security issue
- Report to: <security@example.org>, or via a private security advisory on
  GitHub
- Never open a public issue for an active exploit or a leaked secret
- (We will | We aim to) acknowledge all reports within [X] business days

### Response process

[[ for each section below, write a few sentences about how you would go about each step of the response process, based on your project's specific needs.  If you had an incident, no matter how minor, recently you might use that experience to write about how you would wish to respond to the next one ]]

1. **Triage** — Confirm the incident, assess its scope and severity.
2. **Contain** — Revoke credentials, roll back affected commits, pull
   releases, rotate keys as needed.
3. **Eradicate** — Fix the root cause and patch the vulnerability.
4. **Recover** — Restore normal operations; re-issue a release if required.
5. **Disclose** — Notify affected users and publish an advisory, following
   coordinated disclosure practices.
6. **Review** — Conduct a post-incident review and document follow-up
   actions to prevent recurrence.

### Roles and responsibilities (optional, for larger projects)
- Incident lead: [name/role]
- Communications: [name/role]
- Technical response: [name/role]

### Contact and escalation
[Maintainer email addresses, chat channel, GPG keys if applicable]
```

## Illustrative examples

**Compromised endpoint (lost or stolen device)**
A maintainer's laptop is lost or stolen, and it was not protected with full
disk encryption. SSH keys, Git credentials, and signing keys stored on the
device are now potentially exposed. A documented incident response policy
ensures someone is responsible for promptly revoking the affected keys,
forcing re-authentication on CI/CD systems, and rotating any credentials the
device had access to — rather than the exposure going unnoticed for weeks.

**The XZ Utils backdoor (2024)**
Over a period of roughly two years, an attacker using the identity "Jia Tan"
built credibility within the xz-utils community, was granted co-maintainer
status, and ultimately inserted a backdoor into the project's build scripts
that targeted OpenSSH. The compromise was discovered largely by chance, and demonstrates why even such a relatively minor project will benefit from a pre-existing, written, incident response policy to help manage the impact of such an event. 

These examples illustrate that no matter the size of the open source project, incidents can happen, and incident response is a necessity.


## Recommendations

- Keep contact and escalation details current; outdated contact information
  delays response and erodes trust.
- Either include this within `SECURITY.md`, or link it prominently from that document so it is easy to find.
- A concise policy is far more valuable than no policy — start simple and
  expand it as the project matures.
