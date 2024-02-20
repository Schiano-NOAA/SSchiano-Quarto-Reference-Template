---
title: "Generalized Quarto Template"
author: 
  - name: "Sam Schiano"
    orcid: 0009-0003-3744-6428
    email: "samantha.schiano@noaa.gov"
    affiliations:
      - name: "NOAA Fisheries OST"
        address: "1315 East-West Highway"
        city: "Silver Spring"
        state: "MD"
        postal-code: "20910"
  - name: "John Doe"
    orcid: 0009-0003-3744-6429
    email: johndoe@noaa.gov
date: today
format: 
  html:
    keep-md: true
    embed-resources: true
  pdf:
    keep-md: true
    embed-resources: true
    toc: true
fig-width: 8
fig-height: 5
params:
  fsc: "SE"
  region: "SATL"
  species_init: "RS"
---


::: {.cell}

```{.r .cell-code}
library(here)
```

::: {.cell-output .cell-output-stderr}

```
here() starts at C:/Users/samantha.schiano/Documents/GitHub-Repos/Quarto-Reference-Template
```


:::
:::



## YAML

The area at the top is the YAML command area which dictates some portions of the document. Additional and in-depth details for this portion can also be found at https://quarto.org/docs/reference/formats/opml.html#format-options

The list of commands include

-   title

-   author (name and information)

    -   name
    -   orcid

-   date

    -   today, now, last-modified
    -   or dates in these orders
        -   MM/dd/yyyy
        -   MM-dd-yyyy
        -   MM/dd/yy
        -   MM-dd-yy
        -   yyyy-MM-dd
        -   dd MM yyyy
        -   MM dd, yyyy
        -   YYYY-MM-DDTHH:mm:ssZ

-   format (or multiple formats)

    format:

    html: default

    pdf: default

    docx

-   toc: table of contents

-   code-fold: (true/false) - in an HTML format, the code is hidden in a drop down tab for the use to view or not view

-   toc-depth: specify the number of section levels to include in the table of contents

-   number-sections

You can set all R code chunk options here:

execute:

| Execute options | Actions              |
|-----------------|----------------------|
| echo            | true, false          |
| warning         | true, false          |
| eval            | true, false, \[...\] |
| output          | true, false, asis    |
| warning         | true, false          |
| error           | true, false          |
| include         | true, false          |
| cache           | true, false, refresh |
| freeze          | true, false, auto    |

: These options are listed after the execute: command with a tab inset followed by the option with a colon, space and the action.

## Template

Quarto enables you to weave together content and executable code into a finished document. To learn more about Quarto see <https://quarto.org>.

This template consists of generalized code that could be used as a reference when creating a new quarto document. Tips and tricks that were learned along the way have been included in the respective section. A lot of Rmarkdown notation can be utilized into quarto with previous Rmarkdown documents still able to be rendered when converted to a .qmd (to my knowledge).

## Formatting

### Headings and Page Breaks

Headings can be noted by using a specified number of #. A single \# indicates the *Header 1*, two \# indicates *Header 2*, three \# indicates *Header 3*, and so on.

Page breaks can be added manually into the text when editing the document in the source editor (not visual). The notation is `<br` which will create a manual page break between r objects.

### Font Changes

-   *Italic* is indicated through a word or set of words encased in \*

    `*word*`

-   **Bold** is indicated through a word or set of words encased by a set of double \*

    `**word**`

### Equations

Sample equation (inline): $R_{y}=\frac{\alpha*SSB_{y}}{1+\beta*SSB_{y}}$ Code: `$R_{y}=\frac{\alpha*SSB_{y}}{1+\beta*SSB_{y}}$`

Sample equation (own line): <br> $$
R_{y}=\frac{\alpha*SSB_{y}}{1+\beta*SSB_{y}}
$$ <br>

Greek letters notations:

Generalized notation - `$\alpha$`

| Greek Letter Spelling | Lowercase  | Capital    |
|-----------------------|------------|------------|
| alpha                 | $\alpha$   | A          |
| beta                  | $\beta$    | B          |
| gamma                 | $\gamma$   | $\Gamma$   |
| delta                 | $\delta$   | $\Delta$   |
| epsilon               | $\epsilon$ | E          |
| zeta                  | $\zeta$    | Z          |
| eta                   | $\eta$     | H          |
| theta                 | $\theta$   | $\Theta$   |
| kappa                 | $\kappa$   | K          |
| lambda                | $\lambda$  | $\Lambda$  |
| mu                    | $\mu$      | M          |
| nu                    | $\nu$      | N          |
| omicron               | $\omicron$ | O          |
| rho                   | $\rho$     | P          |
| sigma                 | $\sigma$   | $\Sigma$   |
| tau                   | $\tau$     | T          |
| upsilon               | $\upsilon$ | $\Upsilon$ |
| chi                   | $\chi$     | X          |
| psi                   | $\psi$     | $\Psi$     |
| iota                  | $\iota$    | I          |
| xi                    | $\xi$      | $\Xi$      |
| pi                    | $\pi$      | $\Pi$      |
| phi                   | $\phi$     | $\Phi$     |
| omega                 | $\omega$   | $\Omega$   |

### Other Helpful Functions for Equations

| Component   | Notation              | Output              |
|-------------|-----------------------|---------------------|
| Subscript   | `$*symbol*\_{sub}$`   | $symbol_{sub}$      |
| Superscript | `$*symbol*\^{sup}$`   | $symbol^{sup}$      |
| Fractions   | `$\frac{num}{denom}$` | $\frac{num}{denom}$ |
| Roots       | `$\sqrt{num}$`        | $\sqrt{num}$        |

For in-line text, superscript and subscript notation is different.

-   Superscript^2^ - `superscript^2^`

-   Subscript~2~ - `subscript~2~`

## Running Code

When you click the **Render** button a document will be generated that includes both content and the output of embedded code. You can embed code like this:



::: {.cell}

```{.r .cell-code}
x = 1 + 1
print(x)
```

::: {.cell-output .cell-output-stdout}

```
[1] 2
```


:::
:::



You can add options to executable code to remove the code chunk in the rendered document like this



::: {.cell}
::: {.cell-output .cell-output-stdout}

```
[1] 4
```


:::
:::



The `echo: false` option disables the printing of code (only output is displayed).

Other options include:

| Option  | Description                                                |
|---------|------------------------------------------------------------|
| eval    | Evaluate the code chunk                                    |
| output  | Include the source code in output                          |
| warning | Include warnings in the output                             |
| error   | Include errors in the output                               |
| include | Catch all for preventing any output code (code or results) |

### Figures

Inline references to figures can be generate by using the \@. If one referenced a figure in the test, you would need to label the figure in the R code chunk (@fig-test1).



::: {.cell .fig-cap-location-bottom}
::: {.cell-output-display}
![Test figure caption and example to add in.](quarto-template_files/figure-pdf/fig-test1-1.pdf){#fig-test1}
:::
:::



### Tables

Adding flextable objects into the document.



::: {.cell tbl-cap='Test1 table caption and example to add in.'}
::: {.cell-output-display}


```{=latex}
\global\setlength{\Oldarrayrulewidth}{\arrayrulewidth}

\global\setlength{\Oldtabcolsep}{\tabcolsep}

\setlength{\tabcolsep}{0pt}

\renewcommand*{\arraystretch}{1.5}



\providecommand{\ascline}[3]{\noalign{\global\arrayrulewidth #1}\arrayrulecolor[HTML]{#2}\cline{#3}}

\begin{longtable}[c]{|p{0.75in}|p{0.75in}}



\ascline{1.5pt}{666666}{1-2}

\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{x}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{y}}} \\

\ascline{1.5pt}{666666}{1-2}\endfirsthead 

\ascline{1.5pt}{666666}{1-2}

\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{x}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{y}}} \\

\ascline{1.5pt}{666666}{1-2}\endhead



\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{1}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2021}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2022}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{3}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2023}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{4}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2024}}} \\

\ascline{1.5pt}{666666}{1-2}



\end{longtable}



\arrayrulecolor[HTML]{000000}

\global\setlength{\arrayrulewidth}{\Oldarrayrulewidth}

\global\setlength{\tabcolsep}{\Oldtabcolsep}

\renewcommand*{\arraystretch}{1}
```


:::
:::



<br>



::: {.cell tbl-cap='Test2 table caption to add in break.'}
::: {.cell-output-display}


```{=latex}
\global\setlength{\Oldarrayrulewidth}{\arrayrulewidth}

\global\setlength{\Oldtabcolsep}{\tabcolsep}

\setlength{\tabcolsep}{0pt}

\renewcommand*{\arraystretch}{1.5}



\providecommand{\ascline}[3]{\noalign{\global\arrayrulewidth #1}\arrayrulecolor[HTML]{#2}\cline{#3}}

\begin{longtable}[c]{|p{0.75in}|p{0.75in}}



\ascline{1.5pt}{666666}{1-2}

\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{x}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{y}}} \\

\ascline{1.5pt}{666666}{1-2}\endfirsthead 

\ascline{1.5pt}{666666}{1-2}

\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{x}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{y}}} \\

\ascline{1.5pt}{666666}{1-2}\endhead



\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{5}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2021}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{6}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2022}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{7}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2023}}} \\





\multicolumn{1}{>{\raggedleft}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{8}}} & \multicolumn{1}{>{\raggedright}m{\dimexpr 0.75in+0\tabcolsep}}{\textcolor[HTML]{000000}{\fontsize{11}{11}\selectfont{2024}}} \\

\ascline{1.5pt}{666666}{1-2}



\end{longtable}



\arrayrulecolor[HTML]{000000}

\global\setlength{\arrayrulewidth}{\Oldarrayrulewidth}

\global\setlength{\tabcolsep}{\Oldtabcolsep}

\renewcommand*{\arraystretch}{1}
```


:::
:::



## Modular Workflow

Quarto and Rmarkdown also allow the user to develop a template from a set of .qmd or .rmd documents from calling them in R chunks.

### Child Documents

One can combine a series of qmd files when the report is very long and would be easier to work with in sections rather than a single full report. In order to add one to the template document, the user would need to add it as an R chunk that includes an option of child = "child_file.qmd". Child files will be added as a new section into the template.










## Child Template Example

This document is designed to be built with the quarto template as an example child. It is implemented modularly to make the format easier to work with. Example R code is provided to test the functionality when adding it into the template document.

Function test:
$$
Z_{a,j} = F_{a,j} + M_{a,j}
$$

Linear model and results for R code test:

::: {.cell}
::: {.cell-output-display}
![](quarto-template_files/figure-pdf/mod-res-1.pdf)
:::

::: {.cell-output-display}
![](quarto-template_files/figure-pdf/mod-res-2.pdf)
:::

::: {.cell-output-display}
![](quarto-template_files/figure-pdf/mod-res-3.pdf)
:::

::: {.cell-output-display}
![](quarto-template_files/figure-pdf/mod-res-4.pdf)
:::
:::



Alternatively, you can conditionally load a child document using the following syntax:




```{.r .cell-code}
if(params$region=="SATL"){
  a <- knitr::knit_child("cond_child1.qmd", quiet = TRUE)
  cat(a, sep='\n')
}
```







## Conditional Child Document

This would be a regional specific template or content that would be required by the council or other governing body.



If the user just wants the output of the R code from the child, the user would set an additional option of eval = T.

Testing the visual editor when adding citations [@base].

## References
