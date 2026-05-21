TotnKids — clean Vercel deploy folder
=====================================

This folder is what you drag onto Vercel. It contains ONLY public files,
so nothing private (brand book, audit, reference PDFs) can leak.

Already here:
  - vercel.json   (serves the site at the root URL + security headers)

You need to add (2 things I couldn't copy for you):
  1. v2.html      — the site itself
  2. the hero video + poster (optional; without them the hero shows a
     placeholder, which is fine for a preview)

----------------------------------------------------------------------
OPTION 1 — one command (does everything)
----------------------------------------------------------------------
Open Terminal, paste this whole block, press Enter:

SRC="/Users/tweenguyen/Desktop/TotnKids website"
DEST="/Users/tweenguyen/Desktop/totnkids-deploy"
cp "$SRC/v2.html" "$DEST/"
mkdir -p "$DEST/REFERENCE/Website photo "
cp "$SRC/REFERENCE/Homepage video - Japanese baby waking up.mp4" "$DEST/REFERENCE/"
cp "$SRC/REFERENCE/Website photo /3 Homepage.png" "$DEST/REFERENCE/Website photo /"

----------------------------------------------------------------------
OPTION 2 — Finder (no Terminal)
----------------------------------------------------------------------
1. Open the "TotnKids website" folder.
2. Copy v2.html into this folder (totnkids-deploy). Keep the name v2.html.
3. (Optional, for the hero video) inside this folder create a folder named
   REFERENCE, and inside it another named "Website photo " (with a trailing
   space). Copy in:
     - Homepage video - Japanese baby waking up.mp4  -> REFERENCE/
     - 3 Homepage.png                                -> REFERENCE/Website photo /
   Skip this step if you don't need the hero video yet.

----------------------------------------------------------------------
THEN — publish
----------------------------------------------------------------------
1. Go to https://vercel.com/new
2. Choose to deploy without Git (drag-and-drop / upload).
3. Drag THIS folder (totnkids-deploy) in.
4. Framework Preset: Other. Leave Build Command and Output Directory empty.
5. Deploy. You'll get the live URL. vercel.json makes the site open at "/".

To update later: replace v2.html in this folder with your newest version
and deploy again.
