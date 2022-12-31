## Create a website using Sphinx

For each project, we'll create a website using [Sphinx](https://pypi.org/project/Sphinx/) and [Markdown](https://www.markdownguide.org/cheat-sheet/), mainly for two reasons:

- serving as a demo for the community
- reminding yourself

You can either use [Read the Docs](https://docs.readthedocs.io/en/stable/intro/getting-started-with-sphinx.html) (with [EthicalAds](https://docs.readthedocs.io/en/stable/advertising/ethical-advertising.html)) or [GitHub Actions](https://docs.github.com/en/actions) (under your own domain and ad-free) to build

### Install Sphinx

```bash
# create an environment with the name "docs"
conda env create -n docs python=3.8
conda activate docs
# install sphinx
conda install -c conda-forge sphinx
```

### Use Sphinx

```bash
cd /path/to/project
mkdir docs
cd docs
sphinx-quickstart
```

Follow the options:

```
Separate source and build directories (y/n) [n]: n
Project name: YourProjectName
Author name(s): YourName
Project release []: v0.0.0
Project language [en]: en
```

Follow the template [HERE](https://raw.githubusercontent.com/zzheng93/UrbanClimateExplorer/main/docs/index.rst) to modify the `index.rst` and add new pages.

Follow the template [HERE](https://github.com/zzheng93/UrbanClimateExplorer/blob/main/.github/workflows/main.yml) to set up `main.yml` for GitHub Actions.

### Reference

Last Update: 31/12/2022



