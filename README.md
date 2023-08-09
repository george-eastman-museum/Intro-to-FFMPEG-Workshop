# Intro-to-FFMPEG-Workshop
Documentation for class on using FFmpeg. The website can be accessed [HERE](https://george-eastman-museum.github.io/Intro-to-FFMPEG-Workshop/)

## Building the docs

### HTML
- Install [Sphinx](http://www.writethedocs.org/guide/tools/sphinx/).
- Install the `sphinx-rtd-theme` and `sphinx-copybutton` and `sphinx_tabs` extensions.
- `cd` into the "docsrc" folder.
- Run `make html` to create the html builds in the "build/html" directory.
- `make clean` will remove all files from the "build" directory.
- The Makefile has had the following lines added for creating the GitHub page version.

```
github:
	@make html
	cp -a build/html/. ../docs
```
- If buiding for this GitHub repo, use `make github`.
- This builds the html version in "build/html" and then copies those files into the "docs" folder.

### PDF
- Note 1 - current instructions are for Linux.
- Note 2 - Run `make clean` before building the PDF version. Previously building the html version may cause issues with some formatting in the resulting pdf file.
- Install: `texlive-latex-extra`, `texlive-fonts-recommended`, `texlive-latex-recommended`, and `latexmk`.
- `cd` into the "docsrc" folder.
- Run `make latexpdf` to create the html builds in the "build/latex" directory.
- The Makefile has had the following lines added for creating pdf copy for GitHub.

```
pdf:
	@make latexpdf
	cp -a build/latex/*.pdf ../pdf
```
- If buiding for this GitHub repo, use `make pdf`.
- This builds the pdf version in "build/latex" and then copies the pdf file into the "pdf" folder.

## Making a GitHub Page with Sphinx

- Before starting, you will need to install `sphinx`.
- Create a repository on GitHub.
- Clone the repository.
- Create a `docs` and `docsrc` folder in the cloned repository:

```
cd /path/to/repository
mkdir docs
mkdir docsrc
```

- The "docs" folder will be where html builds are placed for GitHub to use while the "docsrc" folder will hold source files for our documentation, make files, and be the primary location where local builds are initially created.
- Create an empty file in the "docs" folder called ".nojekyll"

```
cd docs
touch .nojekyll
```

- Run sphinx setup in the "docsrc" folder.
- Open the file named "Makefile" and add the following text to the end.

```
github:
	@make html
	cp -a build/html/. ../docs
```

- When building the site with `make github` this will make the html version in a build folder in "docsrc" and then copy those files into the "docs" folder where GitHub will use them for the GitHub page.
- You can now start adding rst files to the source folder and try building the site.
