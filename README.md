<p align="center">
  <picture>
    <img src="./images/logo-light.png" alt="adapts logo" width="350" />
  </picture>
</p>

<h1 align="center">Adapts</h1>
<p align="center">
  Chat with your wikis straight from your IDE &nbsp;·&nbsp; Auto-generate Wiki-style docs on every merge<br/>
  <a href="https://adapts.wiki" target="_blank">adapts.wiki</a> &nbsp;|&nbsp; <a href="https://adapts.app" target="_blank">adapts.app</a>
</p>

---

## Contents

- [What is Adapts?](#what-is-adapts)
- [Getting Started — Chat Assistant](#-getting-started-chat-assistant)
  - [Install the Plugin](#install-the-plugin)
  - [Account Setup](#account-setup)
  - [Using the Assistant](#how-to-use-the-adapts-assistant)
- [Wiki Generation — Code to Wiki](#-wiki-generation--code-to-wiki)
  - [What the workflow does](#what-the-workflow-does)
  - [Quick-start](#-quick-start)
  - [Customisation Tips](#-customisation-tips)
  - [Troubleshooting](#-troubleshooting)
  - [Security Considerations](#-security-considerations)
  - [Accessing your Wiki](#-accessing-your-wiki)
- [Latest Releases](#-latest-releases)
- [Support / Questions](#-support--questions)

---

## What is Adapts?

**Adapts** turns your codebase into living documentation — automatically.

- **Chat Assistant** — Ask questions about your codebase in natural language, right from IntelliJ, Cursor, or VSCode. Powered by wikis generated from your code.
- **Code to Wiki** — Every time a PR merges into `main`, a GitHub Action generates up-to-date Wiki-style documentation and publishes it to [adapts.wiki](https://adapts.wiki).

No context-switching. No stale docs. Just merge and go.

---

## 💬 Getting Started-Chat Assistant

Chat with your wikis straight from your IDE.

### Install the Plugin

| IDE | How to install | Latest Adapts Version |
| --- | -------------- | ----------- | 
| **IntelliJ** | *Settings ▸ Plugins ▸ Marketplace* — search **"Adapts Assistant"** | 1.0.6
| **Cursor** | Marketplace panel — search **"Adapts Assistant"** | 0.0.3
| **VSCode** | Extensions panel — search **"Adapts"** | 0.0.3

<details>
<summary><strong>IntelliJ — step-by-step screenshots</strong></summary>

Browsers supported: Chrome and Edge

1. Go to the Settings icon. Click on the Plugins option.

<img width="350" alt="image" src="./images/settings-panel-with-plugins-search.png" />

2. Go to Marketplace and search "Adapts Assistant".

<img width="350" alt="image" src="./images/screenshot-of-a-marketplace-search-for-adapts-assistant.png" />

3. Click "Apply" and then "Ok".

<img width="350" alt="image" src="./images/software-configuration-window.png" />

4. The Adapts icon will appear on the left side panel.

<img width="350" alt="image" src="./images/settings-menu-for-adapts-assistant-plugin.png" />

</details>

<details>
<summary><strong>Cursor — step-by-step screenshots</strong></summary>

1. Click on the Marketplace icon at the top of the left panel.

<img width="350" alt="image" src="./images/app-store-page-with-multiple-ai-agents.png" />

2. Search "Adapts Assistant".

<img width="350" alt="image" src="./images/software-marketplace-with-search-results.png" />

3. Find the Adapts listing and click install.

<img width="350" alt="image" src="./images/visual-studio-code-interface-displaying-adapts-option.png" />

<img width="350" alt="image" src="./images/adapts-application-information.png" />

</details>

<details>
<summary><strong>VSCode — step-by-step screenshots</strong></summary>

1. Click on the Extensions icon in the left panel.

<img width="350" alt="image" src="./images/vs-code-extensions-menu-displayed.png" />

2. Search "Adapts" and click install.

<img width="350" alt="image" src="./images/screenshot-of-code-extension-marketplace.png" />

</details>

---

### Account Setup

> ⚠️ **Mac users:** set **Chrome** as your default browser before beginning the login process.

1. Click the Adapts icon in your IDE's side panel. The Login/Signup screen will appear.

<img width="350" alt="image" src="./images/login-screen-for-adapts-with-google-and-microsoft-options.png" />

2. Your admin should have added you as a user.
   - Go straight to **Sign In** to access your account.
   - Otherwise, click **Sign Up** and choose your SSO provider.

**NOTE:**

During login you may see this dialog — click **Allow**.

<img width="350" alt="image" src="./images/february-15-2026-7-02-18-pm-screenshot.png" />

If the dialog doesn't appear and authentication still fails:

1. Click the **Lock icon** in the address bar.
2. Check **Permissions for this site**.
3. Set **Local network access** to **Allowed**.
4. Close the window and re-login.

<img width="350" alt="image" src="./images/february-16-2026-11-19-53-pm-screenshot.png" />

You should see this confirmation in your browser. You can now return to your IDE.

<img width="350" alt="image" src="./images/web-browser-sign-in-confirmation.png" />

---

### How to use the Adapts Assistant

Once logged in, you should see a chat window.

1. Click the **Select wiki** dropdown (top-left of the chat window) to choose which wiki to query.

<img width="350" alt="image" src="./images/chat-interface-with-wiki-selection.png" />

2. Select a wiki and start asking questions.

<img width="350" alt="image" src="./images/interface-showing-chat-tool-with-selected-wiki.png" />

From here you can:

- Ask questions about the codebase
- Change the LLM model

<img width="350" alt="image" src="./images/software-interface-with-chatbot-and-code-window.png" />

- View the source repo or the generated wiki
  
<img width="350" alt="image" src="./images/adapts-software-interface.png" />

The toolbar above the chat window lets you start a new chat, view history, change settings, or log out.

<img width="350" alt="image" src="./images/digital-interface-with-icon-menu.png" />

> ⚠️ On the plugins, you may choose one wiki per chat. To query a different wiki, start a new chat. Multi-wiki selection for richer context is available on the web app only at the moment.


You're all set! For feedback, contact <support@adapts.ai>.

---

## 📖 Wiki Generation — Code to Wiki

Automatically generates Wiki-style documentation in [adapts.wiki](https://adapts.wiki) every time a pull-request is merged into `main`.

### What the workflow does

```mermaid
flowchart LR
    %% Subgraph definitions
    subgraph Setup
        A[Add .github/workflows/action.yml into your repo]
    end
    subgraph Trigger
        B[Merge a PR in main branch]
    end
    subgraph Execution
        C[GitHub Action runs and calls Adapts API]
    end
    subgraph Monitoring
        D[Check Wiki generation progress by logging into adapts.app]
        E[Once Wiki is generated, click View to access it]
    end
    subgraph Access
        F[Login to adapts.wiki using the same email address]
    end

    %% Flow connections
    A --> B --> C
    C --> D
    D --> E
    E --> F
    C --> F

    class A setup
    class B trigger
    class C exec
    class D,E monitor
    class F access

```

| Stage                    | Purpose                                                                                                                                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Checkout / Setup**     | Fetches your repo and installs Python 3.11 plus runtime dependencies (`requests`, `adaptsapi`).                                                                                                                |
| **Author e-mail lookup** | Uses GitHub's GraphQL API to obtain the PR author's **organisation-verified e-mail** (Enterprise Cloud feature). Falls back to the head-commit author e-mail if needed.                                       |
| **Repo intel**           | Calculates repository size in bytes (for metadata) and determines dominant language.                                                                                                                           |
| **Adapts API call**      | Sends a signed request to Adapts' `/generate_wiki_docs` endpoint so the service can pull the code and build Wiki pages.                                                                                        |

---

### ⚡ Quick-start

1. **Signup for Adapts: Code to Wiki**
   Signup at [`adapts.app`](https://adapts.app) with your github email address.

2. **Copy the workflow file**
   Save [`.github/workflows/action.yml`](./action.yml) into your own repo under the same path.

3. **Add required secrets**
   Go to *Settings ▸ Secrets and variables ▸ Actions* and add:

   | Secret                  | Where to get it                              |
   | ----------------------- | -------------------------------------------- |
   | `ADAPTS_API_KEY`        | Request from <contact@adapts.ai>             |
   | `ENTERPRISE_READ_TOKEN` | Fine-grained PAT (org admin) **or** GitHub App installation token |

   <details>
   <summary><strong>SSO note</strong></summary>
   If your org enforces SAML/OIDC SSO, remember to <strong>authorise</strong> the PAT after creating it.
   </details>

   For detailed instructions on adding secrets, see the [official GitHub documentation on using secrets in GitHub Actions](https://docs.github.com/en/actions/how-tos/writing-workflows/choosing-what-your-workflow-does/using-secrets-in-github-actions).

4. **Verify domain settings**
   Ensure your org has **verified its corporate e-mail domain** and each developer has added that address to GitHub.

5. **Push or merge a PR**
   Merge into `main` and watch for a ✅ Success log entry.

---

<details>
<summary><strong>⚙️ Environment Variables</strong></summary>

| Name                       | Source                         | Purpose                                          |
| -------------------------- | ------------------------------ | ------------------------------------------------ |
| `GH_TOKEN`                 | `ENTERPRISE_READ_TOKEN` secret | Used by `gh` CLI for GraphQL calls               |
| `ADAPTS_API_KEY`           | Secret                         | Bearer token for Adapts AI API                   |
| GitHub defaults (`GITHUB_…`)| Provided by Actions            | Context for repo, actor, etc.                    |

</details>

---

### 🛠️ Customisation Tips

- **Target branch**: edit `on.pull_request.branches`.
- **Monorepos**: document sub-directories by filtering or passing extra metadata.
- **Non-Enterprise orgs**: remove GraphQL step and rely on commit e-mails.
- **Self-hosted runners**: install the GitHub CLI or add an explicit install step.

---

### 🐞 Troubleshooting

| Symptom                                                           | Likely cause                              | Fix                                                                                   |
| ----------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------- |
| `gh: Expected NAME, actual: UNKNOWN_CHAR`                         | Multiline GraphQL passed incorrectly      | Keep the query on **one line**                                                       |
| `organizationVerifiedDomainEmails` unavailable                    | Non-Enterprise plan                       | Remove this step or migrate to Enterprise Cloud                                       |
| API returns `401`                                                 | Missing/invalid `ADAPTS_API_KEY`          | Re-issue key in Adapts AI console                                                     |
| Author e-mail is `noreply@users.github.com`                       | Developer hasn't added corporate e-mail   | Ask them to add it via GitHub Profile ▸ Emails                                       |

---

### 🔐 Security Considerations

- Tokens are **read-only** and never leave GitHub infra.
- Only **metadata** (URL, size, language) is sent to Adapts AI.
- Source code is fetched by Adapts AI via the provided GitHub token.

---

### 🌐 Accessing your Wiki

1. Visit [adapts.app](https://adapts.app)
2. **Log in** with the **same e-mail** you use on GitHub
3. Navigate to **Application Wikis** ➡️ **Your Repo Name** ➡️ **Click on View**
4. Enjoy your freshly generated Wiki!

---
## 🚀 Latest Releases

### Context Enhancement: Multi-wiki chat context

Users can now choose up to 3 wikis to include in the assistant's chat context for more relevant answers.

<details>
<summary><strong>Release notes & how to use</strong></summary>

**What's new** — Context Enhancement: Users can now choose up to 3 different wikis to include in their assistant's chat context to get more relevant output.

**Why we added this** — With wider context it's easier for developers to avoid breaking API contracts and duplicating business logic, and for architects to avoid drift and cross-service tight coupling.

**Scope** — Limited to the web app for now (as of February 25, 2026). Not applicable to existing conversations.

**How to use**

1. Open a new chat conversation. The wiki selection dropdown now says "Select one or more wikis."

   <img width="350" alt="image" src="./images/select-one-or-more-wikis.png" />

2. Type a wiki name to search and select, or hover over service names to choose the wiki(s) you want.

   <img width="350" alt="image" src="./images/dropdown-menu-interface-showing-search-results.png" />

   <img width="350" alt="image" src="./images/dropdown-menu-interface.png" />

3. Once you've chosen your wikis and model, continue as usual.

</details>



### Wiki Generation: Workflow Documentation

Workflow documentation automatically traces your codebase to capture end-to-end workflows, including functions, inputs, outputs, and business logic.

<details>
<summary><strong>Release notes & how to use</strong></summary>

**What's new** — A 'Workflow Documentation' section has been added to every wiki, tracing through your codebase to document workflows, functions, inputs, outputs, and business logic.

**Why we added this**

1. **Feature sunsetting & migration** — Identify all components involved in a feature for safer modernization.
2. **Technical debt cleanup** — Find dead code (functions/classes not referenced in any workflow) and remove it safely.
3. **Architecture understanding** — See how the application works at a detailed level across the repo.

**Scope** — Applies to past and present wikis. Contact support@adapts.ai if you don't see workflow documentation.

**How to use** — Open any wiki and scroll to the *Workflow Documentation* section.

<img width="350" alt="image" src="./images/software-documentation-interface.png" />

</details>

---

### ❓ Support / Questions

Open an issue in this repo or email <support@adapts.ai> with your workflow logs (mask secrets) and we'll help you get set up.

---

_Ready to give it a spin? Merge into `main` and watch your docs appear!_
