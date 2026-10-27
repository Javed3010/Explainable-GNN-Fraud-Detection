# Before publishing to GitHub

- [ ] Obtain approval from the team and preserve all contributors’ attribution.
- [ ] Confirm that the Elliptic dataset may be redistributed; if not, remove `data/` and document acquisition instructions.
- [ ] Review notebooks and outputs for credentials, personal information, and absolute filesystem paths.
- [ ] Remove any large or unnecessary generated model artifacts and notebook outputs.
- [ ] Choose a code license only after obtaining rights-holder approval.
- [ ] Test notebooks in a clean environment and update version pins as needed.
- [ ] Confirm that performance metrics correspond to the intended model and data split.
- [ ] Push with GitHub Desktop or `git init`, `git add .`, `git commit -m "Initial project release"`, `git branch -M main`, and `git remote add origin <your-repository-url>` then `git push -u origin main`.

**GitHub file-size warning:** the features CSV is approximately 690 MB uncompressed and exceeds GitHub ordinary 100 MB per-file limit. Remove it from the repository or use an approved external data source; Git LFS is another option subject to quota and dataset redistribution rights.
