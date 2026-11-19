<table width="100%" border="0" style="border:none; border-collapse:collapse;">
  <tr>
    <td style="border:none;"><strong>C240 - Lesson 10</strong></td>
    <td style="border:none;" align="right"><img src="https://raw.githubusercontent.com/codeblazar/FileImageShare/main/Branding/RPnoTag.png" height="40"></td>
  </tr>
</table>

---

# :video_game: Activity 01 - Install, Connect, and Build Space Invaders (VS Code Copilot Chat)

**Name:** _(type your full name here)_
**Student ID:** _(type your student ID here)_

---

## :hourglass_flowing_sand: Duration

- 75 minutes
- All tables to be completed
- Complete and submit individually

---

## :clipboard: What You Will Do

- **Play the demo game first** at https://codeblazar.github.io/SpaceInvaders/ so you know what you are aiming for. It is a more complete game coded in VS Code by one of your lecturers using GitHub Copilot. It took a little longer, but it shows what can be done with time, patience and correct use of GitHub Copilot in VS Code.
- Install the **GitHub Copilot** and **GitHub Copilot Chat** extensions in VSCode
- Authenticate Copilot Chat to your free **GitHub Copilot Student** plan
- Use slash commands, `@` participants, and `#` file references to direct Copilot Chat
- Stay on **Auto** model selection and notice which model **Auto** picks on each turn
- Build a working browser-playable **Space Invaders** in three phases: Scaffold, Invaders, and Polish
- Reflect on your credit use (once called premium requests) and what your prompts cost you

---

## :rocket: The Brief (recap of the lecture)

Retro Arcade Co. opens at 8 pm tonight. The Space Invaders cabinet just broke. The owner needs a browser-playable version, single `index.html`, working by end of class. You will not type the game by hand. You will direct Copilot Chat to write it for you. Stay on **Auto**. Read every diff. Ship it.

---

## :arrows_counterclockwise: Reference: The Loop You Will Use

Every interaction with Copilot Chat follows the same simple pattern:

1. You write a prompt (and **attach the file** as context if one is involved - see Exercise 4).
2. Copilot Chat talks to a model. **Auto** picks which one.
3. The model responds:
   - **Interactive** proposes a **diff** (the exact lines it wants to add, change, or remove) and may run tools. Below the chat box you see the current mode, for example **Interactive**. Click it to open the **Agent mode** menu with **Interactive**, **Plan** and **Autopilot**.
   - **Plan** gives you an ordered plan of what to do first - no file changes until you click **Implement Plan**.
   - **Autopilot** works on its own, within your permissions.
4. Read the response. If it is a diff, review each change and **Keep** or **Undo** it before moving on.

When you get a diff, read it before accepting. The diff is your safety net.

---

## :wrench: Exercise 1 - Install Extensions (5 min)

You need two extensions today: **GitHub Copilot Chat** (to write the game) and **Live Server** (to run it in a browser with auto-reload).

1. In VSCode, open the **Extensions** view (`Ctrl+Shift+X`).
2. Search for **GitHub Copilot Chat** (publisher: GitHub) and click **Install**. Reload if prompted.
3. Search for **Live Server** (publisher: Ritwick Dey) and click **Install**. If a dialog appears, click **Trust Publisher and Install**.
4. Press `Ctrl+Alt+B` to open the **Secondary Side Bar** (right side). The Copilot Chat panel lives there.
5. Look at the bottom-right of the VS Code status bar. You should see a **Go Live** button - that is Live Server, ready to serve any HTML file.

> **Tip:** A strikethrough or warning on the Copilot status bar icon is normal until you sign in - that happens in Exercise 2.

> **Why Live Server?** Opening `index.html` directly with your browser (`file:///...`) works for simple cases but can break things like keyboard input focus and module loading. Live Server runs a tiny local web server (`http://127.0.0.1:5500`) and auto-reloads the browser every time you save - much smoother for the missions you are about to do.

| Step | Result |
|------|--------|
| GitHub Copilot Chat installed | |
| Live Server installed | |
| Copilot Chat appears in the Secondary Side Bar (`Ctrl+Alt+B`) | |
| **Go Live** button visible in the status bar | |

---

## :key: Exercise 2 - Authenticate to GitHub Copilot Student (5 min)

Copilot Chat connects to your free or GitHub Education plan through your GitHub sign-in inside VSCode. The first time you open chat, it will walk you through a one-time browser login.

1. Create a project folder for today's work using windows command prompt (cmd):

   ```
   mkdir C:\Users\<your user>\Documents\c240\projects\lesson10
   ```

2. Open the folder in VSCode: `File > Open Folder...` and select the folder you just created. This folder is now your **workspace** - that is what VS Code calls the folder it currently has open.

> **Workspace vs directory:** A **directory** (or folder) is a location on disk where files live. A **workspace** is the folder VS Code is currently treating as your project root. For this lesson the two are the same thing - opening the folder with `File > Open Folder...` is all you need. (VS Code also supports multi-folder workspaces saved as `.code-workspace` files, but you do not need that today.)

### Login

3. Open the **Secondary Side Bar** (`Ctrl+Alt+B`) - this is where the Copilot Chat panel lives.
4. If you are not signed in, click **Sign in to GitHub** in the chat panel.
5. A browser tab will open at `github.com/login/device` (or a direct sign-in page).
6. If asked, enter the device code shown in VSCode and click **Continue** (Green button).
7. Click **Authorize GitHub for VS Code** (Green button).
8. Return to VSCode. The Copilot icon in the status bar should no longer show a warning, and the chat panel should be ready to accept prompts.

> :no_entry: If you cannot get **GitHub Copilot** access through GitHub Education, notify your lecturer. There is no free model fallback inside Copilot Chat - you need an active Copilot subscription (the Student plan covers this).

### Select your model

Confirm **Auto** is your default model. At the **bottom of the Copilot Chat input box**, click the **model picker** dropdown.

> [!WARNING]
> **Auto** is being renamed **Copilot Fusion**. This is a new roll-out, so you may see either name. If you see **Copilot Fusion**, read **Auto** as **Copilot Fusion** in this worksheet.

Depending on GitHub rollouts you may be able to select **Auto**. If not, select a small model, such as one with **Haiku** or **Flash** in its name. Be aware that if you cannot select **Auto**, you may need to manually change models in subsequent worksheets. Managing the models is left to you. Do not always use the best model available. This worksheet was written using **Auto** but you can use better models if you wish. Ask your lecturer if unsure.

Below the chat box you should see **Copilot**, **Interactive** and **Manual permissions**. Leave them as they are. If the first one is not **Copilot**, click it and choose **Copilot**.

---

## :mag: Exercise 3 - Slash Command Scavenger Hunt (5 min)

Copilot Chat has two shorthand menus: **`/` slash commands** (quick actions) and **`@` chat participants** (specialists that know about a topic). VS Code shows the names but **does not** explain what each one does inline - so use the tables below as your cheat sheet.

### Try the menus

1. Click into the Copilot Chat input box and type **`/`**. Read the list. **Do not select or run any command.** Press Escape.
2. Now type **`@`**. Read the list. Press Escape.
3. Open the **Command Palette** with `Ctrl+Shift+P` and type **Chat:** to see chat-related VS Code actions (clear chat, switch mode, etc.). Press Escape.
4. Click **Interactive** below the chat box. The **Agent mode** menu opens with **Interactive**, **Plan** and **Autopilot**. Leave it on **Interactive**.

### Common slash commands

| Command | What it does |
|---------|--------------|
| `/clear` | Starts a new chat session (same as the **+** button) |
| `/explain` | Explains the selected code or referenced file |
| `/fix` | Suggests a fix for problems in the selected code |
| `/tests` | Generates unit tests for the selected code |
| `/new` | Scaffolds a new project or file from a description |

### Common chat participants

The exact list depends on which extensions you have installed. Below are the ones you are most likely to see today.

| Participant | What it does |
|-------------|--------------|
| `@vscode` | Answers questions about VS Code itself - settings, commands, shortcuts |
| `@terminal` *(if shown)* | Answers questions about the integrated terminal and shell commands |
| `@browser` *(if shown)* | Interacts with a browser (added by a browser-related extension) |
| `@github` *(if shown)* | Queries GitHub - repos, issues, PRs |

> **Note:** For today's missions you will mostly use plain prompts plus an **attached file** (covered in Exercise 4). You do not need any `/` or `@` to ship the game - they are useful, not required.

Which command or participant do you think you will use most often?

---

## :paperclip: Exercise 4 - File Context Warm-up (5 min)

To make sure Copilot Chat reads a file, **attach it as context**. Without an attached file, Copilot may still go looking for it, but that takes extra steps and it may pick the wrong file.

### How attaching works

Look just above the chat input box. You will see:

- A **`+` button** (Add Context) - click it to add files, folders, or other context manually.
- A **chip** for the file currently active in the editor (e.g., `<> hello.html`). Hovering shows *"Enable current file context"*. Click it once to attach the file - it then shows with an `×` you can click to detach.
- When you switch to a different file in the editor, the suggested chip updates to match the new active file. Files you have already attached (with the `×`) stay attached.

> **Heads up:** The **+** *inside* the chat input adds context to the current prompt. The **+** at the **top of the chat panel** starts a brand-new chat session. Two different buttons - keep them straight.

### Try it

1. In your `lesson10` folder, create a file called `hello.html` (use VS Code). Paste in this content and save:

   ```html
   <!DOCTYPE html>
   <html>
   <head><title>Hello</title></head>
   <body>
     <h1>Hello from C240</h1>
     <p>This is my first Copilot Chat test.</p>
   </body>
   </html>
   ```

2. Make sure the mode below the chat box is **Interactive**. Copilot will answer without changing files; if it proposes a change, click **Undo**. Then check `hello.html` is the active editor tab. In the chat input, click the `hello.html` chip so it becomes attached (shows the `×`). Send this prompt:

   ```
   What does this file do?
   ```

   ![CheckHello_html](https://raw.githubusercontent.com/codeblazar/FileImageShare/main/PET/C240/Lesson10/CheckHello_html.png)

3. Read the response.

| Item | Your Entry |
|------|------------|
| Did the response correctly describe `hello.html`? (yes/no) | |
| Response length (1 sentence / 1 paragraph / longer) | |

4. Now run the same idea **without** attaching the file. Click the **+** at the top of the chat panel to start a fresh chat session, then **detach** the suggested chip if it appears (click its `×`). Send:

   ```
   What does hello.html do?
   ```

| Item | Your Entry |
|------|------------|
| Did Copilot Chat read the file this time? (yes/no) | |
| Was the response accurate? (yes/no) | |

> **Tip:** Always attach the file you want Copilot to read. It is cheaper, faster, and more reliable than letting Copilot search for it.

---

## :rocket: Exercise 5 - Mission A: Scaffold the Player Ship (15 min)

**Mission:** Build the foundation of Space Invaders. A black canvas with a player ship that moves left and right with the arrow keys. Single file. No frameworks.

**Think First** (fill in before you write your prompt):

### Plan and Interactive mode

Below the chat box you see the current mode, for example **Interactive**. Click it to open the **Agent mode** menu: **Interactive**, **Plan** and **Autopilot**. For this mission you will use **Plan**, then **Implement Plan**.

**Plan mode**
- Used to think through the task **before doing anything**
- Breaks work into clear, ordered steps
- Helps you check scope, logic, and approach
- No file changes are made in this mode

**Interactive mode**
- Used to execute the plan
- Generates code, edits files, applies changes
- Produces actual outputs (a diff you can Keep or Undo)

**Switching modes**
- Use the **Agent mode** menu below the chat box to choose **Interactive**, **Plan** or **Autopilot**.

- Move to **Plan** when you need to map out the approach

- Move to **Interactive** when you are ready to act

:rotating_light:**Important**
- **You are responsible for choosing the correct mode from now on.**
- Do not stay in Interactive mode without a clear plan.
- Do not stay in Plan mode without progressing to execution.

### Reviewing the diff: Keep and Undo

When **Interactive** mode proposes changes, you will see review controls in **two** places:

- **In the editor file** (overlay on each changed region): **Keep** accepts *that one change*; **Undo** rejects *that one change*. Hover a change, or use the Up/Down arrows in the overlay, to step between changes.
- **In the chat panel** (next to the response): **Keep** accepts **all** pending changes across **all** files at once; **Undo** rejects them all.

The difference is **scope**:

- Use **Keep** on each change in the editor when you want to accept some parts of the diff and throw out others (cherry-pick).
- Use the **chat-panel Keep** when you have reviewed the whole diff and want to commit everything in one click.

> **Why two?** Because real reviews are mixed - some changes are good, some are wrong. The editor controls let you cherry-pick. The chat-panel control is the shortcut for "I have read this and it is all fine."

**Try It:**

1. Stay on **Auto**. Do not switch models. (Remember if you do not see **Auto**, select your own model)
2. Make sure your `lesson10` folder is the open VSCode workspace.
3. Switch to **Plan** mode. Write your prompt. Read the plan it proposes.
4. Click **Implement Plan** under the plan. If the button says **Implement with Autopilot**, click the arrow next to it and choose **Implement Plan**. Afterwards, check the mode below the chat box is back on **Interactive**.
5. With `index.html` open, click the **Go Live** button at the bottom-right of the status bar (or right-click `index.html` and choose **Open with Live Server**). A browser tab opens at `http://127.0.0.1:5500/index.html`. From now on, every time you save the file, the page auto-reloads.

**If you are stuck after 5 minutes**, peek at the hints below in order. Do not jump straight to Hint 3.

> **Hint 1 (gentle):** mention "single `index.html`" and a canvas size like 800 by 600. Black background.
>
> **Hint 2 (medium):** specify keyboard handling for `ArrowLeft` and `ArrowRight`, and an animation loop using `requestAnimationFrame`.
>
> **Hint 3 (explicit):** here is a sample prompt you may use as a starting point.
>
> Create a single `index.html` file with vanilla JavaScript. Use an HTML5 canvas at 800x600 with a black background. Draw a small player ship as a white rectangle near the bottom centre. Make the ship move left or right when the arrow keys are pressed. Use `requestAnimationFrame` for the animation loop. No frameworks. No external libraries.

**Checkpoint:**

| Item | Result |
|------|--------|
| Ship is visible on a black canvas | |
| Ship moves left with `ArrowLeft` | |
| Ship moves right with `ArrowRight` | |
| No errors in the browser console | |

**Reflect:**

| Question | Your Answer |
|----------|-------------|
| Did Copilot get the scaffold right on the first prompt, or did you need follow-ups? | |
| Looking at your prompt now, what is one thing you could remove without losing meaning? | |
| Did you **Keep** every change Copilot proposed, or **Undo** any? Why? | |

---

## :alien: Exercise 6 - Mission B: Invaders, Marching, Combat (18 min)

**Mission:** Build out the rest of Space Invaders. Add invaders that look like the original game, in colour. Make them march from side to side and drop one row at the edge. The player and the invaders both fire. Invaders are destroyed in a single hit. The player has three lives.

**Think First:**

A capable model in **Interactive** mode can one-shot this whole mission. We recommend splitting it into **three prompts** so you can review each diff before stacking the next change on top - if the marching breaks, you want to find out before combat is layered on.

Suggested three-prompt split:

| # | Prompt focus |
|---|--------------|
| 1 | Add the invaders (looks - based on the original game, in colour) |
| 2 | Marching movement (side-to-side, drop one row at the edge, reverse direction) |
| 3 | Combat (player and invaders fire at each other; invaders die in one hit; player has three lives) |

Why three and not one? If you one-shot it and the diff has a bug somewhere, you have to either accept a tangled mess or unpick it. Splitting lets you **Keep** what works and **Undo** what does not.

> **Note:** "Based on the original game" works here because Space Invaders is famous - any current model has seen it. The same trick will not work for an obscure game.

**Try It:**

1. Stay on **Auto**.
2. Click the **+** button at the top of the chat panel to start a fresh chat session.
3. On your first prompt, **attach `index.html`** (click its chip in the chat input) so Copilot Chat sees the existing code.
4. Use **Plan** mode first if you want to map the change out, then click **Implement Plan** to build it.
5. After each diff, review it (each change in the editor, or **Keep** in the chat panel) and test in the browser before moving on. Live Server auto-reloads when you save.

![AddInvaders](https://raw.githubusercontent.com/codeblazar/FileImageShare/main/PET/C240/Lesson10/AddInvaders.png)

:rotating_light: Note: In plan mode, you may be **prompted with additional questions to answer**. This **helps you create your vision** correctly. Answer according to your desires. 

![AdditionalQuestions](https://raw.githubusercontent.com/codeblazar/FileImageShare/main/PET/C240/Lesson10/AdditionalQuestions.png)

You can answer this question with "something else" as shown below ...

![SomethingElse](https://raw.githubusercontent.com/codeblazar/FileImageShare/main/PET/C240/Lesson10/SomethingElse.png)

Further, you may be asked for additional approvals. This is to ensure the agent doesn't overwrite or take any actions that you don't approve. Copilot may also ask to open your game in VS Code's built-in browser (**Open Browser Page?**) or to run test code there (**Run Playwright Code?**) so it can check its work. Read what it wants to do before you allow it.

![MoreApprovals](https://raw.githubusercontent.com/codeblazar/FileImageShare/main/PET/C240/Lesson10/MoreApprovals.png)

**If you are stuck after 5 minutes on a prompt**, use these hints in order.

> **Hint 1 (gentle):** keep each prompt focused on one of the three areas above. Do not ask for marching and shooting in the same prompt.
>
> **Hint 2 (medium):** for the marching behaviour, you can ask:
>
> Add invaders that look like the original Space Invaders, in colour. Arrange them in rows near the top. They move sideways at a constant speed. When any invader reaches the left or right edge, drop the whole formation down by one row and reverse direction.
>
> **Hint 3 (explicit):** if you want recommended exact prompts for all three steps, ask your lecturer.
>
> **Hint 4:** Switch to **Plan** mode and ask what is missing or different from the original game. Start a new chat session now and then to keep context tight. Try a different model if behaviour is unsatisfactory.

**Track each prompt:**

| Prompt | Done? (yes/no) | Did you split it further? |
|--------|----------------|---------------------------|
| 1 - Add invaders (look) | | |
| 2 - Marching + edge-drop | | |
| 3 - Combat + lives | | |

**Checkpoint:**

| Item | Result |
|------|--------|
| Invaders are visible and in colour | |
| Invaders march sideways and drop at the edges | |
| Player can fire bullets | |
| Bullets destroy invaders in one hit | |
| Invaders fire back at the player | |
| Player has three lives and loses one when hit | |

**Reflect:**

| Question | Your Answer |
|----------|-------------|
| Did you stick to three prompts, or did you split or combine them? | |
| Which prompt needed the most follow-up to get right? | |
| If you had to do this again, would you one-shot it or split? Why? | |

---

## :sparkles: Exercise 7 - Mission C: Polish, Your Choice (8 min)

**Mission:** Pick one polish feature. Get it working. Stop when it works.

**Choose one:**

- **Score display.** Count invaders destroyed. Draw the score at the top of the canvas.
- **Game-over screen with restart.** Trigger when invaders reach the bottom or the player is hit too many times. Press a key to restart.
- **Sound effects.** Use the Web Audio API. Shoot, explosion, game over.
- **Levels with increasing speed.** When all invaders are destroyed, restart the wave faster.

**Try It:**

1. Click the **+** button at the top of the chat panel to start a fresh chat session.
2. **Attach `index.html`** (click its chip in the chat input) to bring the file into context on your first prompt.
3. Write a clear, short prompt for your chosen feature.

| Item | Your Entry |
|------|------------|
| Feature you chose | |
| Did the feature work on the first try? (yes/no) | |
| If no, how many follow-up prompts before it worked? | |

> **Tip:** Polish is a good place to practise **overriding deliberately**. If a small model keeps producing buggy sound code, you may justify using the **model picker** to pick a stronger one for a single turn. Then return to **Auto**. Note the override in your reflection.

## :bug: Exercise 8 - Mission D: Continue to Refine (Remaining Time)

- You will need to correct the code. Use **Plan** mode and list what is wrong, for example: "Players shoot through the barriers with only one missile. It should take several missiles."
- Click **Implement Plan** to make the fixes, then re-test.

- Compare your game with the demo game at https://codeblazar.github.io/SpaceInvaders/. Notice things like the score, the mother ship, lives, sound effects, the shields, and how the invaders animate and march. Pick something that is missing or different, describe it to **Plan** mode, and keep improving your game.

---

## :thought_balloon: Reflection (4 min)

This is the most important block. Fill it in honestly. We grade engagement with the reflection, not whether your game shipped.

> [!WARNING]
> GitHub now counts usage in **credits**. It used to be called **premium requests**, and the name may change again. Look for whichever name your Copilot usage panel shows.

| Question | Your Answer |
|----------|-------------|
| Roughly how many credits did **Auto** use across the whole lesson? | |
| Which Mission (A, B, or C) used the most credits? Why do you think that is? | |
| In one sentence, what did you learn about prompt clarity and how **Auto** picks models? | |
| Did you ever override **Auto** with the model picker? If yes, why? If no, did you ever wish you had? | |
| What is one thing you would do differently next time? | |

---

## :inbox_tray: Submission

1. Take a screenshot of your final Space Invaders game running in the browser. Ensure you include your class and short name on the bottom right hand side. E.g., "**Name: E66C - Iza Tan**".
2. Save this worksheet with all tables filled in.
3. Post both the screenshot and this worksheet to the **Lesson 10 on Microsoft Teams** before the end of class.

---

*Save this file (`Ctrl+S`) and submit via Microsoft Teams when done.*

---

<p align="center">&copy; Republic Polytechnic, School of InfoComm</p>
