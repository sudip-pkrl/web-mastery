# Flexbox Complete Notes

## What is Flexbox?

Flexbox (Flexible Box Layout) is a CSS layout system used for:

- Alignment
- Spacing
- Responsive layouts
- Centering elements
- Navigation bars
- Cards
- Sidebars

---

# Basic Setup

```css
.container {
  display: flex;
}
```

- Parent becomes a **Flex Container**
- Children become **Flex Items**

---

# Main Axis vs Cross Axis

Default:

```css
flex-direction: row;
```

- Main Axis → Horizontal
- Cross Axis ↓ Vertical

If:

```css
flex-direction: column;
```

- Main Axis ↓ Vertical
- Cross Axis → Horizontal

---

# Flex Container Properties

# 1. flex-direction

Controls item direction.

## Values

```css
row;
row-reverse;
column;
column-reverse;
```

## Example

```css
.container {
  display: flex;
  flex-direction: row;
}
```

---

# 2. justify-content

Aligns items on the **Main Axis**.

## Values

```css
flex-start;
flex-end;
center;
space-between;
space-around;
space-evenly;
```

## Example

```css
.container {
  display: flex;
  justify-content: center;
}
```

---

# 3. align-items

Aligns items on the **Cross Axis**.

## Values

```css
stretch;
flex-start;
flex-end;
center;
baseline;
```

## Example

```css
.container {
  display: flex;
  align-items: center;
}
```

---

# Perfect Centering

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Centers items horizontally and vertically.

---

# 4. flex-wrap

Controls wrapping.

## Values

```css
nowrap;
wrap;
wrap-reverse;
```

## Example

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

---

# 5. gap

Adds spacing between flex items.

## Example

```css
.container {
  display: flex;
  gap: 20px;
}
```

Better than margins for layouts.

---

# 6. align-content

Aligns multiple wrapped rows.

Works only when:
- `flex-wrap` exists
- Multiple rows exist

## Values

```css
flex-start;
center;
space-between;
space-around;
stretch;
```

---

# Flex Item Properties

# 1. flex-grow

Controls growth.

## Example

```css
.item {
  flex-grow: 1;
}
```

### Multiple Items

```css
.item1 {
  flex-grow: 1;
}

.item2 {
  flex-grow: 2;
}
```

`item2` gets double extra space.

---

# 2. flex-shrink

Controls shrinking.

## Example

```css
.item {
  flex-shrink: 0;
}
```

Prevents shrinking.

---

# 3. flex-basis

Initial size before extra space distribution.

## Example

```css
.item {
  flex-basis: 200px;
}
```

---

# 4. flex (Shorthand)

## Syntax

```css
flex: grow shrink basis;
```

## Example

```css
.item {
  flex: 1 1 200px;
}
```

## Common Shortcut

```css
.item {
  flex: 1;
}
```

Equivalent to:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 0;
```

---

# 5. align-self

Overrides `align-items` for one item.

## Example

```css
.item {
  align-self: center;
}
```

---

# 6. order

Changes visual order.

## Example

```css
.item {
  order: 2;
}
```

Default:

```css
order: 0;
```

Lower order appears first.

---

# Common Flexbox Layouts

# Responsive Navbar

```css
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

# Card Layout

```css
.cards {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}
```

---

# Sidebar Layout

```css
.container {
  display: flex;
}

.sidebar {
  width: 250px;
}

.content {
  flex: 1;
}
```

---

# Important Flexbox Tricks

# Push Item to Right

```css
.item {
  margin-left: auto;
}
```

Common in navbars.

---

# Equal Width Columns

```css
.child {
  flex: 1;
}
```

---

# Prevent Overflow

```css
.child {
  min-width: 0;
}
```

Useful for text overflow issues.

---

# Responsive Flex Direction

```css
.container {
  display: flex;
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

---

# Flexbox vs Grid

## Flexbox

- One-dimensional
- Row OR column
- Great for alignment/components

## Grid

- Two-dimensional
- Rows AND columns
- Great for page layouts

---

# Important Remember

```text
justify-content → MAIN AXIS
align-items     → CROSS AXIS
```

---

# Most Important Properties

```css
display: flex;
flex-direction;
justify-content;
align-items;
gap;
flex-wrap;
flex;
```

---

# Simple Complete Example

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
  height: 300px;
  border: 2px solid black;
}

.box {
  flex: 1;
  min-width: 150px;
  background: skyblue;
  padding: 20px;
}
```

---

# Flexbox Mental Model

1. Define direction
2. Align on main axis
3. Align on cross axis
4. Control growth/shrinking

---

# Quick Cheat Sheet

| Property            | Purpose                |
|---------------------|------------------------|
| `display: flex`     | Enable Flexbox         |
| `flex-direction`    | Set direction          |
| `justify-content`   | Main-axis alignment    |
| `align-items`       | Cross-axis alignment   |
| `flex-wrap`         | Control wrapping       |
| `gap`               | Add spacing            |
| `flex-grow`         | Control growth         |
| `flex-shrink`       | Control shrinking      |
| `flex-basis`        | Set base size          |
| `flex`              | Flex shorthand         |