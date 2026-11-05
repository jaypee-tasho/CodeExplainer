# CodeExplainer

A Claude Code skill for learning to code: a teacher's handbook for Claude. You type every line yourself. Claude guides you one small step at a time, checks your output and waits for your go-ahead. It explains each line word for word, with one fixed word per piece of code and no grammar added, like translating 我喜欢吃炒饭 to "Me like eat fried rice".

Each explanation has:
- the goal
- a dictionary of the pieces
- the code with its translation beside every line
- the purpose of each line
- words to know

## Files
- `SKILL.md`: how a lesson runs, the modes, the rules and the output format.
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

To get one part only, add a mode, and optionally which code:

| Type | Get |
|---|---|
| `/code-explainer` | the standard set |
| `/code-explainer blocks` | a note above each block of code: what it does and its role in the whole |
| `/code-explainer translate cell 5` | the word-for-word translation beside every line |
| `/code-explainer explain` | one plain-English sentence beside every line |
| `/code-explainer dictionary` | the dictionary table |
| `/code-explainer purpose` | why each line is there |
| `/code-explainer words` | words to know |

Modes can be combined: `/code-explainer dictionary purpose`.
