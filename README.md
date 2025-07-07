# Generate Wiki Docs – adapts

Automatically generates Wiki‑style documentation in @adapts.wiki every time a pull‑request is merged into **`main`**.

---

## What the workflow does

| Stage                    | Purpose                                                                                                                                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Checkout / Setup**     | Fetches your repo and installs Python 3.11 plus runtime dependencies (`requests`, `adaptsapi`).                                                                                                                |
| **Author e‑mail lookup** | Uses GitHub’s GraphQL API to obtain the PR author’s **organisation‑verified e‑mail** (Enterprise Cloud feature). Falls back to the head‑commit author e‑mail if the user hasn’t registered a verified address. |
| **Repo intel**           | Calculates repository size in bytes (for metadata) and determines dominant language.                                                                                                                           |
| **Adapts API call**      | Sends a signed request to Adapts’ `/generate_wiki_docs` endpoint so the service can pull the code and build Wiki pages.                                                                                    |

---

## Quick‑start

1. **Copy the workflow file**
   Save the YAML from [`/.github/action.yml`](./action.yml) (this repo) into your own repository under the same path.

2. **Add required secrets**
   Open *Settings ▸ Secrets and variables ▸ Actions* and add:

   | Secret                                                         | Where to get it                                                      | Scope needed |
   | -------------------------------------------------------------- | -------------------------------------------------------------------- | ------------ |
   | `ADAPTS_API_KEY`                                               | Contact us at contact@adapts.ai to get an API key.                              | –            |
   | `ENTERPRISE_READ_TOKEN`                                        | **Option A:** Fine‑grained PAT created by an org admin.              |              |
   | **Option B:** Installation token from a GitHub App you manage. | `Organization members: Read‑only` (PAT) · `Members: Read‑only` (App) |              |

   > **SSO note**
   > If your org enforces SAML/OIDC SSO, remember to **authorise** the PAT for the organisation after creating it (GitHub prompts for this).

3. **Verify domain settings**
   The workflow retrieves a developer’s e‑mail via `organizationVerifiedDomainEmails`, which only works if:

   * Your org has **verified its corporate e‑mail domain** (Org Settings ▸ Identity ▸ Verified domains), **and**
   * Each developer has added an address on that domain to their GitHub account.

4. **Push or merge a PR**
   Merge any pull request into `main`; the action should run and you’ll see a *✅ Success* log entry once the Adapts API responds.

---

## Environment variables used by the workflow

| Name                             | Source                         | Description                                  |
| -------------------------------- | ------------------------------ | -------------------------------------------- |
| `GH_TOKEN`                       | `ENTERPRISE_READ_TOKEN` secret | Used by the `gh` CLI to call GraphQL.        |
| `ADAPTS_API_KEY`                 | Secret                         | Bearer token for Adapts AI’s API.            |
| GitHub default vars (`GITHUB_…`) | Provided by Actions            | Repo/actor context passed to Python snippet. |

---

## Customisation tips

* **Different target branch** – change the branch list under `on.pull_request.branches`.
* **Monorepos** – if you only want to document a sub‑directory, pass extra metadata in the payload or filter files before computing size.
* **Non‑Enterprise orgs** – remove the GraphQL step and rely solely on commit e‑mails (may be noreply aliases).
* **Self‑hosted runners** – ensure the GitHub CLI (`gh`) is installed or add an explicit `brew install gh`/`apt‑get install gh` step.

---

## Troubleshooting

| Symptom                                                           | Likely cause                              | Fix                                                                                   |
| ----------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------- |
| `gh: Expected NAME, actual: UNKNOWN_CHAR`                         | Multiline GraphQL passed with `-f query=` | Keep the query on **one line** (already done in sample).                              |
| `GraphQL: field "organizationVerifiedDomainEmails" doesn't exist` | Repo is on non‑Enterprise plan            | You can’t use this field; fall back to commit e‑mails or migrate to Enterprise Cloud. |
| API returns `401`                                                 | `ADAPTS_API_KEY` missing/invalid          | Re‑issue the key in the Adapts AI console and update the secret.                      |
| Author e‑mail resolves to `noreply@users.github.com`              | Dev hasn’t added a verified address       | Ask them to add their corporate e‑mail to GitHub (Profile ▸ Emails).                  |

---

## Security considerations

* The PAT/App token is scoped **read‑only** and never leaves GitHub’s infra.
* The workflow sends **only metadata** (repo URL, size, language) plus the tokenised refresh token to Adapts AI; no source code is uploaded directly.
* Adapts AI pulls the repository via the provided GitHub token for further analysis.

---

## Support / questions

Please open an issue in this repo or contact **[support@adapts.ai](mailto:support@adapts.ai)** with the workflow logs (mask secrets) and we’ll help you get set up.
