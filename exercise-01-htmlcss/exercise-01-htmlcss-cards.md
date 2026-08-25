# Exercise 1 — ArcGIS Hub: Glass Cards (HTML / CSS)

> 💡 **Tip:** Press `Ctrl+Shift+V` to view this file as a formatted preview (or `Cmd+Shift+V` on Mac).
> New to VS Code? Keep [Exercise 0 — VS Code and GitHub Copilot setup](../exercise-00-vscode-setup/exercise-00-vscode-setup.md) open for reference.

**What you'll build:** a set of modern "glassmorphism" cards in HTML and CSS that you can drop into an ArcGIS Hub site — frosted, semi-transparent panels that sit over a background image or map. Be creative with this as you give your prompt design information and answer the assistant's questions.

We'll design it first using `/grill-with-docs`, then build it.

> [!IMPORTANT]
> After copilot has finished responding, you can review what files were created, deleted, or changed by expanding the **Files changed** section in the chat. You can also click on any file to see a diff of what was added or removed. If you don't like the changes, you can click **Undo** to undo them. If you are fine with the changes, you can click the blue **Keep** button.

![Command approval from copilot](../docs/assets/copilot-edits-keep-undo-buttons.jpg)

---

## Step 1 — Open Visual Studio Code

1. In VS Code: **File → Open Folder** and open the folder location of your cloned respository from the pre-work.

2. Open a terminal inside VS Code: **Terminal → New Terminal** (or `` Ctrl+` ``).

3. Ensure you are in the root of the cloned repo in the terminal. You should see a prompt like this:

   Windows:

   ```
   PS C:\dev\SE-Led-Training-AIAssistedCoding>
   ```

   Mac:

   ```
   $ ~/dev/SE-Led-Training-AIAssistedCoding
   ```

   If you don't see that, use the `cd` command to navigate to the root of the cloned repo.

   Windows:

   ```
   cd C:\dev\SE-Led-Training-AIAssistedCoding
   ```

   Mac:

   ```
   cd ~/dev/SE-Led-Training-AIAssistedCoding
   ```

---

## Step 2 — Install the skills into this project

Run these two commands, one at a time, in the terminal:

### Command 1

```
npx skills@latest add mattpocock/skills
```

> **Windows note:** If the command above returns an error, try:
>
> `npx.cmd skills@latest add mattpocock/skills`

1. Your keyboard strokes will be to paste the above then hit enter to run.

2. If prompted with `Ok to proceed? (y)`, type `y` and hit `Enter`.

3. When the skills load, press the spacebar on your keyboard to select all skills. All the empty dots in the terminal will turn green indicating they have been selected. Press `Enter` to continue.

4. Matt Pocock is often adding new experimental skills, you can explore these as needed for future reference. There may also be additional questions for what you want to install. For this workflow, no need to install additional agents, so press `Enter` again.

5. The setup defaults to `Project` - which installs in the current directory, press `Enter` to confirm.

6. Press `Enter` to proceed with installation.

7. If successful, you should see a message like this:

   `Done! Review skills before use; they run with full agent permissions.`

### Command 2

```
npx skills@latest add valdesrosier/arcgis-skills
```

> **Windows note:** If the command above returns an error, try:
>
> `npx.cmd skills@latest add valdesrosier/arcgis-skills`

1. As with `Command 1`, press the spacebar on your keyboard to select all ArcGIS Skills. All the empty dots in the terminal will turn green indicating they have been selected. Press `Enter` to continue.

2. No need to install additional agents, so press `Enter` again.

3. As before, the setup defaults to `Project` - which installs in the current directory, press `Enter` to confirm.

4. Press `Enter` to proceed with installation.

5. If successful, you should see a message like this:

   `Done! Review skills before use; they run with full agent permissions.`

> [!NOTE]
> You only install and set up the skills once per project.

---

## Step 3 — Setup your skills and start the design interview

1. Open **Copilot Chat** using the chat box to the right of the search bar at the top of the Visual Studio window.

2. Ensure you are on "Agent" mode and select either **GPT 5.6 Sol** or **Opus 5** for the model.

3. When it's ready, start by typing a forward slash (`/`) to see the list of available skills. Select `/setup-matt-pocock-skills` from the list by arrowing up or down to highlight it and then press tab. You'll notice that the slash and text turns into a blue pill shape. This is normal for invoking a skill. You are able to type more context after the pill shape, but for now just hit `Enter` to run the skill.
   - You may be prompted at various times during the skill to allow access to your local files or to run `git` commands. Click **Allow** when prompted.

> [!NOTE]
> **What `/setup-matt-pocock-skills` does:** This is a one-time setup command for Matt's skills. It wires them into your project's workflow — it asks which **issue tracker** you use (GitHub, Linear, or local files), what **labels** you apply when triaging tickets, and where to **save the docs** the skills create (like `CONTEXT.md` and ADRs). It's what lets later skills publish tickets and save their paper trail in a consistent place. You run it once per project — we're running it here in the cloned repo, and exercises 2 and 3 reuse it.

4. During the setup skill, if asked on the following (you can reply in the chat with natural language):
   - **Issue tracker:** choose GitHub
   - **Labels:** choose to keep the defaults
   - **Domain Docs :** choose to create AGENTS.md

   - When done, you should see something similar to this in the chat panel:
     ![Setup Matt Pocock Skills Done](../docs/assets/mp-setup-skills-done.jpg)

---

## Step 4 — The prompt

1. Open a new chat in the GitHub Copilot panel by selecting the `+` button at the top of the window. Ensure your model is set to either **GPT 5.6 Sol** or **Opus 5**.

2. Start by typing a forward slash (`/`) to see the list of available skills. Select `/grill-with-docs` from the list by arrowing up or down to highlight it and then press tab, but do not press enter yet.

3. Paste the following prompt after the pill.

```
I want to build a set of "glass" cards in plain HTML and CSS that I can add to an ArcGIS Hub site. The look I'm going for is glassmorphism: frosted, semi-transparent panels with a soft blur, a thin light border, and a gentle shadow, sitting on top of a background image.

Before grilling me on design decisions, use the the arcgis-html-css skill and the arcgis-docs-lookup skill to look up anything you are not sure about for the overall design and approach.

Each card should have:
- a title
- a short description
- an icon or small image
- a button or link

I'd like a few cards laid out in a responsive row that stacks on
smaller screens. Keep the code simple and self-contained so I can paste it into a Hub embed, and make it easy to swap the colors, text, and background later.

Ask me about anything ambiguous — like how many cards, the color theme, and whether the cards should link out or open something — before we settle the design.

Write all code and files for this project only inside the `exercise-01-htmlcss/` folder in this repo. Create it if it doesn't exist. Don't add or modify files anywhere else in the repo.
```

4. Press `Enter` to run the skill.

## Step 5 — What happens next

1. Answer each question in the chat. You can answer however you like, as long it's clear to the model which question you are answering. You can also ask follow up questions to clarify anything you don't understand. The skill will write down the design as you go.
   - Example: "q1: agreed, q2: explain in less technical terms, q3-6: agreed, q7: yes but add ..."

> [!NOTE]
> Copilot may ask your approval to run commands during the course of a response. Be sure to review the **command summary** beneath the code preview to see what commands it wants to run. If you approve, click **Allow**. If you don't, click **Skip** and ask the model to clarify or change its approach. For this workflow - default to **Allow** as needed - this will happen often.

![Command approval from copilot](../docs/assets/copilot-chat-run-command-approval.jpg)

2. When the design is settled, copilot may begin implementing on its own. If not you can use the `/implement` skill to tell it to start building the cards and any other files needed for the project.

3. Preview it with **Live Preview** (steps below).

### Previewing your cards in VS Code

Use the **Live Preview** extension — it shows your page in a pane inside VS Code and refreshes as the file changes.

1. If you don't have it yet: open Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X` for Mac), search **Live Preview** (by Microsoft), and install it.

2. In the sidebar, click once on the `index.html` that was created to open it in the code editor.

3. Press `Ctrl+Shift+P` (or `Cmd+Shift+P` for Mac) and start typing `Live Preview` select either **Live Preview: Show Preview (Internal Browser)** or **Live Preview: Show Preview (External Browser)**.

   ![Live Preview options](../docs/assets/live-preview-options.jpg)

4. A browser pane opens either inside VS Code or in your default web browser at a `localhost` address and updates every time you save.

> [!NOTE]
> Other preview option: you can also double-click the HTML file in File Explorer to open it in your browser. That's fine for static cards, but Live Preview is the smoother option and avoids browser security blocks if your cards ever pull live data. 5. Work through any iterations / changes with the assistant.

> [!IMPORTANT]
> After copilot has finished responding, to view changes you will need to ensure you select the Keep button in your chat.

![Command approval from copilot](../docs/assets/copilot-edits-keep-undo-buttons.jpg)

## Step 6 — Enhance the Cards

Be creative, prompt the agent about cooler additions, for example:

- Cards that **flip or expand** on hover to reveal more,
- A **live stat** on each card pulled from a feature layer,
- Matching the card colors to your Hub site's theme automatically.

Feel free to also test with other models to see how they vary in output.

## Step 7 — OPTIONAL — Add it to an ArcGIS Hub site

- Paste it into an ArcGIS Hub site Text HTML/CSS.
