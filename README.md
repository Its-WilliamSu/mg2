# minigame 2
## Devlog

**1. Tell me about an issue you encountered while writing your code, and how you fixed it.**

While fixing the if statement in Step 2 of Spell.cs, my first attempt actually failed to compile. I wrote `if _timeLeft <= 0.0` and got a syntax error, because a C# if statement needs the whole condition wrapped in parentheses, and `0.0` is a `double` while `_timeLeft` is a `float`. The error message pointed right at the broken line, which was useful — it told me exactly where the parser got confused. I fixed it by writing `if (_timeLeft <= 0.0f)`, adding both the parentheses and the `f` suffix so the types match.

**2. Your best guess: what is going on in `_spriteRenderer.color = new Color(r, 0.2f, 0.2f);`? What is the period (.) for? What about the word `new`?**

My guess: `_spriteRenderer` is an object, and the period is how we reach inside that object to grab one of its pieces — so `.color` means "the color variable that belongs to this SpriteRenderer." On the right side of the equals sign, `new` is telling C# to cook up a brand new Color object on the spot. `Color` is the recipe (the class), and the numbers in the parentheses are the ingredients for this specific instance — a red value of `r`, a green of `0.2f`, and a blue of `0.2f`. So the whole line means: build a fresh red-ish color and assign it as the sprite renderer's color.

## Open-Source Assets
- Pixel art environment & character sprites: https://assetstore.unity.com/packages/2d/environments/pixel-art-top-down-basic-187605
