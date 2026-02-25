<p align="center">
  <picture>
    <img src="./images/logo-light.png" alt="adapts logo" width="250" />
  </picture>
</p>

<h1 align="center">Adapts</h1>
<p align="center">
  Chat with your wikis straight from your IDE &nbsp;·&nbsp; Auto-generate Wiki-style docs on every merge<br/>
  <a href="https://adapts.wiki" target="_blank">adapts.wiki</a> &nbsp;|&nbsp; <a href="https://adapts.app" target="_blank">adapts.app</a>
</p>

---

## Contents

- [Latest Releases](#latest-releases)
- [Getting Started — Chat Assistant](#getting-started--chat-assistant)
  - [IntelliJ](#intellij)
  - [Cursor](#cursor)
  - [VSCode](#vscode)
  - [How To Use The Assistant](#how-to-use-the-adapts-assistant)
- [Wiki Generation — Code to Wiki](#wiki-generation--code-to-wiki)
  - [What the workflow does](#what-the-workflow-does)
  - [Quick-start](#quick-start)
  - [Customisation Tips](#customisation-tips)
  - [Troubleshooting](#troubleshooting)
  - [Security Considerations](#security-considerations)
  - [Accessing your Wiki](#accessing-your-wiki)
  - [Support / Questions](#support--questions)

---

## 🚀 Latest Releases

<details>
<summary><strong>Context Enhancement: Multi-wiki chat context</strong></summary>

### What's new

_Context Enhancement: Users can now choose upto 3 different wikis to include in their assistant's chat context to get more relevant output._

### Why did we add this? 

With an even wider context it will be easier for 
> Developers to avoid things like breaking API contracts and duplicating business logic across services 
> Architects to avoid architecture drift and cross-service tight coupling

### Scope

This is limited to the web app in the absence of future updates after February 25, 2026. 
This feature will not be applicable to old conversations. 

### How to use

1. Open a new chat conversation. The wiki selection dropdown now says "Select one of more wikis."

   <img width="350" height="137.5" alt="image" src="https://github.com/user-attachments/assets/50f2a029-dd84-4926-99f6-2dbc8bc94541" />

3. If you know your wiki names you can type its name to search and select, as show below

   <img width="350" height="202.4" alt="image" src="https://github.com/user-attachments/assets/c253b955-f594-4643-9c20-d1dc14a1251b" />

  Or, you can hover over service names to choose the wiki(s) you want to include as below

  <img width="350" height="169.15" alt="image" src="https://github.com/user-attachments/assets/08612737-df5c-4dbf-9803-16e80d53478a" />

4. Once you choose your wikis and model, you can continue as usual. 

</details>

<details> 
<summary><strong>Documentation Improvement: Workflow Visualizations</strong> </summary>

### What's New 

_Adapts Code-to-Wiki now traces workflows from entry points through all functions, inputs, and outputs within repositories_

### Why did we add this?

**Feature Sunsetting & Migration** Developers can now identify all components involved in specific features, making it easier to plan modernization efforts and ensure no business logic is missed during migrations.
**Technical Debt Cleanup** Developers can discover dead code—functions and classes that aren't referenced in any workflows—so you can safely remove unused code without business impact.
**Architecture Understanding** Architects can gain clear visibility into how your application works at a detailed level, helping developers and product managers understand complex workflows across your entire repository

</details>

---

## 💬 Getting Started — Chat Assistant

Chat with your wikis straight from your IDE.

### Plugins

1. [IntelliJ](#intellij)
2. [Cursor](#cursor)
3. [VSCode](#vscode)
4. [How To Use The Assistant](#how-to-use-the-adapts-assistant)

---

### IntelliJ

IntelliJ IDE should be on the version: 2025 +

Browsers: Chrome and Edge

#### Plugin Installation for IntelliJ

1. Go to Setting Icon. Click on the Plugins option on the IntelliJ platform.

<img width="394" height="371" alt="image" src="https://github.com/user-attachments/assets/34ed6b63-8b45-466f-a9d4-a0668a5f5f9c" />
<br>

2. Go to Marketplace option and search "Adapts Assistant".

<img width="1024" height="275" alt="image" src="https://github.com/user-attachments/assets/2bd285df-fad2-4aed-acda-73ef1771a015" />

3. Click "Apply" and then "Ok".

<img width="629" height="328" alt="image" src="https://github.com/user-attachments/assets/23af5204-12b4-471f-9dfc-3cedd358370a" />

4. You will start seeing the Adapts icon on the left side panel. Click on it and the Login/signup screen will appear.

<img width="385" height="393" alt="image" src="https://github.com/user-attachments/assets/3b778829-a741-4688-9d67-3bba5ee00a55" />

#### Account Setup

> ⚠️ Mac Users, please choose **Chrome** as your default browser before beginning the login process.

1. You will start seeing the Adapts icon on the left side panel. Click on it and the Login/signup screen will appear.

<img width="387" height="352" alt="image" src="https://github.com/user-attachments/assets/f0c03625-4bb5-4b55-b232-0185e75c5c62" />

2. Your admin should have added you as a user.

- You can go straight to sign-in to access your adapts account.
- Otherwise, click on the Sign Up option, and choose your SSO provider.

**NOTE:**

During the log-in you may see this dialogue box on the screen. Click on Allow.

<img width="339" height="209" alt="image" src="https://github.com/user-attachments/assets/e6ad805d-111b-4f07-8074-6622ec393c45" />

If you don't see the above dialog and the authentication still fails, then:

1. Click on the Lock icon in the address bar.
2. Check Permissions for this site.
3. Make sure Local network access is set to Allowed.
4. After this is done, close this window and re-login.

<img width="365" height="265" alt="image" src="https://github.com/user-attachments/assets/a20546fc-a3c0-4dba-bd78-4517c7bfd6a7" />

You should see the following notification at the center of your browser screen. You can now continue to IntelliJ

<img width="640" height="386" alt="image" src="https://github.com/user-attachments/assets/bd1a75dd-ce0c-4240-9762-b52949ec2d4b" />

---

### Cursor

#### Plugin Installation for Cursor

1. Click on the Marketplace Icon at the top of the left panel.

<img width="350" height="300" alt="image" src="https://github.com/user-attachments/assets/603dc13b-9e88-47f9-b2a6-82fb58b8906c" />

2. Once in the marketplace, search "Adapts Assistant".

<img width="350" height="300" alt="image" src="https://github.com/user-attachments/assets/28afa995-c7a8-4f9f-9668-8c135de6d395" />

3. Scroll down until you find the Adapts listing and click install.

<img width="350" height="423" alt="image" src="https://github.com/user-attachments/assets/01e3d98e-3558-4815-991e-2805ec5d92f8" />

<img width="350" height="252" alt="image" src="https://github.com/user-attachments/assets/be0739b3-a9e9-42fa-a8a6-bc5b17d89419" />

#### Account Setup

> ⚠️ Mac Users, please choose **Chrome** as your default browser before beginning the sign-in/sign-up process.

1. You will start seeing the Adapts icon in the left panel's dropdown . Click on it and the Login/signup screen will appear.

<img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/d48bd00a-d5b0-4c33-a048-19643b40dcba" />

<p align="center">↓</p>

<img width="350" height="318" alt="image" src="https://github.com/user-attachments/assets/f0c03625-4bb5-4b55-b232-0185e75c5c62" />

3. Your admin should have added you as a user.

- You can go straight to sign-in to access your adapts account.
- Otherwise, click on the Sign Up option, and choose your SSO provider.

**NOTE:**

During the log-in you may see this dialogue box on the screen. Click on Allow.

<img width="350" height="216" alt="image" src="https://github.com/user-attachments/assets/e6ad805d-111b-4f07-8074-6622ec393c45" />

If you don't see the above dialog and the authentication still fails, then:

1. Click on the Lock icon in the address bar.
2. Check Permissions for this site.
3. Make sure Local network access is set to Allowed.
4. After this is done, close this window and re-login.

<img width="350" height="254" alt="image" src="https://github.com/user-attachments/assets/a20546fc-a3c0-4dba-bd78-4517c7bfd6a7" />

You should see the following notification at the center of your browser screen. You can now continue to Cursor

<img width="350" height="212" alt="image" src="https://github.com/user-attachments/assets/bd1a75dd-ce0c-4240-9762-b52949ec2d4b" />

---

### VSCode

#### Plugin Installation for VSCode

1. Click on the Marketplace Icon in the left panel.

<img width="350" height="358" alt="image" src="https://github.com/user-attachments/assets/7e396e51-87ff-4571-b8ed-9464f039c57c" />

2. Once in the marketplace, search "Adapts". The Adapts app should be the first search result. Click on install.

<img width="374" height="220" alt="image" src="https://github.com/user-attachments/assets/d3c6d009-88d7-4db1-804b-aa193ffa1ca2" />

#### Account Setup

> ⚠️ Mac Users, please choose **Chrome** as your default browser before beginning the sign-in/sign-up process.

1. You will start seeing the Adapts icon in the left panel. Click on it and the Login/signup screen will appear.

<img width="350" height="390" alt="image" src="https://github.com/user-attachments/assets/3213dca9-450c-4544-9a72-48041ee2ef33" />

<p align="center">↓</p>

<img width="350" height="318" alt="image" src="https://github.com/user-attachments/assets/f0c03625-4bb5-4b55-b232-0185e75c5c62" />

3. Your admin should have added you as a user.

- You can go straight to sign-in to access your adapts account.
- Otherwise, click on the Sign Up option, and choose your SSO provider.

**NOTE:**

During the log-in you may see this dialogue box on your browser screen. Click on Allow.

<img width="350" height="216" alt="image" src="https://github.com/user-attachments/assets/e6ad805d-111b-4f07-8074-6622ec393c45" />

If you don't see the above dialog and the authentication still fails, then:

1. Click on the Lock icon in the address bar.
2. Check Permissions for this site.
3. Make sure Local network access is set to Allowed.
4. After this is done, close this window and re-login.

<img width="350" height="254" alt="image" src="https://github.com/user-attachments/assets/a20546fc-a3c0-4dba-bd78-4517c7bfd6a7" />

You should see the following notification at the center of your browser screen. You can now continue to Visual Studio Code

<img width="350" height="212" alt="image" src="https://github.com/user-attachments/assets/bd1a75dd-ce0c-4240-9762-b52949ec2d4b" />

---

### How to use the Adapts Assistant

Once logged in, you should see a chat window.

1. In the top left corner of the chat window, click on Select wiki dropdown to set the context for any QnA by choosing one of the wikis generated by adapts.

<img width="350" height="518" alt="image" src="https://github.com/user-attachments/assets/bf390920-9f62-448f-b4ba-58b7990e765b" />

2. Select the wiki you are interested in and ask questions about anything in it.

<img width="350" height="525" alt="image" src="https://github.com/user-attachments/assets/2baef725-d56d-44e5-9bf7-29c8a195e92c" />

After selecting the wiki, you will see the screen below.
You can:

- Ask questions
- Change LLM Model

<img width="353" height="721" alt="image" src="https://github.com/user-attachments/assets/a5c21630-5c83-4172-8f86-6b3f977e256e" />

Additionally, you can also use the buttons hightlighted below to:

- View Repo
- View Wiki

<img width="497" height="319" alt="image" src="https://github.com/user-attachments/assets/6be23611-0197-4450-b765-47edc5731810" />


> ⚠️ As of version 1.0.4, you may choose one wiki in every chat. If you would like to ask questions about a new wiki, you will need to start a new chat. We are currently wokring on
> releasing to allow multi-wiki selection in the same chat.

Right above the chat window, you can see options to:

- Start a new chat
- View chat history
- Change settings
- Logout

<img width="700" height="186" alt="image" src="https://github.com/user-attachments/assets/160d9317-59e3-41ba-a591-c8959a0e2dac" />

Congratulations! you're all set!

For further feedback please contact support@adapts.ai

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
3. Navigate to **Application Wiki's** ➡️ **Your Repo Name** ➡️ **Click on View**
4. Enjoy your freshly generated Wiki!

---

### ❓ Support / Questions

Open an issue in this repo or email <support@adapts.ai> with your workflow logs (mask secrets) and we'll help you get set up.

---

_Ready to give it a spin? Merge into `main` and watch your docs appear!_
