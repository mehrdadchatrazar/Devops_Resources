# 📝 Vim Cheat Sheet

---

## 🔼 Basic Cursor Movement

| Key | Action |
|-----|--------|
| `h` | Move cursor **left** one character |
| `l` | Move cursor **right** one character |
| `j` | Move **down** one line |
| `k` | Move **up** one line |

---

## 🔢 Count Prefix (Number + Key)

You can prefix many motions or actions with a number `N` to repeat them `N` times.

| Example | Action |
|---------|--------|
| `5j` | Move down **5 lines** |
| `10l` | Move right **10 characters** |
| `3w` | Move forward **3 words** |

---

## 🔤 Word Navigation

| Key | Action |
|-----|--------|
| `w` | Move to the **beginning of the next word** |
| `e` | Move to the **end of the current/next word** |
| `b` | Move to the **beginning of the previous word** |

---

## 🆗 Line Navigation

| Key | Action |
|-----|--------|
| `0` | Move to the **beginning of the line** |
| `^` (Shift + 6) | Move to the **first non-whitespace character** of the line |
| `$` (Shift + 4) | Move to the **end of the line** |

---

## 🔢 Line Number Navigation

| Key | Action |
|-----|--------|
| `Ngg` | Go to **line number N**. Example: `20gg` goes to line 20 |
| `G` (Shift + g) | Go to the **end of the file** |

---

## ✏️ Inserting Text

| Key | Action |
|-----|--------|
| `i` | Enter insert mode **before the cursor** |
| `a` | Enter insert mode **after the cursor** |
| `I` (Shift + i) | Insert at the **start of the line** |
| `A` (Shift + a) | Append at the **end of the line** |
| `o` | Open a **new line below** and enter insert mode |
| `O` (Shift + o) | Open a **new line above** and enter insert mode |

---

## 🔁 Replacing & Changing Text

| Key | Action |
|-----|--------|
| `r<char>` | Replace the **character under the cursor** with `<char>` |
| `cc` | Change (delete) the **entire line** and enter insert mode |
| `cw` | Change from cursor to the **end of the current word**, then insert |
| `Ncw` | Change **N words**, then insert (e.g., `3cw` changes 3 words) |

---