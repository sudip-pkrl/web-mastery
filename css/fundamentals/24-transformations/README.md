# Transformations Notes

## What is CSS Transform?

CSS `transform` allows you to visually modify HTML elements without changing the normal document layout.

You can:
- Move elements
- Rotate elements
- Resize elements
- Skew elements
- Apply 3D effects

---

# Basic Syntax

```css
selector {
  transform: function(value);
}
```

Example:

```css
div {
  transform: rotate(45deg);
}
```

---

# Types of CSS Transformations

## 1. Translate (Move)

Moves an element from its original position.

### Syntax

```css
transform: translate(x, y);
```

### Example

```css
div {
  transform: translate(50px, 100px);
}
```

### Variations

```css
transform: translateX(50px);
transform: translateY(100px);
```

---

## 2. Scale (Resize)

Changes the size of an element.

### Syntax

```css
transform: scale(value);
```

### Example

```css
div {
  transform: scale(1.5);
}
```

### Variations

```css
transform: scaleX(2);
transform: scaleY(0.5);
```

---

## 3. Rotate

Rotates an element clockwise or counterclockwise.

### Syntax

```css
transform: rotate(angle);
```

### Example

```css
div {
  transform: rotate(45deg);
}
```

### Units

- `deg` → degrees
- `rad` → radians
- `turn` → turns

---

## 4. Skew

Tilts an element along X-axis or Y-axis.

### Syntax

```css
transform: skew(x-angle, y-angle);
```

### Example

```css
div {
  transform: skew(20deg, 10deg);
}
```

### Variations

```css
transform: skewX(20deg);
transform: skewY(10deg);
```

---

# Multiple Transformations

You can apply multiple transformations together.

### Example

```css
div {
  transform: translateX(50px) rotate(30deg) scale(1.2);
}
```

Transforms are applied from right to left.

---

# Transform Origin

Defines the pivot point of transformation.

### Syntax

```css
transform-origin: x-axis y-axis;
```

### Example

```css
div {
  transform-origin: top left;
}
```

### Common Values

- center
- top
- bottom
- left
- right

---

# 3D Transformations

Used for 3D effects.

### Example

```css
div {
  transform: rotateX(45deg);
}
```

```css
div {
  transform: rotateY(45deg);
}
```

```css
div {
  transform: rotateZ(45deg);
}
```

---

# Perspective

Adds depth to 3D transformed elements.

### Example

```css
.container {
  perspective: 500px;
}
```

---

# Transition with Transform

Used to animate transformations smoothly.

### Example

```css
div {
  transition: transform 0.3s ease;
}

div:hover {
  transform: scale(1.2);
}
```

---

# Important Points

- `transform` does not affect page layout flow.
- Multiple transforms can be combined.
- 3D transforms often require `perspective`.
- Use `transition` for smooth animations.

---

# Quick Cheat Sheet

| Function      | Description        |
|---------------|--------------------|
| `translate()` | Moves an element   |
| `scale()`     | Resizes an element |
| `rotate()`    | Rotates an element |
| `skew()`      | Tilts an element   |
| `matrix()`    | Combines transforms|

---

# Summary

CSS transformations are used to:
- Create animations
- Build hover effects
- Make interactive UI
- Add modern visual effects

Main transform functions:
- Translate
- Scale
- Rotate
- Skew
- 3D Transform