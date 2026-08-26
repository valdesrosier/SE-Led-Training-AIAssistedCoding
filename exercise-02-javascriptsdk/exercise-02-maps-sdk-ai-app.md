# Exercise 2 — Maps SDK for JavaScript + AI Components App

> 💡 **Tip:** Press `Ctrl+Shift+V` to view this file as a formatted preview (or `Cmd+Shift+V` on Mac).
> New to VS Code? Keep [Exercise 0 — VS Code and GitHub Copilot setup](../exercise-00-vscode-setup/exercise-00-vscode-setup.md) open for reference.

This is a deeper developer topic, so you have a choose-your-own-adventure ahead. Pick the path that matches your experience:

- **Step 1a – Beginner workflow:** Start here if you're new to the ArcGIS Maps SDK for JavaScript. It's a more straightforward introduction to the app development process.
  - **What you'll build:** a web app using the ArcGIS Maps SDK for JavaScript with OAuth sign-in — a full-screen choropleth map of U.S. counties colored by median household income from a Living Atlas ACS layer, plus a side panel chart that animates to show a county's stats as you hover and highlights that county on the map.

- **Step 1b – Advanced workflow:** Start here if you're comfortable with the SDK and want to dive right in. It covers OAuth, the ArcGIS AI Components, and more complex app development and troubleshooting.
  - **What you'll build:** a web app using the ArcGIS Maps SDK for JavaScript and its AI Components — users sign in, load and switch between web maps, and chat with a set of agents (the built-in ones plus two custom agents you define).

We'll design it first using `/grill-with-docs`, then build it.

> [!IMPORTANT]
> After copilot has finished responding, you can review what files were created, deleted, or changed by expanding the **Files changed** section in the chat. You can also click on any file to see a diff of what was added or removed. If you don't like the changes, you can click **Undo** to undo them. If you are fine with the changes, you can click the blue **Keep** button.

![Command approval from copilot](../docs/assets/copilot-edits-keep-undo-buttons.jpg)

---

## Step 1a — The prompt - beginner workflow

> [!IMPORTANT]
> The prompt below uses a Client ID that requires an ArcGIS Online account in the [Esri Federal Organization](https://esrifederal.maps.arcgis.com/home/index.html). If you don't have one, follow [pre-work document 05](../docs/05-create-arcgis-online-oauth-application.md) to create your own OAuth application in any ArcGIS Online org to use instead.

1. Open a new chat in the GitHub Copilot panel by selecting the `+` button at the top of the window. Ensure your model is set to either **GPT-5.6 Sol** or **Claude Opus 5**.

2. Start by typing a forward slash (`/`) to see the list of available skills. Select `/grill-with-docs` from the list by arrowing up or down to highlight it and then press tab, but do not press enter yet.

3. Paste the following prompt after the pill.

```
Build a web app using the ArcGIS Maps SDK for JavaScript. Configure the login so the user can sign in to a named ArcGIS Online account enabled through this app client ID: AzFiycVu64TjjLrG.

Show a full-screen map of U.S. counties using a public ArcGIS Living Atlas demographic feature layer (please find a current public ACS county-level layer and confirm it loads). Color the counties by median household income as a choropleth.

Add a side panel with a chart. When I hover over a county, the chart should smoothly update to show that county's data, and the county name and key stats should appear above the chart. When I move off, the chart returns to a default state. Make the hover feel responsive and highlight the hovered county on the map.

Make it look polished: clean layout, a title, a legend, and a nice color ramp. Use a charting approach that animates between values on hover.

Serve the app over HTTP at http://localhost:5173. This client ID only accepts redirect
URLs beginning with http://localhost, so a plain-HTTP dev server (including the VS Code
Live Preview extension) cannot complete sign-in.

Verify only what works without credentials: the app builds, the dev server
serves http://localhost:5173, and the sign-in screen renders. Then stop and
hand it to me with a short list of what I should check after I sign in.
Do not simulate or fake a signed-in session.

Before grilling me on design decisions, use the js-sdk skill and the arcgis-docs-lookup skill to look up specific elements you are not sure about. Cap web research at 5 minutes.

Write all code and files for this project only inside the `exercise-02-javascriptsdk/` folder in this repo. Create it if it doesn't exist. Don't add or modify files anywhere else in the repo.
```

4. Press `Enter` to run the skill.

5. Skip Step 1b below and jump to Step 2.

## Step 1b — The prompt - advanced workflow

> [!IMPORTANT]
> The prompt below uses a Client ID that requires an ArcGIS Online account in the [Esri Federal Organization](https://esrifederal.maps.arcgis.com/home/index.html). If you don't have one, follow [pre-work document 05](../docs/05-create-arcgis-online-oauth-application.md) to create your own OAuth application in any ArcGIS Online org to use instead.

1. Open a new chat in the GitHub Copilot panel by selecting the `+` button at the top of the window. Ensure your model is set to either **GPT 5.6 Sol** or **Opus 5**.

2. Start by typing a forward slash (`/`) to see the list of available skills. Select `/grill-with-docs` from the list by arrowing up or down to highlight it and then press tab, but do not press enter yet.

3. Paste the following prompt after the pill.

```
I want to build a react web app using the ArcGIS Maps SDK for JavaScript and its AI Components. It should have:

1. ArcGIS Online sign in enabled through this app client ID: AzFiycVu64TjjLrG.

2. This web map already loaded into the app: ed546c8d53204931948ae409bed86a26

3. Add the out-of-the-box agents that come with the AI Components, and create two custom agents:
  - a custom agent that lets me add any layer from my ArcGIS organization to the map,
  - and another custom agent that lets me add any layer from the ArcGIS Living Atlas to the map.

Before grilling me on design decisions, use the the js-sdk skill and the arcgis-docs-lookup skill to look up specific elements you are not sure about. Cap web research at 5 minutes.

Serve the app over HTTP at http://localhost:5173. This client ID only accepts redirect
URLs beginning with http://localhost, so a plain-HTTP dev server (including the VS Code
Live Preview extension) cannot complete sign-in.

Verify the app yourself before handing it back. I will do the sign-in, but confirm the map and assistants all work, and confirm the sign-in screen disappears once signed in.

Write all code and files for this project only inside the `exercise-02-javascriptsdk/` folder in this repo. Create it if it doesn't exist. Don't add or modify files anywhere else in the repo.
```

4. Press `Enter` to run the skill.

## Step 2 — What happens next

1. Answer each question in the chat. You can answer however you like, as long it's clear to the model which question you are answering. You can also ask follow up questions to clarify anything you don't understand. The skill will write down the design as you go.
   - Example: "q1: agreed, q2: explain in less technical terms, q3-6: agreed, q7: yes but add ..."

> [!NOTE]
> Copilot may ask your approval to run commands during the course of a response. Be sure to review the **command summary** beneath the code preview to see what commands it wants to run. If you approve, click **Allow**. If you don't, click **Skip** and ask the model to clarify or change its approach.

![Command approval from copilot](../docs/assets/copilot-chat-run-command-approval.jpg)

> [!NOTE]
> **Scaling up to bigger builds:** For a small app like this, going straight from grilling to building is fine. For a bigger, multi-part app, this is where you'd add two steps first:
>
> - **`/to-spec`** — turns the design you just settled into a written spec you can review.
> - **`/to-tickets`** — breaks that spec into small, ordered tickets, each one a buildable chunk.
>
> **Why bother?** It keeps the AI working on one clearly-defined piece at a time instead of juggling the whole app at once. That's where large AI builds usually drift — losing track of earlier decisions as the work grows. The spec and tickets are the paper trail that keeps it on course.

2. When the design is settled, copilot may begin implementing on its own. If not you can use the `/implement` skill to tell it to start building the app and any other files needed for the project.

## Step 3 - Building and running your app

Because the agent designs the app during the interview, the exact run command depends on what it built (a plain HTML page, a Vite app, and so on). These steps work for any of them:

1. **Ask the agent how to run it.** Something like: _"How do I install dependencies and run this app locally?"_ For a Vite app that's usually `npm install` then `npm run dev`; for a plain HTML page it may just be the Live Preview extension.

2. **Open the local address** the run command prints (often `https://localhost:5173`) in your browser.

3. **Sign in** with your ArcGIS Online named account associated with the Client ID you provided when the app prompts you (if you used the included Client ID, this will be your Esri Federal login). If you used the provided Client ID, this will be your Esri Federal login.

4. Explore the app:

   For 1a, hover over the datasets, are the indicators and graphs in your app changing dynamically?

   For 1b, **try each agent** in the assistant chat:
   - ask a built-in agent to navigate or explore the map (e.g. _"how many big foot sightings are in California"_),
   - ask your **org-layer agent** to add a layer from your organization,
   - ask your **Living Atlas agent** to add a Living Atlas layer.

Test and iterate with the agent as needed.

> [!NOTE]
> If you're tracking your work in Git, add a `.gitignore` before you commit. The `node_modules/` folder holds tens of thousands of files you don't want in version control. Create a `.gitignore` in your project folder with this line:
>
> ```
> node_modules/
> ```
>
> Do this before your first commit. If you already staged `node_modules/`, run `git rm -r --cached node_modules/` to unstage it, then commit.

## Step 7 — OPTIONAL — Diagnose and fix bugs

- Use the **`/diagnosing-bugs`** skill on something that you notice is not working as expected.

## Step 8 — OPTIONAL — Add a feature or change the design

- Ask the assistant
- Start a **new `/grill-with-docs` session** scoped to just the new feature you want to add. Design it, then build it, just like before.

## Key Takeaways

### Building a new app or workflow outside of this exercise

You've built an example. Here's how to keep going once the workshop's over.

The same workflow will work for other apps and maps. Be specific in your prompts and utilize the skills.

If you didn't need to work through the OAuth workflow this time and used the provided Client ID, follow [pre-work document 05](../docs/05-create-arcgis-online-oauth-application.md) to learn more.

Once you've created the app and have an OAuth **Client ID**, you can ask the agent where to put it — usually an `.env.local` file or a config value. OAuth Client IDs are not secrets and are OK to share with the agent; API keys and client secrets are sensitive and should not be shared.

> [!IMPORTANT]
> NEVER share API keys or secrets with the agent. It doesn't need them to build your app, and they are sensitive information that should not be shared.

### When something breaks, or you want to add more

**When something breaks.** Instead of just telling the agent "it's not working," ask it to use **`/diagnosing-bugs`**. It runs a disciplined loop — reproduce the bug → shrink it down to the smallest failing case → form a hypothesis → instrument and test → fix → add a check so it can't come back. That structure is what makes it reliable on the hard bugs, where a plain "fix this" tends to send the AI in circles. For a quick typo it's overkill; for a "why is this behaving strangely" moment, reach for it.

**When you want to add a feature.** Resist the urge to bolt it on mid-conversation. Start a **new `/grill-with-docs` session** scoped to just the new piece — the same design-first flow you used the first time. Two reasons: the design of the addition gets the same careful interview the original did, and you start from a clean slate instead of a long, cluttered chat where the agent has half-forgotten earlier decisions. Design the addition, then build it, just like before.

## When to start a fresh chat (and how to carry your work over)

**When to start a new context window.** A chat has a limited working space, and a long one fills up — early instructions get buried, and answers start to wander or repeat. The signs: the agent forgets a decision you made earlier, its replies get vaguer, or it starts going in circles. We want to start a **new chat** before we get context degradation, rather than push a tired one further.

**How to not lose everything.** Before you switch, ask the agent to use **`/handoff`**. It compacts the current conversation into a short handoff document — the kind of thing you'd want a new teammate to read before picking up your work. A good handoff captures:

- **What you're building** — the goal, in a sentence or two.
- **Decisions already made** — the design choices you settled, so they don't get re-litigated.
- **Where you left off** — what's built and working so far.
- **What's next** — the immediate next step.

Open a fresh chat, tell your assistant to reference the new handoff document and the project, and the new session starts with a clean working space _and_ full context. If you also ran `/grill-with-docs`, a lot of this already lives in your `CONTEXT.md` and ADRs — the handoff doc is the lighter companion to those.
