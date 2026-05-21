# Animations Notes

CSS animations let you move, transform, fade, rotate, scale, and create interactive visual effects without JavaScript.

You’ll mainly use:

- `@keyframes`
- `animation`
- timing functions
- transforms
- transitions

---

# 1. What is a CSS Animation?

A CSS animation changes styles over time.

Example:
- fade in
- bounce
- rotate
- slide
- pulse
- loading spinners

---

# 2. Basic Structure

```css
@keyframes animationName {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.box {
  animation: animationName 2s;
}
```

---

# 3. Your First Animation

## HTML

```html
<div class="box"></div>
```

## CSS

```css
.box {
  width: 100px;
  height: 100px;
  background: royalblue;

  animation: moveBox 2s;
}

@keyframes moveBox {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(300px);
  }
}
```

The box moves from left → right.

---

# 4. Understanding `@keyframes`

`@keyframes` defines animation steps.

## Using percentages

```css
@keyframes colorChange {
  0% {
    background: red;
  }

  50% {
    background: yellow;
  }

  100% {
    background: green;
  }
}
```

---

# 5. Animation Properties

## Full Syntax

```css
animation: name duration timing-function delay iteration-count direction fill-mode;
```

Example:

```css
animation: bounce 2s ease infinite alternate;
```

---

# 6. Important Animation Properties

## 1. animation-name

```css
animation-name: slide;
```

---

## 2. animation-duration

```css
animation-duration: 3s;
```

Controls speed.

---

## 3. animation-delay

```css
animation-delay: 1s;
```

Starts after delay.

---

## 4. animation-iteration-count

```css
animation-iteration-count: infinite;
```

OR

```css
animation-iteration-count: 3;
```

---

## 5. animation-direction

### normal

```css
animation-direction: normal;
```

### reverse

```css
animation-direction: reverse;
```

### alternate

```css
animation-direction: alternate;
```

### alternate-reverse

```css
animation-direction: alternate-reverse;
```

---

## 6. animation-timing-function

Controls speed curve.

### linear

```css
animation-timing-function: linear;
```

Constant speed.

### ease

```css
animation-timing-function: ease;
```

Default.

### ease-in

```css
animation-timing-function: ease-in;
```

Slow start.

### ease-out

```css
animation-timing-function: ease-out;
```

Slow end.

### ease-in-out

```css
animation-timing-function: ease-in-out;
```

Smooth start/end.

---

# 7. Transform Animations

Animations usually work with `transform`.

## Translate

```css
transform: translateX(100px);
```

## Rotate

```css
transform: rotate(45deg);
```

## Scale

```css
transform: scale(1.5);
```

## Skew

```css
transform: skew(20deg);
```

---

# 8. Multiple Transforms

```css
transform: translateX(100px) rotate(45deg) scale(1.2);
```

---

# 9. Fade In Animation

```css
.fade {
  animation: fadeIn 2s ease;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
```

---

# 10. Bounce Animation

```css
.ball {
  animation: bounce 1s infinite alternate;
}

@keyframes bounce {
  from {
    transform: translateY(0);
  }

  to {
    transform: translateY(-200px);
  }
}
```

---

# 11. Rotation Animation

```css
.loader {
  width: 80px;
  height: 80px;
  border: 8px solid #ddd;
  border-top: 8px solid blue;
  border-radius: 50%;

  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
```

---

# 12. Pulse Effect

```css
.pulse {
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.2);
  }

  100% {
    transform: scale(1);
  }
}
```

---

# 13. Shake Animation

```css
@keyframes shake {
  0% { transform: translateX(0); }
  25% { transform: translateX(-10px); }
  50% { transform: translateX(10px); }
  75% { transform: translateX(-10px); }
  100% { transform: translateX(0); }
}
```

---

# 14. Animation Fill Modes

Controls styles before/after animation.

## forwards

Keeps final state.

```css
animation-fill-mode: forwards;
```

## backwards

Applies starting styles before animation begins.

## both

Both forwards + backwards.

---

# 15. Pausing Animations

```css
animation-play-state: paused;
```

Resume:

```css
animation-play-state: running;
```

---

# 16. Hover Animations

```css
.button {
  transition: transform 0.3s;
}

.button:hover {
  transform: scale(1.1);
}
```

This uses `transition`, which is simpler than keyframes.

---

# 17. CSS Transitions vs Animations

## Transition

- simple state changes
- hover effects
- button effects

Example:

```css
transition: 0.3s;
```

---

## Animation

- complex multi-step motion
- loops
- loaders
- repeating effects

Example:

```css
@keyframes bounce
```

---

# 18. Combining Multiple Animations

```css
animation:
  slide 2s ease,
  rotate 2s linear;
```

---

# 19. Performance Tips

Use:
- `transform`
- `opacity`

Avoid animating:
- `width`
- `height`
- `top`
- `left`

Transforms are GPU accelerated and smoother.

---

# 20. Real Project Example

## Animated Button

```html
<button class="btn">Hover Me</button>
```

```css
.btn {
  padding: 15px 30px;
  border: none;
  background: royalblue;
  color: white;
  font-size: 18px;
  cursor: pointer;

  transition: all 0.3s ease;
}

.btn:hover {
  background: darkblue;
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}
```

---

# 21. Loading Dots Animation

```html
<div class="dots">
  <span></span>
  <span></span>
  <span></span>
</div>
```

```css
.dots span {
  display: inline-block;
  width: 15px;
  height: 15px;
  background: black;
  border-radius: 50%;

  animation: jump 0.6s infinite alternate;
}

.dots span:nth-child(2) {
  animation-delay: 0.2s;
}

.dots span:nth-child(3) {
  animation-delay: 0.4s;
}

@keyframes jump {
  to {
    transform: translateY(-20px);
  }
}
```

---

# 22. Text Typing Animation

```css
.typing {
  width: 0;
  overflow: hidden;
  white-space: nowrap;
  border-right: 3px solid black;

  animation:
    typing 4s steps(30) forwards,
    blink 0.7s infinite;
}

@keyframes typing {
  to {
    width: 100%;
  }
}

@keyframes blink {
  50% {
    border-color: transparent;
  }
}
```

---

# 23. Advanced Timing Functions

Custom easing:

```css
animation-timing-function: cubic-bezier(0.68, -0.55, 0.27, 1.55);
```

Useful for realistic motion.

---

# 24. Useful Modern Animation Properties

## will-change

```css
will-change: transform;
```

Hints browser optimization.

---

## transform-origin

```css
transform-origin: center;
```

Changes rotation/scaling origin.

---

# 25. Best Practices

✅ Keep animations smooth  
✅ Use subtle motion  
✅ Prefer transforms  
✅ Keep duration between `200ms–800ms` for UI  
✅ Use easing naturally  
✅ Avoid excessive motion  

---

# 26. Common Beginner Mistakes

❌ Forgetting `@keyframes` name  
❌ Missing units (`px`, `deg`)  
❌ Animating layout-heavy properties  
❌ Using too many infinite animations  
❌ Forgetting browser performance  

---

# 27. Mini Practice Projects

Build these to improve:

1. Loading spinner
2. Animated navbar
3. Floating cards
4. Image hover gallery
5. Typing text effect
6. Animated progress bar
7. CSS clock
8. Toast notification animation
9. Skeleton loading UI
10. Animated login form

---

# 28. Complete Example

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .box {
      width: 100px;
      height: 100px;
      background: tomato;

      animation:
        move 2s ease infinite alternate,
        rotate 2s linear infinite;
    }

    @keyframes move {
      from {
        transform: translateX(0);
      }

      to {
        transform: translateX(300px);
      }
    }

    @keyframes rotate {
      from {
        rotate: 0deg;
      }

      to {
        rotate: 360deg;
      }
    }
  </style>
</head>
<body>

<div class="box"></div>

</body>
</html>
```

---

# 29. Recommended Learning Path

Learn in this order:

1. `transition`
2. `transform`
3. `@keyframes`
4. timing functions
5. loaders
6. hover effects
7. advanced motion
8. animation libraries

---

# 30. Popular Animation Libraries

- Animate.css
- GSAP
- Framer Motion
- Motion One

---

# 31. Practice Challenge

Create:
- a bouncing ball
- rotating loader
- glowing button
- sliding sidebar
- animated card hover
- typing text effect

These cover most real-world animation concepts.

---

# Quick Cheat Sheet

```css
animation: name duration timing-function delay iteration-count direction fill-mode;
```

Example:

```css
animation: slide 2s ease 1s infinite alternate forwards;
```

---

# Final Advice

For modern UI:
- use transitions for interactions
- use animations for storytelling/motion
- keep movement subtle
- prioritize performance
- animate transforms + opacity whenever possible