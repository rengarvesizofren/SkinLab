# GitHub publication checklist — SkinLab

- Repository name: $name
- Description: A Windows workspace for organizing and managing League of Legends skin mods.
- Topics: league-of-legends, skin-mods, mod-manager, game-data
- README: prepared as README.md; original preserved as README-upstream.md.
- Validation: structure and required files checked. Build, tests, installer, and runtime are unverified because .NET SDK and Cargo are unavailable.
- Initial release: wait for a successful Windows build and test run and confirm distribution rights. The project reports FileVersion 2.19.0; check release history before choosing a tag.
- Before publishing: review LICENSE.txt, bundled executable provenance, third-party notices, and game-policy compatibility. CS2 is not included in this source snapshot.

## Publish commands

Create an empty GitHub repository named $name, replace <OWNER>, then run from this folder:

`powershell
git init -b main
git add .
git status --short
git commit -m "Prepare SkinLab repository"
git remote add origin https://github.com/<OWNER>/SkinLab.git
git push -u origin main
`

No remote was created and no push has occurred.

- Large installer: omitted from this Git tree due GitHub's 100 MB file limit; the separate publication ZIP retains the original file. Consider a Release asset only after rights and integrity are confirmed.

