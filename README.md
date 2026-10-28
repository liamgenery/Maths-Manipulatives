# Maths Manipulatives – PowerPoint add-in

A box you place on a slide that stays interactive during the slideshow. It includes:

- **Counters** – a red/yellow two-sided counter (double-tap to flip) and seven single colours.
- **Place value counters** – 1000, 100, 10, 1, 0.1 and 0.01.
- **Base 10 blocks** – ones, tens, hundreds and a thousand cube.
- **Number shapes** – 1 to 10.
- **Rods** – 1 to 10, with numbers you can turn on or off.
- **Mats** – a ten frame, a double ten frame, a part-whole model, a Th H T O place value chart and an O . t h place value chart.

**Exchange** groups 10 matching place value counters or blocks into the next one up. It also breaks one piece into 10 of the next one down.

`index.html` also works on its own in any browser. That covers LibreOffice, OnlyOffice and any computer without the add-in.

## 1. Host the folder (HTTPS required)

Office add-ins load from a web address, so these files need to live on a website that uses HTTPS. Any of these works:

- **GitHub Pages** (free). Make a public repository, upload every file in this folder, then turn Pages on in Settings → Pages. Your address will look like `https://USERNAME.github.io/REPO`. Check that it loads on the school network. github.io can be slow or blocked in mainland China.
- **The school's own web server or intranet.** Ask IT. This is the most reliable option on site.

Then open `manifest.xml` and replace every `https://YOUR-SITE` with your address. There is no trailing slash.

```bash
sed -i 's#https://YOUR-SITE#https://USERNAME.github.io/REPO#g' manifest.xml
```

## 2. Try it yourself (sideload)

- **PowerPoint on the web:** Insert → Add-ins → More Add-ins → My Add-ins → *Upload My Add-in* → choose `manifest.xml`.
- **PowerPoint desktop (Windows, Microsoft 365):** go to Home or Insert → Add-ins. If you see *Upload My Add-in*, use it.
  - If you don't see it, put `manifest.xml` in a shared network folder.
  - Then go to File → Options → Trust Center → Trust Center Settings → Trusted Add-in Catalogs. Add the folder path, tick *Show in Menu*, and restart PowerPoint.
  - The add-in will then appear under Add-ins → *Shared Folder*.

Insert it on a slide, then drag the box so it fills the slide.

## 3. Give it to all staff

Ask IT to deploy `manifest.xml` through the Microsoft 365 admin centre (Settings → Integrated apps → Upload custom apps). It will then appear for everyone automatically, with no sideloading.

The add-in is saved inside the .pptx. Anyone who opens the file without the add-in sees a still picture of it instead. Deploying it to all staff fixes that.

## Using it

| Do this | How |
|---|---|
| Add a piece | Drag it out of the tray, or tap it |
| Move pieces | Drag. Drag on empty space to box-select a group |
| Flip or turn | Double-tap the piece, or press **Turn** |
| Regroup | Select 10 matching pieces → **Exchange**. Select 1 → **Exchange** breaks it into 10 |
| Remove | Drag the piece onto the toolbar, or press **Delete** |
| Change size | **A−** / **A+** |
| Hide the toolbar | **▾**. Bring it back with **☰ Tools** |
| Prepare a slide in advance | Set it up in normal view → **⋯ → Save as starting layout** → save the presentation. Each slideshow starts from that layout. **⋯ → Reset** puts it back |

Keyboard shortcuts: Delete removes the selection, Ctrl+D copies it, Ctrl+A selects everything and Esc deselects.
