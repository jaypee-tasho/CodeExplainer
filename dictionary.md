# Dictionary

Fixed words for the translation. Each piece of code always gets the same word. Add new words at the bottom of the right section.

## Symbols (all languages)

| code | say |
|---|---|
| `=` | is |
| `==` | same-as? |
| `!=` | not-same-as? |
| `<` `>` | less-than? more-than? |
| `<=` `>=` | at-most? at-least? |
| `+` `-` `*` `/` | plus minus times divided-by |
| `+=` | add-to |
| `.` | 's |
| `( )` `[ ]` `{ }` `,` | keep as is |
| `" "` | text |
| `[i]` | item i |
| `#` `//` | note |

## Python

| code | say |
|---|---|
| `import` | bring |
| `from A import B` | from A bring B |
| `as` | name-it |
| `def` | make function |
| `:` at the end of a line | do: |
| `return` | give back |
| `lambda` | small-function |
| `:` in a lambda | gives |
| `for x in y:` | for each x in y do: |
| `if` / `elif` / `else` | if / else-if / else |
| `and` / `or` / `not` | and / or / not |
| `True` / `False` / `None` | yes / no / nothing |
| `print` | show |
| `len` | count |
| `sorted` | sort |
| `enumerate` | number-each |
| `range` | numbers |
| `f"{A}/{B}"` | text A / B |
| `[:n]` | [start to n] |
| `a, b = ...` | a, b is ... |
| `__version__` | version |
| `float( )` | decimal ( ) |
| `!` at the start of a Colab line | command |

### os, matplotlib, Colab

| code | say |
|---|---|
| `os.listdir` | os's list-files |
| `plt` | plot-tools |
| `plt.subplots` | plot-tools's make-boxes |
| `figsize` | picture-size |
| `plt.imread` | plot-tools's read-photo |
| `.imshow` | 's draw-photo |
| `.set_title` | 's set-title |
| `.axis("off")` | 's rulers ("off") |
| `plt.show` | plot-tools's display |
| `.shape` | 's size |
| `.dtype` | 's number-type |
| `.min()` / `.max()` | 's smallest () / 's biggest () |
| `drive.mount` | drive's connect |
| `unzip -q -o ... -d` | unzip quiet overwrite ... to |
| `ls` | list |

### TensorFlow / Keras

| code | say |
|---|---|
| `tf` | tensorflow |
| `tf.config.list_physical_devices` | tensorflow's settings's list-devices |
| `keras.utils` | keras's tools |
| `image_dataset_from_directory` | photo-dataset-from-folder |
| `class_names` | class-names |
| `image_size` | photo-size |
| `batch_size` | group-size |
| `shuffle` | mix |
| `seed` | mix-recipe |
| `.map` | 's change-each |
| `tf.cast` | tensorflow's change-type |
| `tf.float32` | tensorflow's decimal |
| `.prefetch` | 's prepare-early |
| `tf.data.AUTOTUNE` | tensorflow's data's auto-choose |
| `iter` | go-through |
| `next` | take-next |
| `tf.reduce_min` / `tf.reduce_max` | tensorflow's smallest-of-all / biggest-of-all |
| `.numpy()` | 's plain-numbers () |

## Kotlin / Compose

| code | say |
|---|---|
| `package` | folder-name |
| `import` | bring |
| `val` | fixed |
| `var` | changeable |
| `fun` | make function |
| `private` | only-here |
| `@Composable` | screen-piece |
| `: Type` | of-type Type |
| `->` in a lambda | gives |
| `->` in a `when` | then |
| `Unit` | nothing |
| `if` / `else` | if / else |
| `when` | choose |
| `return` | give back |
| `class` | make type |
| `data class` | data type |
| `enum class` | choice-list type |
| `object` | one-only |
| `it` | it |
| `?.` | if-not-empty 's |
| `?:` | or-else |
| `!!` | sure-not-empty |
| `by` | kept-by |
| `remember` | keep |
| `mutableStateOf` | changeable-state |
| `listOf` | list |
| `Modifier` | look-settings |
