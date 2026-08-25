# Exercise 0 — VS Code and GitHub Copilot setup

[Back to the pre-work overview](../README.md)

> 💡 **Tip:** Press `Ctrl+Shift+V` to view this file as a formatted preview (or `Cmd+Shift+V` on macOS).

**What you'll practice:** finding your way around VS Code, using Copilot Chat, reviewing proposed actions and file changes, and working in the integrated terminal.

Complete this quick walkthrough before the first project-building exercise, then return to it whenever you need help finding a tool or reviewing Copilot's work.

## Quick links

- [Quick recovery reference](#quick-recovery-reference)
- [1. Find your way around VS Code](#1-find-your-way-around-vs-code)
- [2. Open and navigate files](#2-open-and-navigate-files)
- [3. Open Copilot Chat](#3-open-copilot-chat)
- [4. Use the integrated terminal](#4-use-the-integrated-terminal)

## Quick recovery reference

| When you need to...       | Do this                                                                       |
| ------------------------- | ----------------------------------------------------------------------------- |
| Find a project file       | Select **Explorer** in the Activity Bar.                                      |
| Find text everywhere      | Select **Search** in the Activity Bar.                                        |
| Open Chat                 | Select the **Chat** icon or **View > Chat**.                                  |
| Start over with Copilot   | Select **New Chat** (`+`).                                                    |
| Open the terminal         | Select **Terminal > New Terminal**.                                           |
| Approve a proposed action | Review the command and summary, then select **Allow** or **Skip**.            |
| Review Copilot edits      | Expand **Files changed**, inspect the diff, then select **Keep** or **Undo**. |
| Reopen a hidden area      | Use the **View** menu.                                                        |
| See errors                | Open **View > Problems**.                                                     |
| Preview a Markdown guide  | Press `Ctrl+Shift+V` or `Cmd+Shift+V`.                                        |

> [!NOTE]
> **Review actions before approving them**
>
> Agent mode may ask permission before it runs a terminal command. Read both the command and the plain-language summary.
>
> ![A Copilot command approval with Allow and Skip buttons](../docs/assets/copilot-chat-run-command-approval.jpg)
>
> - Select **Allow** when the command matches the task and you understand it.
> - Select **Skip** when it is unexpected or unclear, then ask Copilot to explain.
> - Never paste passwords, access tokens, private keys, or other secrets into Chat.
>
> You remain in control. Copilot can propose actions, but you decide what runs and which edits stay.

> [!NOTE]
> **Review file changes**
>
> When Copilot edits files, expand **Files changed** in Chat and select a file to inspect its diff:
>
> - Green lines were added.
> - Red lines were removed.
> - **Keep** accepts the proposed edits.
> - **Undo** removes the proposed edits.
>
> ![The Files changed section with Keep and Undo highlighted](../docs/assets/copilot-edits-keep-undo-buttons.jpg)
>
> Review the files before selecting **Keep**. After keeping them, test the result in the browser or with the command given in the exercise.

<!--
SCREENSHOT TODO: Reviewing a file diff
File: docs/assets/copilot-review-file-diff.png
Capture: Show a changed file in diff view with visible green additions and red removals. Include Files changed and the Keep and Undo controls.
Alt text: A Copilot file diff showing green additions, red removals, the Files changed list, and Keep and Undo controls.
-->

## 1. Find your way around VS Code

VS Code has five main areas:

| Number | Area             | What you use it for                                       |
| ------ | ---------------- | --------------------------------------------------------- |
| 1      | **Activity Bar** | Switch tools using the far-left strip of icons.           |
| 2      | **Side Bar**     | Browse files or use the selected tool.                    |
| 3      | **Editor**       | Read and edit files in the center area.                   |
| 4      | **Terminal**     | Use the terminal or view problems below the editor.       |
| 5      | **Chat**         | Interact with GitHub Copilot Chat for AI-assisted coding. |

![The VS Code workspace with the Activity Bar, Explorer, editor, Chat, terminal panel, and Status Bar labeled](../docs/assets/vscode-workspace-overview.png)

The selected Activity Bar icon is highlighted. This example shows **Extensions** selected and its Side Bar open:

![The Extensions icon highlighted in the VS Code Activity Bar and the Extensions Side Bar open](../docs/assets/vscode-extensions-panel.png)

### Try it

1. Select the **Explorer** icon at the top of the Activity Bar.
2. Select `README.md` to open it in the editor.
3. Select **View > Appearance > Panel** to show or hide the bottom panel.

> [!TIP]
> If a panel disappears, nothing was deleted. Reopen it from the **View** menu.

## 2. Open and navigate files

The Explorer shows the folders and files in your current project.

![The Explorer icon in the VS Code Activity Bar](../docs/assets/vscode-explorer-navigation.png)

- Select a folder arrow to expand or collapse it.
- Select a file once to preview it. Double-click it to keep its tab open.
- Unsaved files display a dot on their editor tab. Use `Ctrl+S` on Windows or `Cmd+S` on macOS to save.

Use **Search** in the Activity Bar to find text across the entire project. Use `Ctrl+F` on Windows or `Cmd+F` on macOS to search only the open file.

## 3. Open Copilot Chat

Select the **Chat** icon near the top of the VS Code window. You can also use **View > Chat**.

![The Chat icon in the VS Code title bar](../docs/assets/vscode-chat-icon.png)

At the start of each exercise:

1. Select **New Chat** (`+`) so the task starts with a clean conversation.
   ![Start a new chat in Copilot Chat](../docs/assets/copilot-chat-practice-prompt.png)
2. Select **Agent** mode when you want Copilot to inspect files, edit the project, or run commands.
   ![Copilot agent mode](../docs/assets/copilot-agent-mode.png)

3. Next to Agent, click the model picker and select either **GPT-5.6 Sol** or **Claude Opus 5** as the model.
   ![The model picker in the Copilot Chat panel](../docs/assets/copilot-models.png)

When Agent mode requests permission or proposes edits, follow the **Review actions before approving them** and **Review file changes** notes above.

### Write a useful prompt

Useful prompts include four things:

1. **Goal:** what you want to create or change.
2. **Context:** which file, page, error, or exercise matters.
3. **Constraints:** what it must preserve or avoid.
4. **Check:** how you will know the result works.

### Try it in Chat

Copy this prompt into Chat and send it:

```text
I am new to VS Code and this workshop. Inspect this project and give me a
brief orientation: explain what each top-level folder is for, identify the
three project-building exercises, and tell me which file I should open first.

Do not edit files or run terminal commands. End by asking which exercise I
plan to complete.
```

Example:
![The sample prompt in the Copilot Chat panel](../docs/assets/copilot-sample-prompt.png)

Copilot should summarize this repository without changing it.
Sample output (Yours may vary slightly):

![Sample output](../docs/assets/copilot-test-prompt-output.png)

When it asks which exercise you plan to complete, reply in normal language, then ask a follow-up such as:

```text
I plan to complete Exercise 1. What are the first two steps?
```

This follow-up stays in the same conversation, so Copilot can use the context it already gathered.

## 4. Use the integrated terminal

Open the terminal with **Terminal > New Terminal** or `` Ctrl+` `` on Windows and macOS. It opens in the bottom panel and lets you run project commands without leaving VS Code.

### Try it: check your project and tools

Run each command separately and read its output before continuing:

1. Confirm that the terminal is working in this workshop repository:

   ```shell
   git status
   ```

   The output identifies the current branch and reports whether any files have changed. It is fine if changes are listed.

2. Confirm that Node.js is available:

   ```shell
   node --version
   ```

3. Confirm that npm is available:

   ```shell
   npm --version
   ```

   > **Windows note:** If the command above returns an error, try:
   >
   > `npm.cmd --version`

The version commands should each print a version number. This workshop recommends Node.js `24.19.0` and npm `11.17.0`. If either command is not found, complete [Install Node.js](../docs/03-development-tools.md#install-nodejs) before starting the project-building exercises.

<!--
SCREENSHOT TODO: Integrated terminal
File: docs/assets/vscode-integrated-terminal.png
Capture: Show the terminal below the editor after running the three readiness-check commands. Highlight the Terminal tab, commands and output, and trash-can button.
Alt text: The integrated terminal below the editor showing Git status, Node.js version, and npm version output.
-->

If the `git status` output names a different repository or says the current directory is not a Git repository, reopen this workshop folder in VS Code before continuing.

If Copilot asks to run the command for you, use the **Review actions before approving them** note above before selecting **Allow**.

> [!NOTE]
> A terminal and Copilot Chat are different tools. The terminal runs commands on your computer; Chat is where you ask Copilot for help.

### Updating your repository from the original

Forked repositories won't automatically reflect changes from the original. To ensure you have the most up to date instructions for each of the exercises, open a new terminal in VS Code and run the following commands one by one:

1.  ```
    git remote add upstream https://github.com/valdesrosier/SE-Led-Training-AIAssistedCoding.git
    ```
2.  ```
    git fetch upstream
    ```
3.  ```
    git checkout main
    ```
4.  ```
    git merge upstream/main
    ```
5.  ```
    git push origin main
    ```
