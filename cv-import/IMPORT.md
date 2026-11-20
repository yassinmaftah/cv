# Import projects and switch CV languages

Visit https://yassinmaftah.github.io/cv/ (version **v2.1 · EN/FR** in the header).

## Import projects

1. Download [projects-items-only.json](./projects-items-only.json).
2. Click **+ Import projects (EN / FR)** and select the JSON file.
3. Open **2. Create CV** and add your projects from the left panel.
4. Select **EN** or **FR** in the language selector. The CV switches titles, subtitles and bullet points without changing project selections.

You can also use **Import JSON / Backup**: the builder automatically detects project-list JSON vs complete backup JSON. Project lists are merged without replacing your CVs; complete backups require confirmation before replacing existing data.

The 12 projects in this repository have both translations. If an older English-only project file uses the same IDs, French translations are filled from the built-in dictionary, while any existing manually edited French translations are preserved.

## Editing your CV

In **1. My Info**, the headline, languages, technology fields, project/experience/education title, subtitle, and descriptions have separate **EN** and **FR** inputs. Phone, email, URLs and dates are shared. In **2. Create CV**, the headline input edits only the selected language.

Use **Export backup** to save your complete bilingual profile and all CVs. Existing browser data and old backups remain supported. The site stores everything in browser localStorage (`cvbuilder.v1`).

**Troubleshooting:** If the header still doesn't show v2.1 or the **+ Import projects** button, force-refresh the page with **Ctrl + Shift + R** to bypass cached GitHub Pages content.
