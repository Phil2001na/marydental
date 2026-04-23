# MARY DENTAL WEBSITE - CPANEL DEPLOYMENT GUIDE

## YOUR CURRENT SETUP ✓

**Files Location on PC:** 
```
C:\Users\khendrick\Downloads\marydental\
```

All your website files and images should be in this folder.

---

## FILE STRUCTURE (What Goes in Your Folder)

Your `marydental` folder should contain:

```
marydental/
├── index.html
├── about.html
├── services.html
├── team.html
├── contact.html
├── logo.jpg
├── dental_chair.JPG
├── dental_drills.JPG
├── resceptiondesk.JPG
├── team_doctor1.jpg
├── team_doctor2.jpg
├── team_doctor3.jpg
└── team_doctor4.jpg
```

**Total: 5 HTML files + 8 image files = 13 files**

---

## IMAGE PATHS IN HTML (Already Configured)

All images use **relative paths** that work when everything is in the root directory:

```html
<!-- Logo (used in navigation and footer) -->
<img src="logo.jpg">

<!-- Clinic Photos -->
<img src="dental_chair.JPG">
<img src="dental_drills.JPG">
<img src="resceptiondesk.JPG">

<!-- Team Photos -->
<img src="team_doctor1.jpg">
<img src="team_doctor2.jpg">
<img src="team_doctor3.jpg">
<img src="team_doctor4.jpg">
```

✓ **No folder paths needed** - all files are in root
✓ **No "./" or "../" needed** - simple filenames only
✓ **Case-sensitive** - Make sure JPG vs jpg matches exactly

---

## BEFORE YOU UPLOAD - IMAGE OPTIMIZATION

⚠️ **CRITICAL:** Compress these images first or your site will be slow!

### Current Sizes (TOO LARGE):
- dental_chair.JPG: **12MB** 🔴
- dental_drills.JPG: **10MB** 🔴
- resceptiondesk.JPG: **6MB** 🔴

### Target Sizes:
- Each should be: **Under 500KB** ✓

### How to Compress:

**Option 1: TinyPNG (Easiest)**
1. Go to https://tinypng.com
2. Drag and drop your 3 large JPG files
3. Wait for compression
4. Download compressed versions
5. Replace original files in your marydental folder

**Option 2: Squoosh (More Control)**
1. Go to https://squoosh.app
2. Upload one image at a time
3. Choose "MozJPEG" format
4. Set quality to 75-85%
5. Download and replace

**Option 3: Windows Built-in (Quick)**
1. Right-click image → Open With → Paint
2. Resize to 1920px width (keep aspect ratio)
3. Save As → JPEG → Quality: 85%
4. Replace original

---

## CPANEL UPLOAD STEPS

### Step 1: Login to cPanel
1. Go to your hosting provider's cPanel login page
2. Enter your username and password
3. Look for "File Manager" icon

### Step 2: Navigate to public_html
1. Click "File Manager"
2. Open `public_html` folder (this is your website root)
3. **Delete any existing index.html or default files**

### Step 3: Upload All Files
1. Click "Upload" button
2. Select ALL files from `C:\Users\khendrick\Downloads\marydental\`
3. Upload all 13 files (5 HTML + 8 images)
4. Wait for upload to complete

### Step 4: Verify File Names
Make sure these exact filenames are uploaded:
- ✓ index.html
- ✓ about.html
- ✓ services.html
- ✓ team.html
- ✓ contact.html
- ✓ logo.jpg
- ✓ dental_chair.JPG (capital JPG)
- ✓ dental_drills.JPG (capital JPG)
- ✓ resceptiondesk.JPG (capital JPG)
- ✓ team_doctor1.jpg
- ✓ team_doctor2.jpg
- ✓ team_doctor3.jpg
- ✓ team_doctor4.jpg

**Important:** Linux servers are case-sensitive!
- `logo.jpg` ≠ `Logo.JPG`
- `dental_chair.JPG` ≠ `dental_chair.jpg`

### Step 5: Set Permissions (Usually Automatic)
Files should have these permissions:
- HTML files: 644
- Image files: 644

If images don't show, right-click → Permissions → set to 644

### Step 6: Test Your Website
1. Open browser
2. Go to your domain: `www.yourdomainname.com`
3. Check all pages load correctly
4. Click through navigation
5. Verify all images display

---

## FOLDER STRUCTURE ON SERVER

After upload, your `public_html` should look like:

```
public_html/
├── index.html           ← Home page (loads automatically)
├── about.html
├── services.html
├── team.html
├── contact.html
├── logo.jpg
├── dental_chair.JPG
├── dental_drills.JPG
├── resceptiondesk.JPG
├── team_doctor1.jpg
├── team_doctor2.jpg
├── team_doctor3.jpg
└── team_doctor4.jpg
```

**DO NOT create subfolders!** All files go directly in `public_html/`

---

## TROUBLESHOOTING

### Problem: Images Don't Show
**Solution 1:** Check filename case
- HTML says: `dental_chair.JPG`
- File uploaded: `dental_chair.jpg` ← Won't work!
- Fix: Rename file to match HTML exactly

**Solution 2:** Check file permissions
- Right-click file in cPanel → Permissions
- Set to 644
- Click "Change Permissions"

**Solution 3:** Clear browser cache
- Press Ctrl + Shift + R (hard refresh)
- Or clear browser cache completely

### Problem: Site is Slow
**Cause:** Images too large (12MB, 10MB, 6MB)
**Solution:** Compress images as described above

### Problem: Logo Looks Wrong
**Check:** 
1. Is logo.jpg uploaded?
2. Is it the correct file? (Should be 3.3KB Mary Dental logo)
3. Try re-uploading

### Problem: Page Not Found
**Check:**
1. Is index.html in public_html root? (Not in subfolder)
2. Filename is exactly `index.html` (lowercase, no spaces)
3. Domain DNS is pointed to hosting server

---

## UPDATING THE SITE LATER

To update content:
1. Download the HTML file from cPanel
2. Edit locally on your PC
3. Re-upload and overwrite old file

To update images:
1. Upload new image to cPanel
2. Use same filename (or update HTML to reference new name)
3. Delete old image if filename changed

---

## NEXT STEPS AFTER UPLOAD

### 1. Update Contact Information
Edit these files and replace placeholders:

**contact.html:**
- Phone: Change `+264 61 123 456` to real number
- WhatsApp link: Update phone number
- Google Maps: Add real address/coordinates

**All pages (footer):**
- Phone number
- Email address
- Complete street address

### 2. Update Team Information
**team.html:**
- Replace stock photos with actual team photos
- Update names
- Update credentials
- Update bios

### 3. Set Up Google Analytics
Add tracking code to all pages (instructions in SEO guide)

### 4. Submit to Google
- Create Google Business Profile
- Submit sitemap to Google Search Console
- See SEO_OPTIMIZATION_GUIDE.md for details

---

## DOMAIN SETUP

If you haven't connected your domain yet:

1. **Check DNS Settings**
   - Login to your domain registrar (where you bought the domain)
   - Update nameservers to point to your hosting provider
   - Or update A record to point to your hosting IP address

2. **Wait for Propagation**
   - DNS changes take 24-48 hours
   - Use https://www.whatsmydns.net to check progress

3. **Force HTTPS**
   - In cPanel, search for "SSL/TLS"
   - Install free SSL certificate (Let's Encrypt)
   - Force all traffic to HTTPS

---

## FILE CHECKLIST BEFORE UPLOAD

Copy this checklist:

```
□ All HTML files are in C:\Users\khendrick\Downloads\marydental\
□ All image files are in the same folder
□ Large images (dental_chair, dental_drills, resceptiondesk) are compressed
□ Filenames match exactly (case-sensitive)
□ No spaces in filenames
□ Tested files open locally on PC
□ Ready to upload to cPanel
```

---

## QUICK REFERENCE - FILE SIZES

After compression, your files should be approximately:

```
index.html          ~21KB
about.html          ~19KB
services.html       ~20KB
team.html           ~17KB
contact.html        ~16KB
logo.jpg            ~3KB
dental_chair.JPG    ~400KB (after compression from 12MB)
dental_drills.JPG   ~400KB (after compression from 10MB)
resceptiondesk.JPG  ~400KB (after compression from 6MB)
team_doctor1.jpg    ~6KB
team_doctor2.jpg    ~1KB
team_doctor3.jpg    ~1KB
team_doctor4.jpg    ~5KB

TOTAL: ~2MB (after image compression)
```

---

## SUPPORT

If you run into issues:
1. Check your hosting provider's documentation
2. Contact hosting support (they can help with cPanel)
3. Refer to SEO_OPTIMIZATION_GUIDE.md for technical details

---

**Your website is ready to go live! Just compress those images and upload to cPanel.** 🚀
