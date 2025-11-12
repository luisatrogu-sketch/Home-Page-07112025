# 🚀 Quick Start Guide - MÉTIS Works Landing Page

## View the Landing Page

### Option 1: Direct File Open
Double-click `index.html` or drag it into your browser.

### Option 2: Local Server (Recommended)

**Using Python:**
```bash
cd /Users/luisatrogu/Desktop/Test
python3 -m http.server 8000
```
Then open: http://localhost:8000

**Using Node.js:**
```bash
cd /Users/luisatrogu/Desktop/Test
npx http-server -p 8000
```
Then open: http://localhost:8000

**Using PHP:**
```bash
cd /Users/luisatrogu/Desktop/Test
php -S localhost:8000
```
Then open: http://localhost:8000

---

## 📋 What's Included

✅ **index.html** - Main landing page  
✅ **styles.css** - All styling (pixel-perfect match to Figma)  
✅ **assets/** - SVG graphics from Figma  
✅ **README.md** - Project overview  
✅ **DESIGN_SPECS.md** - Complete design specifications  

---

## 🎯 Design Fidelity

This implementation matches the Figma design with:

- ✅ **Exact colors**: Background `#F6F3EF`, Accent `#C76A47`
- ✅ **Precise positioning**: All elements placed at exact pixel coordinates
- ✅ **Correct typography**: Helvetica Neue at specified sizes
- ✅ **Background shapes**: Overlapping ellipses with blend modes
- ✅ **Responsive layout**: Adapts to tablet and mobile screens

---

## 📱 Test Responsive Design

Resize your browser window to see the responsive breakpoints:

- **Desktop**: 1440px+ (original design)
- **Tablet**: 768px - 1440px
- **Mobile**: < 768px

Or use browser DevTools (F12) → Toggle Device Toolbar (Ctrl+Shift+M / Cmd+Shift+M)

---

## 🎨 Customization

### Change Colors
Edit `styles.css` and search for:
- Background: `#F6F3EF`
- Accent: `#C76A47`
- Text: `#000000`

### Change Text
Edit `index.html` and update:
- Brand name (line 17)
- Main heading (line 20)
- Description (lines 23-26)
- Contact info (lines 29-33)

### Adjust Layout
Modify positions in `styles.css`:
- Search for `position: absolute;`
- Adjust `left:` and `top:` values
- Reference `DESIGN_SPECS.md` for original values

---

## 🔍 Troubleshooting

**Issue**: Background shapes not visible  
**Solution**: Check that decorative ellipses are rendering. They use CSS gradients and blend modes.

**Issue**: Fonts look different  
**Solution**: Install Helvetica Neue or it will fall back to system fonts. Canela font may need to be added.

**Issue**: Logo not showing  
**Solution**: Ensure `assets/logo.svg` exists and path is correct.

**Issue**: Layout breaks on mobile  
**Solution**: Verify viewport meta tag is present in HTML head.

---

## 📚 Next Steps

1. **Add Canela font**: Include webfont for authentic contact text styling
2. **Add interactions**: Hover effects, smooth scrolling
3. **Integrate email**: Link contact email address
4. **SEO optimization**: Add meta tags, Open Graph tags
5. **Performance**: Optimize images, add lazy loading
6. **Analytics**: Add Google Analytics or similar
7. **Accessibility**: Add ARIA labels, keyboard navigation

---

## 🔗 Resources

- [Original Figma Design](https://www.figma.com/design/ttHstZAv3PMTt4cAforv2C/Web-Portfolio?node-id=277-643&t=1qXjFqWs4IfdpigE-4)
- [Canela Font](https://commercialtype.com/catalog/canela) (Commercial)
- [Helvetica Neue on Adobe Fonts](https://fonts.adobe.com/fonts/helvetica-neue)

---

## ✨ Pro Tips

1. **Test in multiple browsers**: Chrome, Firefox, Safari, Edge
2. **Check mobile devices**: Real device testing is best
3. **Validate HTML**: Use [W3C Validator](https://validator.w3.org/)
4. **Test accessibility**: Use [WAVE Tool](https://wave.webaim.org/)
5. **Optimize performance**: Check with [PageSpeed Insights](https://pagespeed.web.dev/)

---

**Need help?** Refer to `DESIGN_SPECS.md` for detailed specifications.

**Ready to deploy?** Consider hosting on:
- Netlify (drag & drop)
- Vercel (git integration)
- GitHub Pages (free hosting)
- AWS S3 + CloudFront (scalable)

