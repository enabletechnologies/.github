# Introduction
Build platforms and services which extends the right financial services to all people

enabletechnologies/.github is a special repository.

The [Public Readme](/profile/README.md) will appear on the organization's profile.

## Copilot Issue Creation

[Copilot instructions](.github/copilot-instructions.md) select the organization's issue form from the user's request and read that form before drafting or creating a ticket.

For organization-wide activation, an owner must put that file's contents in **Organization Settings > Copilot > Preferences and instructions** and save. See [GitHub's documentation](https://docs.github.com/en/copilot/customizing-copilot/adding-organization-custom-instructions-for-github-copilot).

Instructions in this repository are not automatically inherited by other repositories. Organization instructions currently support sessions on the GitHub website (cloud sandboxes or GitHub Actions) and Copilot code review, not local client sessions. For VS Code and other supported local clients, add the following to each repository's `.github/copilot-instructions.md`, preserving existing instructions:

```markdown
## Issue Creation

When asked to create, draft, or update an issue or ticket, fetch and follow https://github.com/enabletechnologies/.github/blob/HEAD/.github/copilot-instructions.md and read its selected organization issue form before proceeding. Infer bug versus enhancement or a specialized category from the request. Ask for details if intent is unclear. If retrieval fails, request the policy/template contents rather than guessing. Use this repository as the destination unless the user explicitly selects another repository.
```

Push the shared policy to the default branch before relying on its remote URL. Issue creation requires GitHub tools and permissions; otherwise Copilot supplies a draft. Instructions guide behavior but do not enforce form validation at the API level.
