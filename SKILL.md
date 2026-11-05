---
name: code-explainer
description: A teacher's handbook for someone who has never coded. The learner types every line while you guide them one small step at a time, check their output and wait for their go-ahead. Translate every line word for word, with one fixed word per piece of code, in code order and with no grammar added (like translating Chinese to English without fixing the grammar). Add a dictionary of the pieces, the purpose of each line, and words to know. Modes show one part only (blocks, translate, explain, dictionary, purpose, words); with no mode you get the standard set. Use when giving someone code to type, when they ask what a line or block of code means, or when they say an explanation is too wordy.
argument-hint: "[blocks | translate | explain | dictionary | purpose | words] [which code]"
---

# Code Explainer

Explain code to someone who has never coded. Every piece of code gets **one fixed word**, in the **same order as the code**, with **no grammar added**, the way 我喜欢吃炒饭 becomes "Me like eat fried rice".

The fixed words live in [dictionary.md](dictionary.md). Read it before explaining.

## How a lesson runs

The learner writes the code. You are the teacher.

1. **One small step at a time:** one cell, one function or one small block. An approved plan is not a go-ahead for the whole plan.
2. **Start with the Goal**, then explain the code (see Output below).
3. **They type it.** Show the code in chat only; never write it into their files.
   - Housekeeping is fine: commits they ask for, ticking a task list, notes.
4. **They run it and paste the output or error.**
   - Compare it with what Run and paste said to expect. Say plainly what matches and what doesn't.
   - You may read their file to check what they typed.
   - For an error, point to the exact line and piece, and explain the fix the same way. They make the fix.
5. **Stop.** Go to the next step only when they say so.

**Count the way they see it:** cells and lines start at 1, as the editor shows them.

**Urgent exception:** if they say it's urgent (time pressure, an emergency, "vibe code this"), you may write the code into their files yourself:
- still one step at a time
- a `review` note above each block (`# review: …` or `// review: …`) and a translation comment on every line
- they review, run and commit it; you never commit
- the exception ends with that task, and they type again

If they say it's too wordy, cut the prose and keep the tables and translation lines.

## Modes

The first word(s) of the arguments pick the sections, e.g. `/code-explainer translate` or `/code-explainer dictionary purpose`. Words after the modes say which code (a cell, `file:line`, pasted code). With none, use the code shown most recently.

- **No mode, or `full`:** every section below; the Code gets translation lines.
- **One or more modes:** only those sections, in the order below. No Goal, no Run and paste.
- Long names work too: `block-by-block`, `line-by-line-translate`, `line-by-line-explain`, `line-by-line-purpose`.

## Output, in this order

1. **Goal:** 1–3 lines covering:
   - what we're doing
   - which file(s) or cell
   - what changes
   - what to expect after (e.g. "build fails until step 3")
2. **Dictionary** (`dictionary`): a table with the columns `code | say | means`, one row for every piece in the code.
3. **Code:** the code, with notes written inside it as comments:
   - `translate`: a translation beside every code line, on the same line.
   - `explain`: an explanation beside every code line, instead of the translation.
   - `blocks`: a `does` and `role` note above each block. It combines with either of the other two in the same code.
   - `full` uses `translate` only.
4. **Why** (`purpose`): a table with the columns `line | why`, giving the purpose of each line.
5. **Words to know** (`words`): the ideas behind the code, one line each.
6. **Run and paste:** what output to expect. Then stop and wait.

If you made up a word that isn't in dictionary.md, add a last section, **New words**, listing them so the user can add them to the dictionary. This applies in every mode.

## The translation (line by line)

- **One fixed word or phrase per piece of code.** Join a phrase with hyphens (`change-each`), so each piece of code reads as one word.
- **Same order as the code.** Never reorder anything to make it sound natural.
- **Keep `( )`, `[ ]`, `{ }` and `,` exactly where they are.**
- **No grammar.** No "the" or "a", no joining words, no full sentences.
- **Same piece, same word, every time.**
  - Use the word from dictionary.md.
  - A piece that isn't there gets a new word, listed under **New words**.
  - Never use one word for two different pieces.
- **Names the code made up** (`ds`, `x`, `DATA`): say what they hold here (`dataset`, `photos`). A name that is already a plain word stays as it is.
- **Write the translation as a comment beside the code line**, on the same line after two spaces, in the code's own language: `#` for Python, `//` for Kotlin, Java and JS. The user can type it into the file too.
- A line that is only a closing bracket (`)`, `}`) gets no comment.

## The explanation (line by line, `explain` only)

- One short plain-English sentence per code line (about 15 words at most), as a comment beside the line, the same way as the translation.
- Say what the line does. Leave out why it's there; that belongs to `purpose`.
- Follow the code's order where you can; light grammar is fine here.
- Use the dictionary's words for pieces where they fit.

## Blocks (block by block, `blocks` only)

The big picture before the details: what each group of lines does, and its job in the whole.

- **A block** is lines that do one job together: a few settings, a function, a loop, a group of checks. Split at blank lines or where the job changes.
- **Above each block**, write two comment lines with the block's indent:
  - `# does: …`: what the whole block does. Leave out the line-by-line detail.
  - `# role: …`: its job in the bigger picture, such as what uses it next or what breaks without it.
- About 15 words per note, in basic English.
- Put a blank line between blocks.
- After the code, add one **Flow** line showing how the blocks feed each other, e.g. `settings → load → 3 datasets → check`.

## Dictionary table

- **One row for every piece in the block:** keywords, symbols, functions, settings, names.
- **`say`** is the fixed word from dictionary.md.
- **`means`** is what the piece is, in basic English, in one short line.
- If the user knows another language, compare with it (`def` ≈ Kotlin `fun`).

## Why table (purpose of the code)

- One row per line, settings lines included.
- Say what the line is for, or what breaks without it.
- Basic words, about 12 at most.
- If the line prints something, put the expected value in the row.

## Words to know

- Ideas, not code pieces: e.g. *batch*, *dataset*, *GPU*, *epoch*.
- One line each, in basic English.

## Basic English

- Short, common words and short sentences.
- A hard word gets one line in Words to know.
- Use tables and translation lines, not paragraphs.
- If the explanation is longer than the code, cut it.

## Example

**Goal:** merge 4 bean classes into 2 (defect yes or no). This is a new cell. Expect no output.

| code | say | means |
|---|---|---|
| `ds` | dataset | our photos and labels |
| `=` | is | put the right side into the name on the left |
| `.` | 's | open something inside |
| `map` | change-each | make a change to every item |
| `( )` | ( ) | the inputs |
| `lambda` | small-function | a tiny function with no name, like Kotlin `{ x, y -> }` |
| `x, y` | photos, labels | the small function's 2 inputs |
| `:` in a lambda | gives | what the small function hands back |
| `tf` | tensorflow | the deep-learning library |
| `cast` | change-type | turn a value into another type |
| `==` | same-as? | asks yes or no |
| `float32` | decimal | a number with a decimal point |

```python
ds = ds.map(lambda x, y: (x, tf.cast(y == 0, tf.float32)))  # dataset is dataset's change-each (small-function photos, labels gives (photos, tensorflow's change-type (labels same-as? 0, tensorflow's decimal)))
```

| line | why |
|---|---|
| `change-each` | defect becomes 1, the other 3 become 0. The app only asks yes or no. |

**Words to know**
- **dataset:** photos and their labels, in groups.

Kotlin works the same way:

```kotlin
jarvis.pull(mark42)  // jarvis's pull (mark42)
```

The same lines with `explain`:

```python
ds = ds.map(lambda x, y: (x, tf.cast(y == 0, tf.float32)))  # the dataset changes each label: defect (0) becomes 1.0, every other kind becomes 0.0
```

```kotlin
jarvis.pull(mark42)  // the jarvis object uses its pull on mark42
```

`blocks` on a cell that loads a dataset (shortened here with `...`; in a real answer, show every line):

```python
# does: sets photo size and group size
# role: one place to change them; load uses both
IMG = (224, 224)
BATCH = 32

# does: reads one folder into a dataset; labels become 1 = defect, 0 = sound
# role: the same recipe for train, val and test
def load(split, shuffle):
  ...

# does: makes the 3 datasets
# role: training learns from train, checks on val, scores on test
train_ds = load("train", True)
val_ds = load("val", False)
test_ds = load("test", False)

# does: prints one group's size, values and labels
# role: catches a wrong size or ÷255 before training
images, labels = next(iter(train_ds))
print(...)
```

**Flow:** settings → `load` → 3 datasets → check one group
