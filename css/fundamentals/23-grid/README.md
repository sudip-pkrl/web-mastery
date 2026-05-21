# Grid Complete Notes

## What is Grid?

Grid (Grid Layout) is a CSS layout system used for:

- Two-dimensional layouts
- Rows and columns
- Responsive layouts
- Page structures
- Dashboards
- Galleries
- Complex UI layouts

---

# Basic Setup

```css
.container {
  display: grid;
}
```

- Parent becomes a **Grid Container**
- Children become **Grid Items**

---

# Columns vs Rows

Default Grid behavior:

```css
grid-template-columns: repeat(3, 1fr);
```

- Columns → Horizontal tracks
- Rows ↓ Vertical tracks

Grid controls BOTH directions together.

---

# Grid Container Properties

# 1. grid-template-columns

Controls column structure.

## Values

```css
200px 200px 200px;
1fr 1fr 1fr;
repeat(3, 1fr);
```

## Example

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

---

# 2. justify-items

Aligns items horizontally inside grid cells.

## Values

```css
start;
end;
center;
stretch;
```

## Example

```css
.container {
  display: grid;
  justify-items: center;
}
```

---

# 3. align-items

Aligns items vertically inside grid cells.

## Values

```css
start;
end;
center;
stretch;
baseline;
```

## Example

```css
.container {
  display: grid;
  align-items: center;
}
```

---

# Perfect Centering

```css
.container {
  display: grid;
  place-items: center;
}
```

Centers items horizontally and vertically.

---

# 4. gap

Controls spacing between rows and columns.

## Values

```css
10px;
20px;
2rem;
```

## Example

```css
.container {
  display: grid;
  gap: 20px;
}
```

---

# 5. grid-template-rows

Controls row sizes.

## Example

```css
.container {
  display: grid;
  grid-template-rows: 100px 200px;
}
```

---

# 6. align-content

Aligns the entire grid vertically.

Works only when:
- Extra vertical space exists
- Grid height is larger than content

## Values

```css
start;
center;
space-between;
space-around;
stretch;
```

---

# Grid Item Properties

# 1. grid-column

Controls horizontal spanning.

## Example

```css
.item {
  grid-column: span 2;
}
```

### Multiple Columns

```css
.item1 {
  grid-column: span 1;
}

.item2 {
  grid-column: span 2;
}
```

`item2` takes double column space.

---

# 2. grid-row

Controls vertical spanning.

## Example

```css
.item {
  grid-row: span 2;
}
```

Makes item taller.

---

# 3. minmax()

Sets responsive minimum and maximum size.

## Example

```css
.container {
  grid-template-columns:
    repeat(3, minmax(200px, 1fr));
}
```

---

# 4. repeat() (Shorthand)

## Syntax

```css
repeat(number, value);
```

## Example

```css
.container {
  grid-template-columns: repeat(3, 1fr);
}
```

## Common Shortcut

```css
grid-template-columns:
repeat(auto-fit, minmax(200px, 1fr));
```

Creates responsive layouts automatically.

---

# 5. justify-self

Overrides `justify-items` for one item.

## Example

```css
.item {
  justify-self: center;
}
```

---

# 6. grid-area

Assigns named layout areas.

## Example

```css
.item {
  grid-area: header;
}
```

Used with:

```css
grid-template-areas;
```

---

# Common Grid Layouts

# Responsive Gallery

```css
.gallery {
  display: grid;

  grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));

  gap: 20px;
}
```

---

# Card Layout

```css
.cards {
  display: grid;

  grid-template-columns:
    repeat(auto-fit, minmax(250px, 1fr));

  gap: 20px;
}
```

---

# Sidebar Layout

```css
.container {
  display: grid;

  grid-template-columns: 250px 1fr;
}

.sidebar {
  background: #eee;
}

.content {
  background: white;
}
```

---

# Important Grid Tricks

# Full Width Item

```css
.item {
  grid-column: 1 / -1;
}
```

Common for headers and footers.

---

# Equal Width Columns

```css
.container {
  grid-template-columns: repeat(3, 1fr);
}
```

---

# Prevent Overflow

```css
.item {
  min-width: 0;
}
```

Useful for long text overflow issues.

---

# Responsive Grid Columns

```css
.container {
  display: grid;

  grid-template-columns:
    repeat(4, 1fr);
}

@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

---

# Grid vs Flexbox

## Grid

- Two-dimensional
- Rows AND columns
- Great for page layouts

## Flexbox

- One-dimensional
- Row OR column
- Great for alignment/components

---

# Important Remember

```text
justify-items → HORIZONTAL ALIGNMENT
align-items   → VERTICAL ALIGNMENT
```

---

# Most Important Properties

```css
display: grid;
grid-template-columns;
grid-template-rows;
gap;
grid-column;
grid-row;
place-items;
```

---

# Simple Complete Example

```css
.container {
  display: grid;

  grid-template-columns:
    repeat(auto-fit, minmax(150px, 1fr));

  gap: 20px;

  height: 300px;

  border: 2px solid black;
}

.box {
  background: skyblue;

  padding: 20px;
}
```

---

# Grid Mental Model

1. Define columns
2. Define rows
3. Add spacing
4. Place items
5. Control spanning

---

# Quick Cheat Sheet

| Property                  | Purpose                     |
|---------------------------|-----------------------------|
| `display: grid`           | Enable Grid                 |
| `grid-template-columns`   | Define columns              |
| `grid-template-rows`      | Define rows                 |
| `justify-items`           | Align items horizontally    |
| `align-items`             | Align items vertically      |
| `gap`                     | Add spacing                 |
| `grid-column`             | Control column span         |
| `grid-row`                | Control row span            |
| `minmax()`                | Set responsive sizing       |
| `repeat()`                | Repeat grid values          |