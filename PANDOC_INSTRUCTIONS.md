# Pandoc PPTX Export Solution

## Problem
Pandoc couldn't use the Google Slides template (`styles_guidelines.pptx`) because it doesn't have the standard layout names Pandoc expects.

## Solution
I've created two approaches:

### Approach 1: Clean Pandoc Template (Recommended for editing)
- **File:** `slides-final.pptx` (60KB)
- **Source:** `slides-pandoc.md` + `pandoc-reference.pptx`
- **Pros:** 
  - Clean, editable PowerPoint format
  - Standard layouts that work in all Office tools
  - Easy to apply your own template in PowerPoint
- **Cons:** Uses default Office styling (not GitGuardian branded yet)

### Approach 2: Marp Export (Best for presenting)
- **File:** `slides.pptx` (5.5MB)
- **Pros:** Preserves all GitGuardian styling, fonts, colors
- **Cons:** Less editable, may have compatibility issues

## How to Apply GitGuardian Branding to Pandoc Version

### Option A: In PowerPoint/Google Slides
1. Open `slides-final.pptx`
2. Go to **View > Slide Master**
3. Apply your colors, fonts, logo:
   - Background: `#0C1222` (dark blue)
   - Text: `#FFFFFF` (white)
   - Accent: `#6B8FE8` (blue)
   - Title font: Funnel Display
   - Body font: Instrument Sans
4. Add GitGuardian logo to master footer
5. Save as new template

### Option B: Create Custom Pandoc Reference Template
1. Start with `pandoc-reference.pptx`
2. Open in PowerPoint
3. Customize the slide master with your branding
4. Save as `gitguardian-template.pptx`
5. Re-export:
   ```bash
   pandoc slides-pandoc.md -t pptx \
     --reference-doc=gitguardian-template.pptx \
     -o slides-branded.pptx
   ```

## Files Generated

| File | Size | Source | Purpose |
|------|------|--------|---------|
| `slides.html` | 374KB | Marp | For web viewing |
| `slides.pdf` | 480KB | Marp | For PDF sharing |
| `slides.pptx` | 5.5MB | Marp | Styled presentation (less editable) |
| `slides-pandoc.md` | - | Clean markdown | Source for Pandoc |
| `pandoc-reference.pptx` | - | Pandoc default | Reference template |
| `slides-final.pptx` | 60KB | Pandoc | Editable presentation |

## Recommended Workflow

**For presenting today (styled):**
- Use `slides.pptx` (Marp export with full GitGuardian branding)

**For editing and sharing (flexible):**
- Use `slides-final.pptx` (Pandoc export)
- Apply branding in PowerPoint/Google Slides
- Easier to edit, update, and share

**For web/PDF:**
- Use `slides.html` or `slides.pdf` (perfect rendering)

## Key Differences

### Marp Version
- ✅ Perfect GitGuardian styling
- ✅ Custom fonts, colors, layout
- ❌ Less editable
- ❌ Large file size
- ❌ May have compatibility issues

### Pandoc Version
- ✅ Highly editable
- ✅ Works everywhere (Office, Google, LibreOffice)
- ✅ Small file size
- ❌ Needs manual branding
- ❌ Default styling

## Next Steps

1. **Test both versions** to see which works better for your needs
2. **If using Pandoc version:** Follow "Option A" above to apply branding
3. **If using Marp version:** Use directly, but test compatibility first
