# minigame 2
## Devlog

**1. Tell me about an issue you encountered while writing your code, and how you fixed it.**

The spell initially lasted only half a second even though `_life` was set to `1.0f` in Spell.cs. The scene still had the Life value saved as `0.5`. Unity uses an existing serialized Inspector value instead of replacing it with a new default from the script, so changing the field declaration alone did not change the running game. I changed the saved Life value to `1`, rebuilt the game, and checked it again. I also corrected the starter if statement to `if (_timeLeft <= 0.0f)`: the parentheses fix the syntax error, and the `f` suffix keeps the literal consistent with the float timer.

**2. Your best guess: what is going on in `_spriteRenderer.color = new Color(r, 0.2f, 0.2f);`? What is the period (.) for? What about the word `new`?**

My guess: `_spriteRenderer` is an object, and the period is how we reach inside that object to grab one of its pieces — so `.color` means "the color property that belongs to this SpriteRenderer." On the right side of the equals sign, `new` is telling C# to cook up a new Color value on the spot. `Color` is the recipe (the struct), and the numbers in the parentheses are the ingredients for this specific instance — a red value of `r`, a green of `0.2f`, and a blue of `0.2f`. So the whole line means: build a fresh red-ish color and assign it as the sprite renderer's color.

## Open-Source Assets
- Pixel art environment & character sprites: https://assetstore.unity.com/packages/2d/environments/pixel-art-top-down-basic-187605
