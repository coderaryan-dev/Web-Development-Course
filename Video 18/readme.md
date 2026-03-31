# 🎯 CSS Specificity & Cascade

### By Aryan Singh

---

## 📌 Overview

CSS Specificity determines **which CSS rule is applied** when multiple rules target the same element.
It works together with the **Cascade system** to resolve conflicts between styles.

Understanding specificity is essential for writing **predictable, clean, and maintainable CSS**.

---

## 🧠 What is CSS Specificity?

Specificity is a **priority system** used by browsers to decide which CSS rule wins.

When multiple selectors apply to the same element, the browser calculates a **specificity value** based on the selector type.

---

## ⚖️ Specificity Hierarchy (Low → High)

| Selector Type    | Example         | Priority   |
| ---------------- | --------------- | ---------- |
| Element Selector | `p`, `h1`       | 🔹 Low     |
| Class Selector   | `.text`, `.box` | 🔸 Medium  |
| ID Selector      | `#header`       | 🔥 High    |
| Inline Style     | `style=""`      | 🚀 Highest |

---

## 🔢 Specificity Calculation (Points System)

Each selector gets a score:

```css
Inline styles  = 1000
ID selectors   = 100
Class selectors= 10
Element        = 1
```

### ✅ Example:

```css
p            /* 1 */
.text        /* 10 */
#id          /* 100 */
```

```html
<p id="id" class="text">Hello</p>
```

👉 Final specificity:

* `#id` (100) > `.text` (10) > `p` (1)
  ✔️ **ID selector wins**

---

## 🔥 Example Breakdown

```css
p {
  color: blue;
}

.text {
  color: green;
}

#unique {
  color: orange;
}
```

```html
<p id="unique" class="text">Hello World</p>
```

### 🧾 Result:

👉 **Orange text** (ID wins over class and element)

---

## ⚖️ What is CSS Cascade?

The Cascade decides **which rule applies when specificity is equal**.

### Rule:

👉 **Last declared CSS rule wins**

```css
.same {
  color: purple;
}

.same {
  color: red;
}
```

✔️ Output: **Red**

---

## 💣 The `!important` Rule

```css
p {
  color: red !important;
}
```

* Overrides **all other rules**
* Even beats inline styles
* ❌ Not recommended for regular use

---

## ⚠️ Important Notes

* Specificity only matters when multiple rules target the same element
* Inline styles override almost everything
* `!important` should be avoided unless absolutely necessary
* Cleaner CSS = better maintainability

---

## 💡 Best Practices

* ✅ Use classes instead of IDs for styling
* ✅ Avoid overusing `!important`
* ✅ Keep selectors simple and readable
* ✅ Follow a consistent CSS structure

---

## 🚀 Conclusion

CSS Specificity and Cascade are the backbone of styling behavior in web development.
Mastering them helps you avoid unexpected styling issues and write better CSS.

---

## 🏷️ Tags

```
css
css-specificity
css-cascade
frontend
web-development
```

---
