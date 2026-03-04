plain.css
=========
**A minimalist, utilitarian CSS framework** — no bloat, no opinions, just the essentials.

* * *

plain.css is not trying to win design awards. It's just trying to be useful — a solid foundation that gets out of your way.

**Design tokens** that scale • **Utilities** that work • **Components** that compose • **Dark mode** that just happens

* * *

Why plain.css?
--------------
* **No build step** — drop in one file, start building
* **Design token driven** — change `--space-unit`, rescale everything
* **Dark mode baked in** — respects `prefers-color-scheme`, zero config
* **Unopinionated** — use as much or as little as you want
* **Lightweight** — ~18kb gzipped (1/10th of Bootstrap)
* **Accessible** — proper focus states, semantic HTML patterns

Quick Start
-----------
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="plain.css">
    <title>My plain site</title>
</head>
<body>
    <div class="container">
        <button class="btn btn-primary">Hello, world!</button>
    </div>
</body>
</html>
```

## Philosophy

plain.css occupies the sweet spot between:

|Approach | Example | Where plain.css fits|
|---|---|---|
|**Utility-only** | Tailwind | Has utilities, but also components |
|**Component-only** | Bootstrap | Has components, but also utilities |
|**Minimal reset** | Pure CSS | Has tokens, but also batteries |
|**plain.css** | Hybrid | **Just right** | 


### 🎨 Design Tokens
Everything scales from a single unit: `--space-unit: .5rem (8px)`
```css
:root {
    /* Spacing scale — change one, everything updates */
    --space-xxs: 2px;  --space-xs: 4px;  --space-sm: 8px;
    --space-md: 16px;  --space-lg: 24px;  --space-xl: 32px;
    --space-2xl: 48px;  --space-3xl: 64px;
    /* Type scale */
    --text-xxs: 10px; --text-xs: 12px; --text-sm: 14px;
    --text-base: 16px; --text-md: 18px; --text-lg: 20px;
    --text-xl: 24px; --text-2xl: 30px; --text-3xl: 36px;
    /* Full color palettes (50–950) */
    --gray-50: #fafafa;  ...  --gray-950: #0a0a0a;
    --blue-50: #eff6ff;  ...  --blue-950: #172554;
    --green-50: #f0fdf4; ...  --green-950: #052e16;
    --yellow-50: #fefce8; ... --yellow-950: #422006;
    --red-50: #fef2f2;  ...  --red-950: #450a0a;
    --orange-50: #fff7ed; ... --orange-950: #431407;
    --purple-50: #f5f3ff; ... --purple-950: #2e1065;
}
```

**Semantic aliases** — all automatically invert in dark mode:
```css
--color-primary: var(--blue-600);       /* primary actions */
--color-secondary: var(--gray-600);     /* neutral gray */
--color-success: var(--green-500);      /* success states */
--color-warning: var(--yellow-500);     /* warning states */
--color-error: var(--red-500);          /* error states */
--color-info: var(--blue-500);          /* info states */
```

### 📐 Layout Utilities
#### Grid System
```css
.grid                   /* display: grid; gap: 16px */
.grid-2 ... grid-6      /* equal columns */
.grid-auto-sm           /* auto-fill, min 160px */
.grid-auto-md           /* auto-fill, min 240px */
.grid-auto-lg           /* auto-fill, min 320px */
.col-span-2             /* span 2 columns */
.col-span-full          /* span all columns */
.gap-xxs ... gap-xl     /* gap control */
.gap-x-sm ... gap-x-lg  /* column gap */
.gap-y-sm ... gap-y-lg  /* row gap */
```

#### Flexbox (comprehensive)
```css
.flex                   /* display: flex */
.flex-0                 /* flex: 0 0 auto (fixed) */
.flex-1                 /* flex: 1 1 0% (fills) */
.flex-01                /* flex: 0 1 auto (shrink only) */
.flex-10                /* flex: 1 0 auto (grow only) */
.flex-grow-2            /* proportional growth */
.flex-shrink-3          /* proportional shrink */
.flex-grow-only         /* alias for flex-10 */
.flex-shrink-only       /* alias for flex-01 */
/* All alignment utilities */
.justify-[start/center/end/between/evenly]
.items-[start/center/end/stretch/baseline]
.self-[start/center/end/stretch/auto]
.content-[start/center/end/between/evenly/stretch]
```

#### Layout Helpers
```css
.stack > * + *        /* vertical rhythm (16px) */
.stack-xs ... stack-xl  /* size variants */
.cluster                /* wrapping horizontal group */
.layout-sidebar         /* 240px + 1fr grid layout */
.container              /* 1200px max, centered */
.container-sm ... container-xl  /* width variants */
```

### 🎯 Spacing Utilities
Full coverage of margin and padding with intuitive naming:
```css
/* Margin — all sides */
.m-0, .m-xxs, .m-xs, .m-sm, .m-md, .m-lg, .m-xl, .m-auto
/* Single sides */
.mt-*, .mb-*, .ml-*, .mr-*
/* Axes */
.mx-*, .my-*
/* Padding (same pattern) */
.p-*, .pt-*, .pb-*, .pl-*, .pr-*, .px-*, .py-*
```

### 🔤 Typography
```css
/* Type sizes */
.text-xxs ... text-3xl
/* Weights */
.font-normal, .font-medium, .font-semibold, .font-bold
/* Colors */
.text-default, .text-secondary, .text-muted, .text-disabled
.text-primary, .text-info, .text-success, .text-warning, .text-error
/* Line heights */
.lh-tight, .lh-snug, .lh-base, .lh-relaxed
/* Tracking */
.tracking-tight, .tracking-normal, .tracking-wide, .tracking-wider
/* Modern utilities */
.text-balance       /* balanced line wrapping for headlines */
.text-truncate      /* ellipsis overflow */
.break-words        /* safe word breaking */
```

🧩 Components
-------------
### Buttons
```html
<button class="btn">Default</button>
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-subtle">Subtle</button>
<button class="btn btn-ghost">Ghost</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-xs">XS</button>
<button class="btn btn-sm">SM</button>
<button class="btn btn-md">MD (default)</button>
<button class="btn btn-lg">LG</button>
<button class="btn btn-xl">XL</button>
<div class="btn-group">
    <button class="btn">Left</button>
    <button class="btn">Center</button>
    <button class="btn">Right</button>
</div>
```

### Forms
```html
<div class="form-group">
    <label class="required">Email</label>
    <input type="email" placeholder="Enter email">
    <span class="form-hint">We'll never share your email</span>
</div>
<div class="form-group">
<label>Password</label>
<input type="password" class="is-error">
<span class="form-error">Password too short</span>
</div>
<div class="select-wrapper">
</select>
    <option>Option oneoption</option>
    <option>Option twooption</option>
</select>
</div>
<div class="input-wrapper has-addon flex">
    <span class="input-addon">https://</span>
    <input type="text" placeholder="yoursite.com">
</div>
<label class="checkbox-group">
    <input type="checkbox" checked> Accept terms
</label>
<input type="color"> <input type="date"> <input type="range">
<input type="file"> <input type="number"> <input type="search">
```

### Cards
```html
<div class="card">
    <div class="card-header">Header</div>
    <div class="card-title">Card Title</div>
    <div class="card-description">Optional description</div>
    <p>Body content goes here.</p>
    <div class="card-footer">Footer</div>
</div>
<div class="card card-sm">Compact</div>
<div class="card card-lg">Spacious</div>
<div class="card card-hoverable">Lifts on hover</div>
```

### Navigation
```html
<nav>
    <a href="#" class="active">Dashboarda>
    <a href="#">Projectsa>
    <a href="#">Teama>
</nav>
<div class="tabs">
    <button class="tab active">Overview</button>
    <button class="tab">Analytics</button>
</div>
<div class="nav-pills">
    <a href="#" class="tab active">Alla>
    <a href="#" class="tab">Activea>
</div>
<nav class="breadcrumb">
    <a href="#">Homea>
    <span class="breadcrumb-sep"></span>
    <span class="breadcrumb-current">Settings</span>
</nav>
```

### Badges & Tags
```html
<span class="badge">Default</span>
<span class="badge badge-primary">Primary</span>
<span class="badge badge-secondary">Secondary</span>
<span class="badge badge-info">Info</span>
<span class="badge badge-success">Success</span>
<span class="badge badge-warning">Warning</span>
<span class="badge badge-error">Error</span>
<span class="badge badge-orange">Orange</span>
<span class="badge badge-purple">Purple</span>
<span class="badge badge-pill">Pill shape</span>
<span class="badge badge-success badge-dot">With dot</span>
<span class="tag">JavaScript <button class="tag-dismiss">✕</button></span>
```

### Alerts & Callouts
```html
<div class="alert alert-info">
<div class="alert-content">
<div class="alert-title">Information</div>
    This is an informational alert.
</div>
</div>
<div class="callout callout-warning">
    <strong>Warning:strong> This action cannot be undone.</strong>
</div>
```

### Tables
```html
<div class="table-wrapper">
    <table>
        <thead>...</thead>
        <tbody>...</tbody>
    </table>
</div>
<table class="table-compact">
<table class="table-striped">
```

### Overlays
```html
<div class="overlay">
    <div class="modal">
    <div class="modal-header">...</div>
    <div class="modal-body">...</div>
    <div class="modal-footer">...</div>
</div>
<div class="dropdown">
    <div class="dropdown-label">Account</div>
    <a href="#" class="dropdown-item active">Profilea>
    <a href="#" class="dropdown-item danger">Sign outa>
    <div class="dropdown-sep"></div>
</div>
<span class="tooltip">Tooltip content </span>
```

### Tree / Outliner
**plain.css's standout component** — perfect for file trees, outlines, and hierarchical data.
```html
<div class="tree-item">
<span class="drag-handle">⠿</span>
<button class="tree-toggle">▾</button>
<span class="tree-bullet">●</span>
<span class="tree-content" contenteditable="true">Editable item</span>
</div>
<div class="tree-indent">
</div>
<div class="drop-indicator"></div>
```

Features:
*   `.tree-item`, `.tree-indent-0` through `.tree-indent-4`
*   `.tree-toggle.collapsed` (rotates chevron)
*   `.tree-toggle.empty` (hidden for leaf nodes)
*   `.drag-handle` (appears on hover)
*   `.drop-indicator` (visual drag target)
*   `.focus-mode` (dims non-selected items)
*   `[contenteditable]` support with placeholder

### Utility Components
```html
<div class="avatar">JD</div>
    <div class="avatar avatar-sm">XS</div>
    <div class="avatar-group">...</div>
    <div class="progress">
        <div class="progress-bar" style="width:60%"></div>
    </div>
    <div class="progress progress-success">...</div>
    <div class="spinner spinner-sm"></div>
    <div class="spinner"></div>
    <div class="spinner spinner-lg"></div>
    <div class="skeleton skeleton-title"></div>
    <div class="skeleton skeleton-text"></div>
<div class="empty-state">
    <div class="empty-state-icon">📁</div>
    <div class="empty-state-title">Nothing here</div>
    <p>Descriptionp</p>
</div>
<div class="divider">Section</div>
<div class="shortcut-hint"><kbd>⌘kbd><kbd>Kkbd></div>
```

🎨 Visual Utilities
-------------------
### Backgrounds
```css
.bg-base .bg-surface .bg-raised
.bg-primary .bg-secondary .bg-info
.bg-success .bg-warning .bg-error
```

### Borders
```css
.border .border-strong
.border-t .border-b .border-l .border-r
.border-primary .border-secondary .border-info
.border-success .border-warning .border-error
```

### Shadows
```css
.shadow-xs .shadow-sm .shadow .shadow-lg .shadow-xl .shadow-inner
```

### Radius
```css
.rounded-xs .rounded-sm .rounded .rounded-lg .rounded-xl .rounded-full
```

### Misc
```css
.opacity-0 ... opacity-100
.cursor-pointer .cursor-not-allowed .cursor-grab
.select-none .select-all
.pointer-events-none .pointer-events-auto
.focus-ring .focus-ring-inset
.visually-hidden  /* accessible hide */
```

🌙 Dark Mode
------------
Automatic — no classes needed. The framework respects `prefers-color-scheme` and adjusts all semantic colors:
```css
@media (prefers-color-scheme: dark) {
    :root {
    --color-bg: #0a0a0a;
    --color-text: #fafafa;
    --color-primary: var(--blue-400);  /* lighter blue */
    /* everything else inverts appropriately */
    }
}
```

📦 Browser Support
------------------
*   Chrome (latest)
*   Firefox (latest)
*   Safari (latest)
*   Edge (latest)
*   Opera (latest)
Modern browsers only — IE11 is not supported.

📏 Size
-------
Framework
Gzipped
plain.css
~18kb
Bootstrap
~150kb
Tailwind (with purge)
~10-30kb*
*Tailwind requires build step and purging

🚀 Usage
--------
### Direct download
```bash
curl \-O https://raw.githubusercontent.com/sysdevcode/plain.css/main/plain.css
```

### npm  (coming soon)
```bash
npm install plain.css
```

### CDN (coming soon)
```html
<link rel="stylesheet" href="https://unpkg.com/plain.css@1.1/dist/plain.min.css">
```

📚 Documentation
----------------
The `plain.html` file in this repository is a comprehensive **kitchen sink reference** showing every token, component, and utility in action. Open it in your browser to:
*   See all color palettes
*   Test interactive components
*   Copy-paste examples
*   Verify dark mode behavior

🤝 Contributing
---------------
plain.css is intentionally minimal. 

Before adding features, ask:
*   Does this solve a common problem?
*   Can it be built with existing utilities?
*   Does it maintain the ~20kb gzipped target?
  
PRs welcome for:
*   Bug fixes
*   Accessibility improvements
*   Documentation clarifications

📄 License
----------
MIT © sysdevcode@gmail.com
* * *

**plain.css** — no prizes, just progress.
