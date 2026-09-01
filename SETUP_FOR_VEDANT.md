# Install this GitHub profile

This package is already customized for **vedantbhusari33**. Your links, portrait source, selected projects, theme and automation files are filled in.

## 1. Protect the existing profile

Your profile repository already exists, so clone it first. This also gives you a local backup of the current README.

```powershell
cd $env:USERPROFILE\Downloads
git clone https://github.com/vedantbhusari33/vedantbhusari33.git vedant-profile
```

Extract this ZIP. Copy everything inside the `vedant-github-profile` folder into the new `vedant-profile` folder and allow Windows to replace `README.md`.

## 2. Allow the automated files to update

Open the repository on GitHub, then go to:

`Settings -> Actions -> General -> Workflow permissions`

Select **Read and write permissions** and save.

## 3. Add the metrics secret

1. Open <https://github.com/settings/tokens>.
2. Choose **Generate new token (classic)**.
3. Select `read:user`. Select `repo` only if you want private contributions included.
4. Copy the token once. Never paste it into any project file.
5. In the profile repository, open `Settings -> Secrets and variables -> Actions`.
6. Create a repository secret named exactly `METRICS_TOKEN` and paste the token there.

## 4. Upload the profile

Open PowerShell inside the `vedant-profile` folder and run:

```powershell
git add -A
git commit -m "build automated profile README"
git push
```

## 5. Start the three automations

Open the repository's **Actions** tab. Run these workflows once in this order:

1. **Charts and cards**
2. **Metrics**
3. **Snake**

The snake URLs show a temporary 404 until the first Snake workflow creates the `output` branch. That is normal.

## 6. Final check

Open <https://github.com/vedantbhusari33> in GitHub dark mode and light mode, and then check it once on your phone.

## What updates automatically

- 3D calendar, languages and achievements: every 6 hours
- Contribution snake: every 12 hours
- Skill/language radars, statistics and project cards: daily

## Easy future edits

- Change the introduction or links in `README.md`.
- Change self-rated skill values in `assets/skills.json`.
- Change the four featured repositories in `assets/projects.json` and update the matching card links in `README.md`.
- Regenerate the portrait locally with:

```powershell
python -m pip install pillow
python scripts/dotify.py assets/profile-photo.png -o assets/portrait --cols 100 --equalize --detail 0.5 --color --circle --reveal
```

The generators and automation structure follow Gargi Bhardwaj's Profile README Guide and have been rewritten and customized for Vedant's profile.
