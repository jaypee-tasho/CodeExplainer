# CodeExplainer

A Claude Code skill for learning to code. It explains each line word for word, with one fixed word per piece of code and no grammar added, like translating 我喜欢吃炒饭 to "Me like eat fried rice".

Each explanation has:
- the goal
- a dictionary of the pieces
- the code with its translation under every line
- the purpose of each line
- words to know

## Files
- `SKILL.md`: the rules and the output format.
- `dictionary.md`: the fixed words. Add to it as new pieces come up.

## Install
Clone this repo into the Claude Code skills folder:

```
git clone https://github.com/jaypee-tasho/CodeExplainer.git ~/.claude/skills/code-explainer
```

You can also keep the repo where it is and link it in. Run this in Windows cmd:

```
mklink /J "%USERPROFILE%\.claude\skills\code-explainer" "%USERPROFILE%\Documents\Projects\CodeExplainer"
```

## Use
Type `/code-explainer`, or ask Claude to explain some code. It loads the skill by itself.
