# Bilingual project import (English / French)

The CV builder stores its data locally in your browser under `cvbuilder.v1`. No account or server is required.

## Import or update your 12 projects (recommended)

1. Open https://yassinmaftah.github.io/cv/
2. Click **Import projects** in the header.
3. Download and select **cv-import/projects-items-only.json** from this repository (or use **cv-import/projects.json**, which is also supported).
4. The 12 projects are **merged by project ID** into your saved information. Your existing CVs, profile, skills, other entries and project selections are preserved.
5. Open **2. Create CV**, choose projects on the left, then select **EN** or **FR** from the **Language** menu. Titles, descriptions and technology subtitles change automatically.

## Enter bilingual content

In **1. My Info**, enter English and French versions separately for profile headline, languages, technology categories, project titles, subtitles and descriptions, experience, education and other entries. URLs, dates, phone numbers and email addresses are language-neutral.

In **2. Create CV**, the headline input edits **only the currently selected language**. Switching EN/FR shows the independently saved version.

## Backup and compatibility

- **Export backup** saves all current content and both translations.
- **Import backup** replaces your entire saved state from a full backup file; use it only when you actually want a full restore.
- **Import projects** is non-destructive and accepts either a project array or a JSON object with an `items` array. Non-project entries in that file are ignored.
- Existing old English-only saved strings remain readable. They appear in EN and are used as a fallback in FR until you enter a translation.

The repository's **cv-import/projects-items-only.json**, **cv-import/projects.json**, and **cv-backup.json** include English and French versions of all 12 imported projects.
