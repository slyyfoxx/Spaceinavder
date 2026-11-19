## Game Improvement Hints

Use these hints when your game still looks or behaves differently from the [Space Invaders Demo](https://codeblazar.github.io/SpaceInvaders/), a more complete game coded in VS Code by one of your lecturers using GitHub Copilot.

### Before you use a hint

- Start a fresh Copilot chat with **+**
- Attach `index.html`
- Use **Plan** mode first, then click **Implement Plan**
- Test after every change

You can also ask Copilot to improve accuracy during planning. For example:

- “Make the invaders behave more like the original arcade game.”
- “Match the movement and timing of the classic Space Invaders.”
- “Make the sprites and gameplay closer to the arcade version.”

Write your own prompt first. Use the checklist as guidance. Only use the *Last resort* prompt if your own attempt fails twice.

------

### Hint 1: Sprites

Your prompt should mention:

- Original Space Invaders style sprites
- Three different invader types
- Two animation frames each
- A proper player cannon sprite
- Pixelated rendering

*Last resort:*
 “Reference the original Space Invaders sprites online. Create three invader designs: squid, crab, and octopus, each with two animation frames. Replace the white player rectangle with a green cannon sprite. Add `image-rendering: pixelated` to the canvas CSS.”

------

### Hint 2: Stepped movement and speed-up

Your prompt should mention:

- Stepped movement, not smooth scrolling
- Formation drops and reverses at edges
- Faster movement as invaders are destroyed
- Animation frame swap on each step

*Last resort:*
 “Change invader movement to stepped motion with one move about every 500ms. When the formation reaches an edge, drop it down and reverse direction. Speed up movement as invaders are destroyed. Swap animation frames on each step.”

------

### Hint 3: Collisions and Game Over

Your prompt should mention:

- Smaller hitboxes
- Both bullet directions
- Losing lives
- Game over conditions
- Overlay and final score
- Play Again button
- Resetting all game state

*Last resort:*
 “Shrink hitboxes to about 80% of sprite size. Player bullets should destroy invaders and award points. Invader bullets should remove a life and briefly flash the player. Trigger game over when lives reach zero or invaders reach the player row. Show a dark overlay, GAME OVER text, final score, and a Play Again button with hover effects. Reset score, lives, invaders, and bullets when restarting.”

------

### Hint 4: Destructible bunkers

Your prompt should mention:

- Four bunkers
- Pixel-art style
- Arched bunker shape
- Damage by small chunks, not full removal
- Damage from both bullet types

*Last resort:*
 “Add four destructible pixel-art bunkers between the player and invaders. Use an arched shield shape with a notch underneath. Damage should remove a small area around impact points. Both player and invader bullets should damage the bunkers.”

------

### Hint 5: HUD polish

Your prompt should mention:

- Pixel-style score display
- Lives shown as cannon icons
- Ground line
- Correct point values

*Last resort:*
 “Show the score in a pixel-style font at the top-left. Display remaining lives as small green cannon sprites at the bottom-left. Add a green ground line above the player. Use point values of 30 for squid, 20 for crab, and 10 for octopus.”

------

If **Auto** (or **Copilot Fusion**) gives weak results, switch the model manually for one prompt, then switch back. Mention this in your Reflection.
