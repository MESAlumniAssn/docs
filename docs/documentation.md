# Updating the documentation

The documentation site uses [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/). All the pages are written in Markdown with few sprinkles of HTML and CSS.

The documentation site is hosted on Github Pages. The configuration file, `ci.yml` is located in `.github/workflows` in the `docs` repository. Once a change is pushed to the `main` branch, the workflow automatically kicks off and deploys the site on Github Pages.

Presently, all changes are being pushed directly to the `main` branch. It is up to the developers if they would like to create a feature branch and merge the changes to the `main` branch.
