# How to Import Projects into Your CV Builder

Your CV builder website ([yassinmaftah.github.io/cv](https://yassinmaftah.github.io/cv/)) uses a local-first architecture storing all state inside your browser's `localStorage` under the key `cvbuilder.v1`.

We generated **`cv-import/projects.json`** in the exact JSON schema required by the site's native **Import backup** button.

---

## Method 1: One-Click GUI Import (Recommended)

1. Open your CV website in your browser:
   👉 **[https://yassinmaftah.github.io/cv/](https://yassinmaftah.github.io/cv/)**
2. In the top navigation header, locate the **`Import backup`** button (next to `Export backup`).
3. Click **`Import backup`**.
4. In the file picker dialog that opens, navigate to:
   📂 `C:\Users\yassi\Desktop\cv_data\cv-import\projects.json`
5. Select the file and click **Open**.
6. That's it!
   - All **12 projects** will be instantly loaded into your **Saved info** list.
   - Your personal profile (Name, Email, Phone, GitHub, LinkedIn, Languages) and existing technologies categories are 100% preserved.
   - Switch to tab **`2. Create CV`** to toggle, reorder, or customize which projects appear on your generated CV.

---

## Method 2: Browser Developer Console Merge (Alternative)

If you have already made manual edits in your browser session that you don't want to replace, you can merge only the 12 projects directly into your active browser storage without touching your current profile or settings:

1. Open **[https://yassinmaftah.github.io/cv/](https://yassinmaftah.github.io/cv/)** in Chrome / your browser.
2. Press **F12** (or `Ctrl + Shift + I`) to open Developer Tools, then click the **Console** tab.
3. Open the file **`cv-import/projects-items-only.json`**, copy its entire contents, and run this one-line command in the console:

```javascript
(function(newProjects) {
  const KEY = 'cvbuilder.v1';
  let data = JSON.parse(localStorage.getItem(KEY)) || { profile: {}, items: [], cvs: [{ id: 'c1', name: 'Master CV', headline: 'Full-Stack Developer', ids: [], accent: '#2f4a7d', photo: true }] };
  
  // Remove any previous project entries with these IDs to prevent duplicates
  const newIds = new Set(newProjects.map(p => p.id));
  data.items = data.items.filter(i => !newIds.has(i.id) && i.id !== 'a1');
  
  // Append new projects
  data.items.push(...newProjects);
  
  // Ensure Master CV includes the new project IDs
  const activeCv = data.cvs.find(c => c.id === data.cur) || data.cvs[0];
  newProjects.forEach(p => {
    if (!activeCv.ids.includes(p.id)) activeCv.ids.push(p.id);
  });
  
  localStorage.setItem(KEY, JSON.stringify(data));
  location.reload();
})(/* PASTE JSON HERE */);
```

---

## Verification Checklist

After importing:
- [ ] Go to tab **`1. My Info`** -> Scroll down to **Saved info** -> Click **Projects**. You should see all 12 projects listed with their titles, dates, links, and technologies.
- [ ] Go to tab **`2. Create CV`**. On the left panel, click on **Projects (12)** to expand. You can click any project to add or remove it from the live CV page.
- [ ] Reorder projects on the page using the `↑` and `↓` buttons on each project card.
- [ ] Click **Download PDF** when ready to print or save your resume.
