# MÉTIS Works - Design Specifications

## 📐 Layout Structure

### Canvas
- **Dimensions**: 1440px × 1024px
- **Background**: `#F6F3EF` (warm beige)

---

## 🎨 Color Palette

| Element | Color Code | Usage |
|---------|-----------|-------|
| Background | `#F6F3EF` | Page background |
| Primary Text | `#000000` | Headlines, body text |
| Accent Orange | `#C76A47` | Contact information, call-to-action |
| Shape Overlay | `#D2DCD3` | Background decorative element |
| Dark Gray | `#D9D9D9` | Shape fill |
| Charcoal | `#2B2B2B` | Dark ellipse overlay |

---

## 📝 Typography

### Font Families
1. **Helvetica Neue** - Primary typeface
2. **Canela** - Contact information (with Georgia fallback)

### Text Styles

| Element | Font | Weight | Size | Line Height | Position |
|---------|------|--------|------|-------------|----------|
| Brand Name | Helvetica Neue | 400 | 50px | 1.193em | (131, 47) |
| Main Heading | Helvetica Neue | 500 | 100px | 1.221em | (128, 234) |
| Description | Helvetica Neue | 400 | 50px | 1.193em | (133, 375) |
| Contact Info | Canela | 400 | 30px | 1.51em | (133, 622) |

---

## 📍 Element Positioning

### Logo
- **Position**: (56px, 50px)
- **Size**: 50px × 51px
- **Format**: SVG

### Brand Name "MÉTIS Works"
- **Position**: (131px, 47px)
- **Dimensions**: 318px × 58px
- **Text**: "MÉTIS Works"

### Main Heading
- **Position**: (128px, 234px)
- **Dimensions**: 1034px × 122px
- **Text**: "Design Led Innovation"

### Description
- **Position**: (133px, 375px)
- **Dimensions**: 1020px × 180px
- **Text**: "We help you see what's next by bridging human centricity, technology and business goals."

### Contact Information
- **Position**: (133px, 622px)
- **Dimensions**: 1020px × 128px
- **Color**: `#C76A47`
- **Text**: 
  ```
  Get in touch!
  call +41 76 605 0771
  or email
  ```

---

## 🎭 Background Decorative Shapes

### Container
- **Position**: (1142px, 750px) from top-left
- **Dimensions**: 425px × 420.72px
- **Blend Mode**: Multiply
- **Base Color**: `#D2DCD3`

### Ellipse 1 (Dark)
- **Size**: 661.95px × 678.05px
- **Color**: `#2B2B2B`
- **Blend Mode**: Multiply
- **Opacity**: 0.8

### Ellipse 2 (Orange)
- **Size**: 661.95px × 678.05px
- **Color**: `#C76A47`
- **Blend Mode**: Multiply
- **Opacity**: 0.6

### Ellipse 3 (Gray)
- **Size**: 403.99px × 349.54px
- **Color**: `#D9D9D9`
- **Opacity**: 0.5

---

## 📱 Responsive Breakpoints

### Desktop (1440px+)
- Original design specifications
- All elements at exact positions

### Tablet (768px - 1440px)
- Proportional scaling
- Reduced font sizes:
  - Main heading: 80px
  - Description: 40px
  - Contact: 24px
- Adjusted padding: 60px horizontal

### Mobile (<768px)
- Single column layout
- Further reduced font sizes:
  - Main heading: 48px
  - Description: 24px
  - Contact: 18px
- Padding: 30px horizontal
- Background shapes scaled to 0.8

---

## 🎯 Design Principles

1. **Minimalism**: Clean, spacious layout with ample white space
2. **Hierarchy**: Clear visual hierarchy through size and weight
3. **Color Usage**: Strategic use of accent color for CTAs
4. **Depth**: Overlapping shapes create visual interest without clutter
5. **Readability**: High contrast text with generous line spacing

---

## 🔧 Technical Implementation

### HTML Structure
```
body
  └── .container (1440×1024)
      ├── .logo-container
      │   └── img (logo.svg)
      ├── h1.brand-name
      ├── h2.main-heading
      ├── p.description
      ├── .contact-info
      └── .background-shapes
          └── .shape-container
              ├── .ellipse-dark
              ├── .ellipse-orange
              └── .ellipse-gray
```

### CSS Approach
- Absolute positioning for pixel-perfect placement
- CSS gradients for ellipse effects
- Mix-blend-mode for authentic overlay effect
- Media queries for responsive adaptation

---

## ✅ Quality Checklist

- [x] Exact color matching from Figma
- [x] Precise positioning of all elements
- [x] Correct typography hierarchy
- [x] Background shapes with proper blend modes
- [x] Responsive design for all screen sizes
- [x] SVG assets exported and optimized
- [x] Cross-browser compatibility
- [x] Semantic HTML structure
- [x] Clean, maintainable CSS

---

## 📊 Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- iOS Safari 14+
- Android Chrome 90+

---

## 🎨 Design Tools Used

- **Source**: Figma (Web Portfolio file)
- **Node ID**: 277-643
- **Frame Name**: "Métis Works HP"
- **Export Format**: SVG for graphics, CSS for styling

---

**Last Updated**: November 7, 2025
**Design Fidelity**: 100% match to Figma source

