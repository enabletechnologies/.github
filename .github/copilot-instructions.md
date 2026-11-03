# ENABLE Issue Creation

Use this workflow when asked to create, file, open, draft, or update an issue
or ticket for an `enabletechnologies` repository, including "let's create an
issue". It does not apply to unrelated coding requests.

## Source and Routing

Read `config.yml` and the selected YAML form from the organization templates:
<https://github.com/enabletechnologies/.github/tree/HEAD/.github/ISSUE_TEMPLATE>
on the current default branch before drafting or submitting. In the template
repository, use local files. Honor explicit target-repository template overrides
and explain differences. If retrieval fails, request the template contents;
do not submit a guessed form.

Infer the form from intent and verified context:

| Intent | Template | Issue Type |
| --- | --- | --- |
| Broken existing behavior, unexpected behavior, or regression | `1-bug-report.yaml` | `Bug` |
| Roadmap initiative spanning multiple enhancements or tasks | `2-epic-request.yaml` | `Epic` |
| New functionality or improved behavior | `3-feature-request.yaml` | `Enhancement` |
| Documentation or design/code documentation work | `4-documentation.yaml` | `Documentation` |
| Add a library, dependency, or development tool | `5-library-request.yaml` | `Enhancement` |
| Standalone testing or test coverage work | `90-testing-test-request.yaml` | `Test` |
| Provision or change infrastructure | `91-devops-infra-request.yaml` | `Task` |
| Application deployment or deployment pipeline work | `92-devops-application-request.yaml` | `Task` |

- Prefer a specialized form for the primary work; a malfunction or regression
  remains a bug, including in deployment or infrastructure.
- Honor an explicit compatible category choice; clarify conflicting choices
  before submission.
- If the user only says "let's create an issue", ask for the problem or desired
  change before selecting a form.
- Follow `config.yml`: report suspected security vulnerabilities privately to
  `cloudops@enable-technologies.com`, not in public issues. Route general ideas
  without actionable work to
  <https://github.com/orgs/enabletechnologies/discussions>.

## Draft and Create

- Determine the target repository from an explicit choice or unambiguous
  workspace context; otherwise ask. The `.github` repository supplies templates,
  not the default destination for product tickets.
- Parse YAML as structured data. Preserve field labels, order, dropdown options,
  required versus optional fields, checkbox wording, links, and static review
  instructions. For API/CLI creation, render fields as Markdown headings and
  checkboxes as checklists; omit introductory thank-you text.
- Write a descriptive title. Preserve meaningful prefixes such as `[Epic]:` and
  `[Deps] Add dependency -`; replace a generic title such as `Bug` with a specific
  summary.
- Apply the form's `type`, `labels`, and `projects` as distinct metadata. Do not
  invent labels from issue types. API/CLI tools may not apply form metadata
  automatically: set it explicitly where supported and report metadata blocked
  by tools or permissions.
- For bugs, include observed and expected behavior in `Description`, plus
  reproduction steps and context when known. Request required
  `Relevant log output`; state that none are available only when the user
  confirms this. Never fabricate logs.
- For enhancements, provide testable `Success and Failure Criteria` and retain
  every `Considerations` checkbox. For epics, collect required `Source`,
  `Category`, `Description`, and `Comments`, using an exact allowed source option.
- For dependencies, retain all `Sanity Checks` and required evaluation fields:
  description, license, similar libraries, production dependencies, Snyk
  analysis, code evaluation, and references, plus reviewer instructions. Never
  invent package evaluations or audit findings.
- For documentation, testing, and DevOps, follow the chosen form's fields; do
  not make optional criteria mandatory.
- Fill fields from user input and verified evidence. Ask concise questions for
  missing required information. Drafts may mark gaps as `Needs input`; do not
  submit unresolved required fields.
- Leave checkboxes unchecked unless the user or verified evidence confirms
  completion. Resolve required confirmations before submission; never check
  boxes merely to satisfy validation.
- Include known relevant paths, related issues, and parent epic links. Never
  invent issue numbers, environments, root causes, or completion claims. Exclude
  secrets and sensitive customer data.
- Briefly identify the selected form and why it fits. Draft-only requests must
  not publish. For explicit creation requests, use available GitHub tools after
  resolving required inputs; clarify authorization if publishing intent is
  unclear.
- Before submission, verify the repository, title, body, required confirmations,
  and metadata against the form. Do not silently fall back to a blank issue;
  `config.yml` disables blank issues.
- If tools or permissions prevent creation, provide a template-shaped draft and
  explain the limitation. Claim creation only after a successful tool result;
  return the issue URL and any pending metadata.

## Examples

- "Let's create an issue: login returns HTTP 500 after the latest release"
  -> Bug Report.
- "Create a ticket to add CSV export to transactions" -> Feature/Enhancement Request.
- "Create an issue to add a Python library" -> Add new dependency.
- "Open a ticket to provision a staging database" -> Devops Infra Request.
- "Let's create an issue" -> Ask for the problem or desired change, then choose
  the form.
