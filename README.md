Modified tufte-book class to be used for Tow Center reports, now susbtantially modified and renamed as towcenter-book. This branch is arranged to work with `biblatex-chicago` for Chicago-style endnote citations.

Essentials
----------

***Note: Some of the materials (e.g. graphics) in this repo are under copyright and may not be used without permission.*** 

**Features:**

	+ Formatted for A5 paper for (almost) trade-size bound printing.
	+ Colors, fonts and frontmatter match existing Tow Center reports.
	+ Supports margin notes on body text.
	+ Citation style is biblatex-chicago, which generates numerical according to the 15th+ edition of Chicago Manual of Style.


**To generate the pdf for printing, run the following commands in a Terminal window:**

	xelatex sample-report.tex
	biber sample-report
	xelatex sample-report.tex
	xelatex sample-report.tex



***Known Issues/Dependencies:***

1. This fileset does *not* compile properly if the `soul` package is present. Users who do a "complete" (rather than a minimal) install of MacTeX (see below) may need to delete this package manually in order to use these files.
2. Unlike the [towreport](https://github.com/susanemcg/tufte-latex/tree/towreport) branch of this template, this version requires `biblatex` and its dependencies in order to compile. Depending on the distribution of MacTeX you are running, you may need to update your packages accordingly.
3. Known additional packages required (over the [towreport](https://github.com/susanemcg/tufte-latex/tree/towreport) branch) include:
	+ biblatex
	+ biblatex-chicago
	+ logreq
	+ endnotes

**Formatting Basics:**

	***Bold, Italics, Quotations***
	\textbf{This text will be bold.}
	\textit{This text will be in italics.}
	``This will be in quotation marks.''

	***Lists***
	\begin{enumerate} Numbered list.
	\begin{itemize} Bulleted list.
	\begin{description}Description list.
	\item text Add an item.

	***Images***
	\begin{figure}
	\includegraphics{foldername/imagename.jpg}
	\caption{Caption text here, if any.}
	\end{figure}

	***Links***
	\href{Link URL}{Link text}

	***Blockquotes***
	\begin{quote}
	``Quote goes here''
	\end{quote}


***More formatting help***

LaTeX is an extremely powerful typesetting and layout engine; virtually every element of the page can be controlled in great detail. Good examples of how to achieve specific formats can be found in the LaTeX WikiBook here: [https://en.wikibooks.org/wiki/LaTeX](https://en.wikibooks.org/wiki/LaTeX). More detailed and extensive help can also be found on TeX Exchange, the Stack Exchange site dedicated to LaTeX: [https://tex.stackexchange.com/](https://tex.stackexchange.com/)

Certain formats & styles may require additional LaTeX packages; for more on how to add these to your LaTeX installation (or how to install LaTeX in the first place), see below.

Setting up LaTeX
----------------

**Installing LaTeX**

Use of these files requires an installation of LaTeX. MacTeX for Mac users can be downloaded from the MacTeX website here: [https://www.tug.org/mactex/](https://www.tug.org/mactex/).

**Installing Biber and/or BibLaTeX**

The simplest way to do this is through `tlmgr`, which you probably already have installed if you've setup MacTeX. Start with

`sudo tlmgr update --all` 

to update all of the packages you have currently installed. You may first be prompted to update `tlmgr` itself.

Generally, you can use `tlmgr` to check/update/install packages as you need them. So for `biber`, first check whether it's installed via `tlmgr show biber`. If it's not installed, run `sudo tlmgr install biber`. You can do the same for `biblatex` and `biblatex-chicago`. You can also install packages manually per the below.


**Installing missing packages**

Some of the styles required for these files may not be in the default installation of MacTeX. If you see a 'missing file' error when you run xelatex, search for and download the package from the CTAN (Comprehensive TeX Archive Network) website here: [http://www.ctan.org/](http://www.ctan.org/)

The package download may contain the generated `package_name.sty` file, or it may contain a `package_name.ins` file. If the latter, run `latex package_name.ins` in a terminal window; it should generate the necessary `.sty` file.

Finally, you must move the packages into place and "restart" (e.g. recompile) LaTeX for the changes to take effect. Exactly where the packages go depends on your system, but you're looking for your "main" LaTeX installation. A good place to start is:


`MacintoshHD -> Library -> TeX -> texmf-dist -> tex -> xelatex`

You'll want to drag the entire `package_name` folder into this folder - having the extra files in there is ok. You'll need an administrator's password for this.

Finally, to recompile LaTeX so that it recognizes the new packages, in Terminal run: `sudo texhash`. It will ask you to authenticate, and then you should see the compile messages. 

A helpful (and more complete) reference for installing LaTeX packages can be found on WikiBooks here: [https://en.wikibooks.org/wiki/LaTeX/Installing_Extra_Packages](https://en.wikibooks.org/wiki/LaTeX/Installing_Extra_Packages)

