---
name: code-explainer
description: Teach code to someone who has never coded. Translate every line word for word, with one fixed word per piece of code, in code order and with no grammar added (like translating Chinese to English without fixing the grammar). Add a dictionary of the pieces, the purpose of each line, and words to know. Use when giving someone code to type, when they ask what a line or block of code means, or when they say an explanation is too wordy.
---

# Code Explainer

Explain code to someone who has never coded. Every piece of code gets **one fixed word**, in the **same order as the code**, with **no grammar added**, the way 我喜欢吃炒饭 becomes "Me like eat fried rice".

The fixed words live in [dictionary.md](dictionary.md). Read it before explaining.

## Output, always in this order

1. **Goal:** 1–3 lines covering:
   - what we're doing
   - which file(s) or cell
   - what changes
   - what to expect after (e.g. "build fails until step 3")
2. **Dictionary:** a table with the columns `code | say | means`, one row for every piece in the block.
3. **Code:** the code, with a translation line under every code line.
4. **Why:** a table with the columns `line | why`, giving the purpose of each line.
5. **Words to know:** the ideas behind the code, one line each.
6. **Run and paste:** what output to expect. Then stop and wait.

If you made up a word that isn't in dictionary.md, add a last section, **New words**, listing them so the user can add them to the dictionary.

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
- **Write the translation as a comment** in the code's own language: `#` for Python, `//` for Kotlin, Java and JS. Put it on the line under the code line, with the same indent, so the user can type it into the file too.

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

## Teaching flow

- One small step at a time (one cell, or one small block), then stop for review.
- The user types the code. Don't write it into their files unless they ask.
- When they paste output or an error:
  - compare it with what you said to expect
  - say plainly what matches and what doesn't
  - go to the next step only when they say so.
- If they say it's too wordy, cut the prose and keep the tables and translation lines.

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
ds = ds.map(lambda x, y: (x, tf.cast(y == 0, tf.float32)))
# dataset is dataset's change-each (small-function photos, labels gives (photos, tensorflow's change-type (labels same-as 0?, tensorflow's decimal)))
```

| line | why |
|---|---|
| `change-each` | defect becomes 1, the other 3 become 0. The app only asks yes or no. |

**Words to know**
- **dataset:** photos and their labels, in groups.

Kotlin works the same way:

```kotlin
jarvis.pull(mark42)
// jarvis's pull (mark42)
```
