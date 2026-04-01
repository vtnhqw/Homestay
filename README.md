# Serene Stays — Minimalist Homestay Portal

Serene Stays is a premium, single-page landing website designed for high-end, minimalist homestays. It focuses on a "quiet luxury" aesthetic, combining deep atmosphere with functional, state-of-the-art web components.

---

## 🚀 Tech Stack
- **HTML5 & Semantic SEO**: Structured for accessibility and search visibility.
- **Tailwind CSS**: Used for rapid utility-based styling and layout.
- **Vanilla JavaScript**: Lightweight logic for calendar rendering, modal management, and scroll effects.
- **Material Symbols (Google Fonts)**: Premium iconography for a clean, modern feel.
- **Glassmorphism Design System**: Custom CSS for frosted-glass effects (backdrop-blur + translucency).

---

## ✨ Key Features & Architecture

### 1. Dynamic Global Gradients
Instead of flat background colors, the site uses a **dual-mode global gradient system** applied directly to the `html` tag:
- **Light Mode ("Morning Mist")**: A 225° diagonal gradient from pure white to sky blue (`#bfdbfe`).
- **Dark Mode ("Midnight Sky")**: A 135° diagonal gradient from deep navy (`#020617`) into cobalt blue.
- **Implementation**: The backgrounds of all sections are set to `bg-transparent` to allow this atmosphere to flow throughout the entire page.

### 2. Premium Glassmorphism Navigation
A sticky header that adapts as you scroll:
- **Default State**: Ultra-translucent (`40%` opacity in light mode) with high-intensity `2xl` blur.
- **Scrolled State**: Triggered via JS at `20px` scroll depth, it increases opacity and adds a sophisticated shadow to create physical depth.
- **Logic**: Uses `scroll-padding-top: 100px` to ensure section links arrive with perfect breathing room under the sticky bar.

### 3. Interactive Availability Calendar
A custom-built JS calendar that handles:
- **Standardized Navigation**: The prev/next month buttons (`chevron_left`/`chevron_right`) share the exact same `cal-day` circular styling as the dates.
- **Dynamic Data**: Populates days automatically using a `BOOKED_DAYS` Set.
- **Immediate Booking**: Available dates are clickable and linked directly to the `openModal()` booking trigger.

### 4. Visual Components
- **Carousel Gallery**: A smooth, snap-scrolling horizontal gallery with smart navigation arrows.
- **Refined Cards**: `location-card` and `amenity-card` use a "Deep Elevation" shadow stack and refractive white borders to stand out in light mode.
- **Scroll Reveals**: An `IntersectionObserver` system that fades and slides sections into view as the user scrolls.

---

## 🛠️ How to Use & Extend

### To Run:
Simply open `serene-stays.html` in any modern web browser. No compilation or build steps are required.

### To Update Booked Dates:
Modify the following Set at the bottom of the `<script>` tag:
```javascript
const BOOKED_DAYS = new Set([1, 2, 3, 4, 13, 14, 15, 21, 22, 29, 30]);
```

### To Change Section Padding:
If you modify the header height, adjust the `scroll-padding-top` value in the `<style>` block:
```css
html {
    scroll-padding-top: 100px;
}
```

---

## 🤖 AI Development Notes
- **Theme Logic**: The project uses a `dark` class on the `html` element. Always use the `dark:` prefix in Tailwind to handle theme-specific styling.
- **Centering**: The `.cal-day` class uses `inline-flex` and `items-center justify-center` for layout. Icons within these circles are wrapped in `w-6 h-6` containers to ensure pixel-perfect centering regardless of glyph weight.
- **Transparency**: High-level section backgrounds are inherited from the `html` tag. Avoid using `bg-white` or `bg-slate-x` on sections unless you intend to break the global gradient flow.

---

© 2024 Serene Stays Development Team. Designed for peace and tranquility.
