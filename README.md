# Sonalika Photography Website

Premium single-page photography portfolio website for **Sonalika Photography** built as a static HTML project with cinematic motion, luxury editorial styling, and a scroll-driven hero frame sequence.

## Overview

This project is a custom landing page and portfolio website designed for a photography brand.  
It focuses on:

- a premium visual identity
- a cinematic hero section built from frame-by-frame images
- elegant gallery and service presentation
- smooth interactions for desktop and mobile
- simple static deployment without a build step

The site is currently powered by one main file:

- `Design/code.html`

There is no framework build process. The page uses:

- HTML
- Tailwind CSS via CDN
- custom CSS
- vanilla JavaScript

## Main Highlights

- Scroll / swipe driven hero animation using **80 image frames**
- Glass-style transparent navigation bar
- Active gold navigation state based on section visibility
- Responsive hero behavior for desktop and mobile
- Infinite horizontal gallery motion
- Animated service cards with premium hover depth
- About section with portrait interaction
- Refined footer with contact and address information
- Vercel-ready root routing via `vercel.json`

## Project Structure

```text
Suresh/
├─ Design/
│  ├─ code.html
│  ├─ DESIGN.md
│  └─ screen.png
├─ Hero_camera/
│  ├─ Robotic_camera_orbiting_202604011739_000.jpg
│  ├─ ...
│  └─ Robotic_camera_orbiting_202604011739_079.jpg
├─ images/
│  ├─ Logo.png
│  ├─ Logo1.png
│  ├─ Suresh.jpeg
│  ├─ 1.jpeg
│  ├─ 2.jpeg
│  ├─ 3.jpeg
│  ├─ Wedding.jpeg
│  ├─ wed.jpg
│  ├─ pre.jpg
│  ├─ baby.jpg
│  ├─ name.jpg
│  ├─ birth.jpg
│  └─ cor.jpg
├─ Notes.txt
├─ vercel.json
└─ README.md
```

## Page Sections

### 1. Navbar

The top navigation is fixed and uses a dark glass effect.  
It contains:

- brand logo
- brand name
- section links for Gallery, About, Services, and Contact

Behavior:

- active link gets a gold highlight
- links update based on visible section
- mobile menu opens as a full-screen overlay

### 2. Hero Sequence

This is the signature section of the website.

It uses the image sequence stored in:

- `Hero_camera/Robotic_camera_orbiting_202604011739_000.jpg`
- through
- `Hero_camera/Robotic_camera_orbiting_202604011739_079.jpg`

How it works:

- JavaScript preloads the frame images
- a `<canvas>` draws the active frame
- on desktop, mouse wheel input drives the sequence first
- after the sequence finishes, the page is released to the About section
- on mobile, touch swipe drives the sequence
- mobile rendering uses a more contained frame style to reduce over-zoom and cropping

Why mobile looked zoomed earlier:

- the source frames are wide landscape images
- mobile screens are tall portrait screens
- if the frame is drawn in full `cover` style, the sides get cropped heavily

Current mobile fix:

- more matte spacing around the canvas
- softer 3D movement
- more contained rendering on small screens
- touch-based sequence control

### 3. About Section

This section introduces the photographer and includes:

- portrait image
- name and role
- brand philosophy text
- CTA button

The portrait area includes a subtle parallax interaction on pointer devices.

### 4. Gallery Section

The gallery uses a continuous marquee-style motion to display image cards in a premium exhibition layout.

Behavior:

- infinite horizontal motion
- hover-based image scaling
- masked left and right edges for a softer visual transition

### 5. Services Section

Services are presented as square image cards.

Included services:

- Wedding
- Pre-wedding
- Bangle wearing
- Baby naming
- Birthday
- Corporate

Behavior:

- tilt hover effect
- framed image layout
- premium gold-accent hover styling

### 6. Contact / Footer

The footer includes:

- brand title
- email
- WhatsApp
- phone number
- Instagram
- Vogue Portfolio placeholder
- physical address

Current address:

- `Puthupatti Bus Stand, Alangulam - 627851`

## Design Direction

The project follows a luxury editorial direction documented in:

- `Design/DESIGN.md`

Core style ideas:

- serif + sans-serif pairing
- gold accent used sparingly
- sharp architectural edges
- large negative space
- cinematic imagery-first presentation
- glassmorphism for the navbar

## How to Edit Content

All main content lives inside:

- `Design/code.html`

Typical edits:

- logo: update files inside `images/`
- hero sequence: replace images inside `Hero_camera/`
- gallery images: edit the gallery image paths in `code.html`
- services: change service card images and titles in `code.html`
- about text: edit the About section paragraph
- contact info: edit the footer contact block

## Replacing the Hero Frames

If you want to replace the hero animation:

1. Keep the files inside `Hero_camera/`
2. Use the same numbering style from `000` to `079`
3. Keep the same file extension or update the JS source path in `code.html`
4. If you add more or fewer frames, update the `frameCount` value in the hero script

Current expected frame count:

- `80`

Current naming prefix:

- `Robotic_camera_orbiting_202604011739_`

## Local Preview

Because this is a static site, you can preview it in simple ways.

### Option 1: Open the HTML file directly

Open:

- `Design/code.html`

This works for quick visual review, but some browser behaviors are more reliable when served through a local server.

### Option 2: Use a local static server

From the project root, you can use:

```powershell
python -m http.server 8000
```

Then open:

```text
http://localhost:8000/Design/code.html
```

## Deployment on Vercel

This project is already prepared for Vercel.

File used:

- `vercel.json`

Current rewrite:

- `/` → `/Design/code.html`

That means when the site is deployed, opening the root domain will load the main page automatically.

### Deploy Steps

1. Push the project to GitHub.
2. Open Vercel.
3. Click `Add New Project`.
4. Import this repository.
5. Keep the project root as the `Suresh` folder.
6. Use framework preset `Other`.
7. Leave build command empty.
8. Leave output directory empty.
9. Click `Deploy`.

### Important Deployment Notes

- Make sure `Design`, `Hero_camera`, and `images` folders are committed to GitHub.
- The hero animation depends on all 80 image frames being present.
- Large JPG frame sequences can slow initial load on low-end mobile devices.

## Performance Notes

The heaviest part of this site is the hero frame sequence.

If you want better production performance later, the best improvements are:

- convert hero JPG frames to compressed `webp`
- reduce file size of the frame images
- keep image dimensions only as large as needed
- optimize large gallery and service images

## Troubleshooting

### Hero frames not loading

Check:

- `Hero_camera` folder exists
- all 80 files are present
- file names still match the expected numbering

### Images appear broken after deployment

Check:

- folder names are exactly the same
- relative paths in `code.html` were not changed incorrectly
- all assets were committed and pushed

### Mobile hero feels too cropped

Reason:

- landscape source frames on a portrait screen naturally crop more

Fix options:

- use wider matte framing
- reduce 3D movement further on mobile
- prepare a separate mobile hero sequence with portrait-friendly framing

## Future Improvements

- convert hero sequence to `webp`
- create a dedicated mobile-optimized frame sequence
- add a real portfolio link instead of placeholder
- split CSS and JS into separate files for easier maintenance
- add analytics and SEO meta improvements
- add form-based contact section if needed

## Credits

Brand:

- Sonalika Photography

Creative direction and build:

- custom static implementation using Tailwind CDN and vanilla JavaScript
