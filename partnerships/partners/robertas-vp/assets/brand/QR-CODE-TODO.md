# QR Code Generation - TODO

## Purpose
Create QR code for EU Executive One-Pager linking to Nexrizen contact/booking page

## Recommended Link
Choose one of:
1. **nexrizen.com** (general website)
2. **nexrizen.com/contact** (contact page)
3. **Wei's calendar link** (direct booking - fastest)

## How to Generate

### Option 1: QR Code Generator (Recommended)
1. Go to https://www.qr-code-generator.com/
2. Enter URL: `https://www.nexrizen.com` (or calendar link)
3. Customize:
   - **Color:** `#502cff` (Nexrizen primary purple/blue)
   - **Background:** White
   - **Size:** 300x300px minimum (for print quality)
   - **Format:** PNG (transparent background if possible)
4. Download as `nexrizen-contact-qr.png`

### Option 2: Python Script (if needed)
```python
import qrcode

qr = qrcode.QRCode(version=1, box_size=10, border=4)
qr.add_data('https://www.nexrizen.com')
qr.make(fit=True)

img = qr.make_image(fill_color="#502cff", back_color="white")
img.save('nexrizen-contact-qr.png')
```

### Option 3: Online Tools
- https://qr.io/
- https://www.the-qrcode-generator.com/
- https://www.qrcode-monkey.com/

## File Specifications

**Filename:** `nexrizen-contact-qr.png`
**Size:** 300x300px or larger (for print quality)
**Format:** PNG with transparent or white background
**Color:** `#502cff` (brand primary) or black
**Location:** Save to `/partnerships/partners/robertas-vp/assets/brand/`

## Placement on One-Pager
- Bottom right corner of page
- Size: ~1 inch square (2.54cm)
- Caption: "Scan to connect"or "Visit nexrizen.com"

---

**Status:** ⚠️ TODO - Generate QR code before final design
**Priority:** Medium (needed for final PDF, can use placeholder in draft)
