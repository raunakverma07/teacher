# Design System Architecture for AttendX

This document outlines the design system architecture for the AttendX application, focusing on a premium, luxury interface inspired by leading technology and design companies. The goal is to create a unified, visually stunning, and highly interactive user experience while preserving all existing functionality.

## 1. Color Tokens

The color palette is built around deep blacks, graphite surfaces, and vibrant accents to create a sophisticated and modern aesthetic. Aurora gradients will be used to add depth and visual interest.

| Token Name         | Value                                  | Description                                     |
| :----------------- | :------------------------------------- | :---------------------------------------------- |
| `--color-primary`  | `#5b9bd5` (Cyan-Blue)                  | Main accent color, used for interactive elements |
| `--color-secondary`| `#4ecdc4` (Teal)                       | Secondary accent, used in gradients and highlights |
| `--color-background`| `#07070f` (Deep Black)                 | Primary background color                        |
| `--color-card-bg`  | `rgba(255,255,255,0.035)`              | Background for glassmorphic cards               |
| `--color-border`   | `rgba(91,155,213,0.14)`                | Default border color for UI elements            |
| `--color-text`     | `#e8eaf0` (Off-White)                  | Primary text color                              |
| `--color-muted`    | `rgba(232,234,240,0.5)`                | Secondary text, hints, and less prominent info  |
| `--color-dim`      | `rgba(232,234,240,0.25)`               | Faded text, placeholders                        |
| `--color-success`  | `#56c47a` (Emerald Green)              | Success states, present status                  |
| `--color-warning`  | `#f0c040` (Amber)                      | Warning states, average attendance              |
| `--color-danger`   | `#e85555` (Red)                        | Danger states, critical attendance, errors      |
| `--gradient-main`  | `linear-gradient(135deg, var(--color-primary), var(--color-secondary))` | Main gradient for buttons and highlights        |

## 2. Typography Scale

Soft typography with a focus on readability and modern aesthetics. Syne will be used for headings and prominent elements, while DM Sans will be used for body text.

| Element          | Font Family        | Weight | Size (rem) | Line Height | Letter Spacing |
| :--------------- | :----------------- | :----- | :--------- | :---------- | :------------- |
| `h1`             | `Syne`, sans-serif | 800    | `clamp(2.5, 6.5vw, 4.4)` | 1.07        | 0.02em         |
| `h2`             | `Syne`, sans-serif | 800    | `clamp(1.8, 4vw, 2.5)` | 1.2         | 0.02em         |
| `h3`             | `Syne`, sans-serif | 700    | 0.98       | 1.3         | 0.02em         |
| `body`           | `DM Sans`, sans-serif | 400    | 0.9          | 1.7         | 0.05em         |
| `small`          | `DM Sans`, sans-serif | 600    | 0.73         | 1.5         | 0.08em         |
| `button`         | `Syne`, sans-serif | 700    | 0.92         | 1           | 0.02em         |

## 3. Spacing System

A consistent 8-pixel grid system will be used for all spacing, ensuring visual harmony and responsiveness.

| Token Name         | Value (px) | Description                                     |
| :----------------- | :--------- | :---------------------------------------------- |
| `--spacing-xs`     | 4          | Extra small spacing (e.g., between icons and text) |
| `--spacing-sm`     | 8          | Small spacing (e.g., between form elements)     |
| `--spacing-md`     | 16         | Medium spacing (e.g., card padding)             |
| `--spacing-lg`     | 24         | Large spacing (e.g., section margins)           |
| `--spacing-xl`     | 32         | Extra large spacing (e.g., major section breaks)|

## 4. Glassmorphism and Aurora Gradients

**Glassmorphism:** Achieved through `rgba` backgrounds, `backdrop-filter: blur()`, and subtle borders. This creates a frosted glass effect, allowing background elements to subtly show through.

**Aurora Gradients:** Dynamic, animated gradients using `--gradient-main` and other color combinations to create a sense of depth and luxury. These will be applied to backgrounds, text, and interactive elements.

## 5. Component Blueprints

### 5.1. Buttons

**Magnetic Buttons:** Interactive buttons that subtly attract the cursor, providing a tactile feel. Will incorporate `transform` and `box-shadow` animations on hover.

**Glowing Buttons:** Buttons with a subtle glow effect, especially for primary actions, using `box-shadow` and `animation`.

### 5.2. Cards

**Glass Cards:** Cards with glassmorphic backgrounds, refined borders, and premium shadows. Will include `3D tilt` effects on hover for dashboard elements.

### 5.3. Forms

**Animated Forms:** Input fields and form elements with subtle focus animations, glowing borders, and smooth transitions.

### 5.4. Navigation

**Premium Navigation:** Responsive navigation with smooth transitions, subtle hover effects, and clear active states. Will incorporate `clip-path` or `mask reveals` for cinematic transitions between sections.

### 5.5. Charts and Reports

**Animated Charts:** Data visualizations with smooth entry animations, progress rings, and interactive elements.

**Executive Reports:** Refined tables and data displays with elegant borders, spacing, and typography.

### 5.6. Loader

**Animated Loader:** A full-screen animated experience featuring a branded reveal, glowing particles, and a progress percentage, transitioning seamlessly into the main application.

### 5.7. Three.js Hero

**Interactive 3D Scene:** A fullscreen Three.js hero section featuring an education-themed floating 3D object (e.g., an attendance tablet, holographic classroom panel). This will include:

- **Volumetric Fog:** To create depth and atmosphere.
- **Procedural Particles:** Dynamically generated particles for a futuristic feel.
- **Ambient Stars:** Subtle background stars for a cosmic touch.
- **Animated Light Rays:** Dynamic light effects to highlight the 3D object.
- **Mouse-Reactive Physics:** The 3D object will respond to mouse movement with subtle physics and inertia.
- **Scroll-Driven Camera Choreography:** The camera in the Three.js scene will animate based on scroll position, revealing different aspects of the 3D object or scene.

## 6. Animations and Transitions

- **GSAP and ScrollTrigger:** Used for all major animations and scroll-driven effects.
- **Lenis:** For premium smooth scrolling.
- **Split-Text, Blur Reveals, Mask Reveals, Clip-Path Transitions:** For cinematic text and section reveals.
- **SVG Drawing:** For subtle line animations and decorative elements.
- **Perspective Motion:** For depth and dynamic movement of UI elements.
- **Liquid Reveals:** For unique and fluid transitions.
- **Spring Easing:** For natural and organic animation feel.
- **Staggered Choreography:** For sequential animations of multiple elements.

## 7. Technical Considerations

- **Single Production-Ready HTML File:** All code will be contained within a single HTML file, using CDN libraries only.
- **No Build Tools:** No Node.js, npm, Yarn, Vite, Webpack, Parcel, or `package.json`.
- **GPU-Friendly Transforms:** Prioritizing `transform` and `opacity` for animations to ensure smooth performance.
- **Accessibility:** Semantic HTML, ARIA attributes where necessary, and reduced-motion support.
- **Browser Compatibility:** Ensuring functionality across modern browsers.
- **Clean and Maintainable Code:** Well-structured and commented code following best practices.
