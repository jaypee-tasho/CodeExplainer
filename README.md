# CodeExplainer

A Claude Code skill for learning to code: a teacher's handbook for Claude. You type every line yourself. Claude guides you one small step at a time, checks your output and waits for your go-ahead. It explains each line word for word, with one fixed word per piece of code and no grammar added, like translating 我喜欢吃炒饭 to "Me like eat fried rice".

By default you get only:
- this step's goal: what it does for the whole project, in one line
- where the code goes, in one line
- the code with its translation beside every line
- what to run and what to expect, in one line

Everything else comes when you ask for it: the big picture, a dictionary of the pieces, the purpose of each line, words to know, plain-English explanations, or block notes.

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

To get more, add a mode (or just ask in plain words), and optionally which code:

| Type | Get |
|---|---|
| `/code-explainer` | the default: goal, where, code + translation, what to run |
| `/code-explainer full` | everything below at once |
| `/code-explainer big-picture` | a table of the task's steps, each with its goal for the whole project |
| `/code-explainer goal` | this step's goal, in one line |
| `/code-explainer blocks` | a note above each block of code: what it does and its role in the whole |
| `/code-explainer translate cell 5` | the word-for-word translation beside every line |
| `/code-explainer explain` | one plain-English sentence beside every line |
| `/code-explainer dictionary` | the dictionary table |
| `/code-explainer purpose` | why each line is there |
| `/code-explainer words` | words to know |
| `/code-explainer new-words` | the words not in `dictionary.md` yet |

Modes can be combined: `/code-explainer dictionary purpose`.
