# tutthesis

This is a LaTeX document class made according to the Tampere University of Technology Thesis Writing Guide.
For bibliography styles to go with the document class, see [tut-bst](https://github.com/tkalliom/tut-bst).
If you'll be using Overleaf, the easiest way to get started is to use the [templates](https://www.overleaf.com/gallery/tagged/tut) in the gallery.


## Prerequisites

The class only requires the TeX Live base LaTeX collection, recommended fonts and Finnish language support (of course, you can also use MiKTeX).
Depending on your installation, you might already have all this.
However, if you're using other packages for features such as source code listings, you will need a more complete installation.
Usage of LuaTeX for a more modern support of Unicode is suggested, but not required.


## Usage

[Download](https://github.com/tkalliom/tutthesis/releases) the class file in this repository and place it in a search path or the directory with your document.
Do the same for the bibliography style of your choice from [tut-bst](https://github.com/tkalliom/tut-bst).

If you already have experience with LaTeX, the usage should (hopefully) be obvious, as the document class is based on the standard `report` and there should be helpful warnings for everything that is different.
The `examples` folder contains document files which can be used as a template if you don't want to start from scratch.
The documents and the comments in the files contain lots of hints, so at least skimming through is suggested.

Similarly to the standard `\title` and `\author`, there are commands for defining various bibliographic information such as your major, examiners etc.
Set these in the preamble, and then again translated inside an `otherlanguage` environment if your thesis has two abstracts.

The writing guide leaves several layout choices to the writer.
These are set with standard document class options (e.g. `twoside`), custom options (e.g. `globalnumbering`), standard commands (e.g. `\pagestyle{headings}` or package-specific commands (e.g. `\addto\extrasenglish{\btxifchangecaseoff}`).
See the appendix of the example document for more documentation; furthermore, the two example documents themselves cover both versions of each choice.

## PDF/A

The document class writes the bibliographic information into an `.xmpdata` file to be compatible with the package `pdfx`.
However, `pdfx` is a relatively young package and may still have issues with features such as OpenType fonts, so its usage is not required.
The ICC color profile required by the PDF/A standard is included in this repository for convenience because Debian (and by extension, Ubuntu, which is used by Overleaf) strips it out of `texlive-latex-extra` and until very recently did not did not refer to `icc-profiles` where the file is located instead. 

Until LaTeX / PDF/A support becomes more robust, the preflight tool in Adobe Acrobat Pro is probably the best option for getting a proper PDF/A file.
Note that even if a PDF reader shows a note about the PDF standard, that does not mean there are no errors in the file.
However, enabling `pdfx` is probably still a useful step in the right direction, since it at least sets metadata properly.