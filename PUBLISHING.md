# Share the repository with a reviewer

## Complete the research record

1. Add the manuscript title and author details to README.md. If review is anonymous, follow the journal's anonymity policy.
2. Verify the provenance of the supplied `dataset/BnNERIntent25.json`. Record provenance and permitted redistribution for all included data.
3. Choose a code license with the coauthors. Data and upstream models may need separate terms. A license and citation file have deliberately not been fabricated.
4. Resolve or disclose the limitations in REPRODUCIBILITY.md. Record the actual working package versions and hardware after a successful run.

## Upload using the GitHub website

1. Sign in to GitHub and create a repository with a descriptive name such as `bengali-intent-classification`.
2. Choose visibility appropriate for reviewer access. A public repository is viewable without an invitation; a private repository requires granting reviewer access.
3. On the repository page, choose **Add file → Upload files**. Upload the prepared project files and only data whose redistribution is authorized. Include the hidden `.gitignore` file; exclude `.venv`, checkpoints, logs, credentials, and caches. Preserve the `dataset/` folder structure.
4. Commit the upload. Open `BERT.ipynb` on GitHub and check that it renders correctly.
5. Copy the repository link, or the notebook link. For a stable review reference, use the notebook's permalink for the uploaded commit and create a versioned release when ready.

The repository link will have the form `https://github.com/YOUR_USERNAME/YOUR_REPOSITORY`. Replace both placeholders; this is not an existing published URL.

Suggested reviewer response after the upload:

> The implementation is available at [repository URL]. The repository includes the research notebook, dependency instructions, and data availability and reproducibility notes.

Only state that the dataset or exact results are available once they actually are. No repository has been created or uploaded by the local preparation.
