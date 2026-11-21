# Bilingual CV data import (EN / FR)

The CV builder is at https://yassinmaftah.github.io/cv/ .

## Import every project and technical skill

1. Download **[all_data.json](./all_data.json)** from this directory (use GitHub's **Download raw file** option).
2. Open the CV builder and click **+ Import data (EN / FR)**.
3. Choose `all_data.json`.
4. The importer merges **12 projects and 10 technical-skills categories**, each with English and French titles and descriptions. It updates entries by stable ID, prevents duplicates on repeated imports, and preserves your existing CVs, profile and unrelated saved information.
5. Go to **2. Create CV**, add any skills and projects you want, and select **EN** or **FR**. Both versions are stored in the same data.

Existing five starter technology categories are replaced by their equivalent imported categories where their original IDs and titles match. The existing CV selections are transferred to the new IDs. Other newly imported technology categories remain available to select manually.

For projects only, you can still import **[projects-items-only.json](./projects-items-only.json)** using the same button.

## JSON format

`all_data.json` has a top-level `items` array with entries having `type: "project"` or `type: "technologies"`. Each entry has a stable `id` and bilingual `title`, `sub`, and `text` properties:

```json
{
  "items": [
    {
      "id": "tech-front-end",
      "type": "technologies",
      "title": {"en": "Front-End", "fr": "Front-End"},
      "text": {"en": "HTML, CSS", "fr": "HTML, CSS"},
      "sub": {"en": "", "fr": ""},
      "link": "",
      "date": ""
    }
  ]
}
```

## Editing, backups, and compatibility

In **1. My Info**, edit English and French independently. In **2. Create CV**, the selected language determines which version is displayed and which headline is edited.

**Import JSON / Backup** automatically merges partial item lists, but complete backup JSON files restore the entire state after confirmation. Export your own backup before doing a full restore. Data is stored locally in your browser under `cvbuilder.v1`.

If the new import label does not appear immediately, refresh with **Ctrl + Shift + R** and check the GitHub Actions Pages deployment.
